# 2단계 - 로또(자동)

* 로또 구입 금액을 입력하면 구입 금액에 해당하는 로또를 발급해야 한다.
* 로또 1장의 가격은 1000원이다.

# 입력

1. 구입금액을 입력해 주세요.
2. 지난 주 당첨 번호를 입력해 주세요.

# 출력

1. ?개를 구매했습니다.
2. 갯수 * 6개로 이루어진 로또
3. 당첨 통계 (수익률 포함)

# 설계

## 생각

1. 사용자(콘솔)은 시스템에 (돈)을 입력한다.
2. (돈)을 기준으로 (로또들)을 생성한다.
3. (로또들)을 순회하면서 (돈-이익)을 계산한다.

## 클래스

* [x] Money
    * [x] 개발자 주관 Int 로 타입을 한정한다.
    * [x] 0 이하의 숫자를 가질 수 없다.
    * [x] 계산 단위가 주어졌을때 몇개까지 살 수 있는지 반환한다.
    * [x] 다른 Money와 비교해아여 비율을 반환한다.  
* [x] Lottos
    * [x] List<Lotto> 를 가지고 있는 일급 컬렉션이다.
    * [x] 돈이 입력되면, 특정 계산을 통해 Lotto를 만들고 소유하는 계산을 한다.
    * [x] 당첨 로또를 입력해서 모든 로또들의 총당첨 결과를 반환한다
* [x] Lotto
    * [x] Set<LottoNumber> 를 가지고 있는 일급 컬렉션이다. 
    * [x] 당첨 로또를 입력해서 당첨 결과를 반환한다.  
* [x] LottoNumber
    * [x] 1~45 까지의 숫자만 가질 수 있다.
    * [x] Map<Integer, LottoNumber> 캐싱을 이용, factory method 이용
    * [x] 출력시에 오름차순으로 출력되므로 비교 가능한도록 한다 
* [x] MatchBoard
    * [x] enum 타입, 당첨 금액과 매핑되어 있다.
    * [x] 맞은 개수를 통해 알맞은 enum 식별자를 반환한다
* [x] MatchResult
    * [x] Map<MatchBoard, Int> 를 가지고 있는 일급 컬렉션이다.
    * [x] 총 수익률을 반환할 수 있다
* [x] LottoService
    * [x] Service 역할의 클래스
* [x] LottoApplication
    * [x] Controller 역할의 메인 클래스