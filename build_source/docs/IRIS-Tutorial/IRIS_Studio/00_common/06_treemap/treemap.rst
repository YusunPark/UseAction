===================================================================
트리맵
===================================================================

데이터를 그룹과 그 그룹의 값에 따라 크기와 색을 다르게 표현하는 트리맵을 보고서에 추가하는 방법에 관하여 기술합니다.

-------------------------------------------------------------------
사용 데이터
-------------------------------------------------------------------

| 트리맵을 그리기 위해서는 그룹 컬럼과 값(수치) 컬럼이 필요합니다.
| 아래 그림은 야구팀 성적데이터의 팀 ID와 각 팀의 득점의 총합으로 나타난 데이터의 예시 화면입니다.

.. image:: ./images/ko/treemap_00.png
    :alt: 트리맵_사용데이터설명
    :scale: 90%

-------------------------------------------------------------------
트리맵 생성 절차
-------------------------------------------------------------------

트리맵을 그리는 방법은 다음과 같습니다. 아래 절차는 보고서 편집 화면에서 진행됩니다.


차트 영역 생성
=================================================================

.. image:: ./images/ko/treemap_01.png
    :alt: 트리맵_차트영역생성

위 화면에 주황색 상자로 표시된 "차트" 아이콘을 클릭한 후, 마우스 드래그 앤 드롭으로 트리맵이 그려질 영역을 생성합니다.

|

데이터 설정
=================================================================

.. image:: ./images/ko/treemap_02.png
    :alt: 트리맵_데이터설정

이어서 화면 우측의 "데이터" 탭에서 트리맵을 그릴 때 사용될 데이터를 설정합니다. 
위 예시 화면은 야구팀 성적데이터의 전체 기간 중 출현한 팀ID(TEAMID)별로 득점(R)의 총합을 구하고, 그 중 득점의 총합의 상위 40개만 추려낸 설정을 보여주고 있습니다.

.. code::

    데이터 Command: * |  stats sum(R) as TotalScore by TEAMID | sort 40 -TotalScore

시각화 옵션 설정
=================================================================

.. image:: ./images/ko/treemap_03.png
    :alt: 트리맵_시각화 옵션 설정

데이터 설정이 끝나면 "실행"을 누른뒤 우측 "시각화" 탭으로 이동합니다.
"시각화 유형"에서 "트리맵"을 선택한 후 하단의 "일반" 옆의 "시각화 옵션"을 클릭하십시오.

.. |opt1| image:: ./images/ko/treemap_04.png
    :scale: 90%
    :alt: 트리맵 시각화 옵션 (1) - 일반

.. |opt2| image:: ./images/ko/treemap_05.png
    :scale: 90%
    :alt: 트리맵 시각화 옵션 (2) - 범례

.. |opt3| image:: ./images/ko/treemap_06.png
    :scale: 90%
    :alt: 트리맵 시각화 옵션 (3) - 데이터


.. list-table::
   :header-rows: 1

   * - 옵션
     - 설명
   * - |opt1|
     - 데이터 값의 표현여부, 배경색상, 다운로드 및 상세보기 버튼 설정
   * - |opt2|
     - 트리맵에 표시되는 범례의 여부를 설정
   * - |opt3|
     - 트리맵에 표시되는 데이터의 그룹 및 값을 설정. 최초의 실행(Run) 후에 변경 가능

그리고자 하는 트리맵에 맞게 위 옵션들을 수정합니다. 

|

결과 확인
=================================================================

설정을 마친 후 우측 하단의 [실행] 버튼을 클릭하면, 아래 그림과 같이 결과가 표시됩니다.

.. image:: ./images/ko/treemap_07.png
    :alt: 트리맵_시각화 결과 확인


제대로 적용됐는지 확인하고자 한다면, 우측 상단의 [보기] 버튼 (주황색 상자로 표시)을 눌러 작성 결과를 다시 한 번 확인합니다.

|

미리 보기
=================================================================

.. image:: ./images/ko/treemap_08.png
    :alt: 트리맵_시각화 결과 [보기]에서 확인

결과가 정상적으로 표출될 경우, 작성 화면에서 [저장] 버튼을 눌러 결과를 저장합니다.

|

-------------------------------------------------------------------
주의사항
-------------------------------------------------------------------

.. code::

    [Notice 1] [보기] 버튼을 눌렀을 때, 차트가 자동으로 실행되지 않을 경우

    차트의 경우, "자동 실행"을 설정하지 않을 경우 보고서 조회 시 자동으로 실행되지 않습니다.

    [데이터] 탭 하단의 [데이터 실행방법 설정]에 있는 "자동 실행"을 선택한 후 다시 확인해보시기 바랍니다.
    (아래 그림 참조)

.. image:: ./images/ko/autoplay.png
    :scale: 90%
    :alt: 자동실행 설정

.. code::

    [Notice 02] "그룹"과 "값" 드롭다운 메뉴에 아무 컬럼도 표시되지 않을 경우, 아래 절차를 진행하시기 바랍니다.

    1) 데이터 설정에 오류가 있는지 확인합니다.
    2) 데이터 설정에 문제가 없다면, 우측 하단의 [실행] 버튼을 클릭한 후 다시 확인하시기 바랍니다.
