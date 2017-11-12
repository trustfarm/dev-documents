# DPOS 네트워크 보안리스크를 완화하고 중앙화를 막는 consensus 개선방안


### 1. 배경
-----------

POS (Proof Of Stake) 블록체인의 경우는 검증인(Validator) 노드에 일정 Fund 를 보유시켜서 , 이를 기반으로 대의적으로 신규블록을 생성하는 합의를 수행한다.
이때, 검증인 노드의 잘못된 투표 및 많은 Fund가 보유되고있는 특정 몇개의 노드를 무력화하는 51% Attack 을 포함한 DDOS 공격이 가능하다.
또는, 작은 Fund 를 가지고서 악의적으로 validator 로 참여한후, 대형 펀드를 가지고있는 노드 몇개를 DDOS 하는 방법도 가능하다.

또한, 내부자 매수등의 방법을 통해서 검증인 노드를 무력화 할수 도 있다.
그외에 stake grinding 등의 방법도 가능하다.

위의 다양한 공격방법중 기술적으로 발생할수있는 POS 에 대한 가장 중요한 공격방식으로 거론 되는것은, 
* 1) nothing at stake  -  1vote 가 아닌, 가능한 여러곳에 vote 해서 이득을 취하려는 형태. 즉, 이쪽도 걸고, 저쪽도 걸어서 둘중에 한곳에서 되면 이득을 취한다.
* 2) stake grinding 등의 작은 노드 펀드로 지속적으로 DDOS 처럼 공격하는 방식이 있다.

casper 및 cosmos 등의 새로운 DPOS 합의 알고리즘에서는 위의 경우에 fund 를 잃게 하는등의 불이익을 줌으로서 이를 해결하고자 한다.
하지만, 위의 경우도, 네트워크 공격자체가 목적인 공격자에게는 무력화 될수있다.

### 2. 문제해결을 위한 알고리즘 제안
-----------

* 1) 검증인 노드에 Hardcap/Softcap 의 fund 상한선을 정하는 컨센서스 정책으로, 한도 이상의 Fund 노드에는 Cap 이상의 Fund에 대한 이자는 지급하지 않는다.

* 2) 최소 하한의 검증인 노드의 fund 를 지정한다.

* 3) 최소 지정한 검증인 노드를 전체 목표노드의 150% 이내에서 여분으로 확대가능하고, 이를 논리적으로 분산시킬수있도록 한다.

* 4) 검증인 노드가 위치한 물리적 네트워크를 다양하게 분산하여야 한다. 이는 IP 를 통한 서버의 geolocation 정보를 기반으로 같은 네트워크 IDC 세그멘트에는 전체 검증인 노드중 10% 이상의 노드가 참여하지 못하게 한다. 10%라는 비중은 상대적이므로, 이는 현실적인 적용상황에서 다소 조정이 가능하다. 위의 경우는 50개 이상의 노드가 참여한다 할경우를 기준으로 경험적으로 가이드를 잡은 것이다.

* 5) 반드시, 네트워크가 않좋은 지역의 geolocation 및 IDC 네트워크 노드도 10% 정도 포함하게 한다.
이는 기회의 균등의 의미도 있지만, 네트워크 상황이 물리적으로 약한 경우, DDOS 자체가 10% 노드에 공격을 쉽게 못한다는 의미도 된다.

### 3. 기대효과
----------

* 1) DPOS 검증인 노드의 분산화, 분권화를 통하여, 블록체인 네트워크 자체의 보안성을 강화한다.
* 2) 불필요하게 많은 Fund 가 노드에 잠기지 않게하여, Fund 가 거래소및 실제 적용되는 분야에 유동성을 제공할수있게 하여야 한다.
* 3) Fund 의 분산을 통해서 P2P 들의 참여폭을 확대하고, 이를 기반으로 블록체인의 활성화 , 가치를 상승시킨다.


[ENG]
=====

# Consensus improvement plan to mitigate DPOS network security risk and prevent centralization

### 1. Background
-------

In the POS (Proof Of Stake) block chain, a certain fund is held in the validator node, and a new block is created based on this.

At this time, Validator node will wrong vote and DDOS ,including a 51% attack that disables a certain number of nodes holding a lot of funds is possible.
Alternatively, it is possible to DDOS some of the nodes that have a large fund after having a small fund and participating maliciously as a validator.


In addition, Validator node may be disabled by a way of buying a insiders.
Other methods such as stake grinding are also possible.

Among the various attack vectors mentioned above, as the most important attack vector to POS that can occur technically,

* 1) nothing at stake - not a 1vote, but a way to earn a profit by voting at as many as possible. In other words, you can take advantage of this if you hang on one side and walk on the other side.

* 2) stake grinding - continuously attack like a DDOS attack with small funds of validator's node.

Such as casper and cosmos, new DPOS consensus algorithm, they solve this problem by disadvantages/fenalty such as losing funds.
However, in the above case, Just brutal attack on the network itself, is purpose then network can be incapacitate by attacker.

### 2. Algorithm proposal for problem solving
-------------------------------------------

* 1) The consensus policy is to set the upper limit which is apply hardcap/softcap fund for the validator node, the fund over upper limit or cap, the interest fee will not paid. 

* 2) Specify the minimum fund for the validation node.

* 3) It is possible to extend the verification node within 150% of the total target node and logically distribute it.

* 4) The physical network where validator node is located should be diversified. Based on the geolocation information of the server through IP, more than 10% of nodes that are participating in the same network IDC segment, prevent participating to validation node. 10% is relative value, so this is somewhat adjustable in realistic applications. In this case, the guide is experience based on the case where more than 50 nodes participate.

* 5) Be sure to include 10% of the geolocation and IDC network nodes where in poor network condition areas.
This means equal opportunity, but also means that if the network situation is physically weak, DDOS itself can not easily attack 10% nodes.

### 3. Expected Effect
----------

* 1) Through the diversifying and decentralization of DPOS validator nodes, the security of the blockchain network itself will be more secure.
* 2) Ensure that unnecessary funds are not locked into the nodes, so that the Fund can provide liquidity to the exchanges and the fields to which they are actually applied application.
* 3) Through the dispersion of funds, the participation of P2P will expanded and the activation and value of the blockchain are increased based on this.
