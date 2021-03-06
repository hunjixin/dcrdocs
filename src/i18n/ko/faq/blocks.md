# <i class="fa fa-cubes"></i> 블록 

---

#### 1. 블록이 여러 번 확인 된 후 고아가 될 수 있습니까? 

충분히 긴 reorg가있는 경우에만[^8918]. 이를 위해서는 포크의 반대쪽에서 현재의 가장 좋은 체인에서 작동하는 해시 전력보다 더 많은 해시 전력이 필요합니다.

---

#### 2. 메인 넷을 사용할 수 있다면 testnet 블록 탐색기를 제거 할 수 있습니까? 

Testnet은 계속해서 새로운 기능의 테스트 장소가 될 것이므로 testnet 블록 탐색기를 계속 유지하는 것이 좋습니다[^9621].

---

#### 3. "[INF] CHAN: 고아 블록 추가"메시지의 의미는 무엇입니까? 

부모가없는 블록이 수신되었음을 의미합니다[^14660]. 동기화가 작동하는 방식 때문에 `dcrd` 를 다시 시작할 때 거의 항상 발생합니다. 여전히 최신 블록까지 동기화하고 있지만 원격 피어 (즉, 앞선 사용자)는 새로운 블록이 표시되었음을 알리는 알림을 보냅니다.이 중 하나는 아직 부모가없는 것입니다.

이를 무시하기보다 일단 동기화가 완료 될 때까지는 본질적으로 나중에 저장하므로 부모 블록을 확보하면 새로운 블록이 자동으로 연결됩니다.

---

#### 4. 새로운 소프트웨어가 출시 될 때마다 블록 체인을 다시 다운로드해야합니까? 

다시 시작하는 것이 의미가있는 엄청난 변화가 아니라면 업그레이드에 체인을 다시 다운로드 할 필요가 거의 없습니다[^14788] 일반적으로는 일을 마이그레이션해야 작동합니다.

---

#### 5. 기원 블록 번호는 무엇입니까?

기원 블록[^16987] 은 블록 높이 0 (블록 번호 0)입니다. 그 이후의 모든 블록은 1 씩 증가합니다.

---

#### 6. "[INF] CHAN: FORK: Block 000..." 메시지의 의미는 무엇입니까? 

다음은 메시지 예입니다:

```no-highlight
[INF] CHAN: FORK: Block 0000000000001aedcf1b82b087a1d05ef787550174da1012e473e8ee8c178937 (height 17879) forks the chain at height 17878/block 000000000000150f863186cab6ef5c433bcc155d2f683394f8e65cb037f80b16, but does not cause a reorganize
```

두 명의 광부가 같은시기에 한 블록에 대한 해결책을 찾았고 둘 다 해결 된 블록을 네트워크에 제출했음을 의미합니다[^17791]. 둘 다 유효한 해결책이지만 , 노드가 다른 방안을 찾았음을 의미합니다. ([000000000000147d33cde5e9823122924fb43405418712720eb6457956d8edbb](https://mainnet.decred.org/block/000000000000147d33cde5e9823122924fb43405418712720eb6457956d8edbb)) 첫째,보기의 노드의 관점, 새로운 블록에서 그렇게 ([0000000000001aedcf1b82b087a1d05ef787550174da1012e473e8ee8c178937](https://mainnet.decred.org/block/0000000000001aedcf1b82b087a1d05ef787550174da1012e473e8ee8c178937)) 가 측쇄에있었습니다.

이 블록을 릴레이 할 시간이 필요하기 때문에, 다른 노드가 당신의 노드가 처음 본 다른 솔루션 0000000000001aedcf1b82b087a1d05ef787550174da1012e473e8ee8c178937 을 먼저 봤지만 ([000000000000147d33cde5e9823122924fb43405418712720eb6457956d8edbb](https://mainnet.decred.org/block/000000000000147d33cde5e9823122924fb43405418712720eb6457956d8edbb)) 사이드 체인에 포함 된 것 일수도 있습니다.

이것은 완전히 정상적이며 다음 블록이 발견 될 때마다 자체적으로 해결됩니다. 이제는 가장 긴 체인을 정의 할 것이고, 빌드되지 않은 솔루션이 고아가 될 것이기 때문입니다.

이 경우, 블록 #17880 ([000000000000154c6091747245e3c2620447c71b346aed09548e74b4543d0d66](https://mainnet.decred.org/block/000000000000154c6091747245e3c2620447c71b346aed09548e74b4543d0d66)) 위에 건물을 끝내므로 다른 용액 000000000000147d33cde5e9823122924fb43405418712720eb6457956d8edbb, ([0000000000001aedcf1b82b087a1d05ef787550174da1012e473e8ee8c178937](https://mainnet.decred.org/block/0000000000001aedcf1b82b087a1d05ef787550174da1012e473e8ee8c178937)) 이 고아가되었습니다.

---

## <i class="fa fa-book"></i> 소스 

[^8918]: Decred Forum, [Post 8,918](https://forum.decred.org/threads/557/#post-8918)
[^9621]: Decred Forum, [Post 9,621](https://forum.decred.org/threads/651/#post-9621)
[^14660]: Decred Forum, [Post 14,660](https://forum.decred.org/threads/1333/#post-14660)
[^14788]: Decred Forum, [Post 14,788](https://forum.decred.org/threads/1336/#post-14788)
[^16987]: Decred Forum, [Post 16,987](https://forum.decred.org/threads/1852/#post-16987)
[^17791]: Decred Forum, [Post 17,791](https://forum.decred.org/threads/2925/#post-17791)
