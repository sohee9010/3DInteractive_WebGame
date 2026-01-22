# Requirements Document

## Introduction

이 기능은 게임에 충돌 감지 시스템과 게임 오버 화면을 추가하는 것입니다. 플레이어가 장애물에 부딪히면 즉시 게임이 종료되고, ending.html의 스타일을 참고한 게임 오버 화면이 표시됩니다.

## Requirements

### Requirement 1

**User Story:** 플레이어로서, 장애물에 부딪혔을 때 게임이 즉시 종료되어 게임의 긴장감을 느끼고 싶습니다.

#### Acceptance Criteria

1. WHEN 플레이어가 bush 장애물에 충돌 THEN 시스템 SHALL 즉시 게임을 일시정지하고 게임 오버 상태로 전환
2. WHEN 플레이어가 stylized_tree 장애물에 충돌 THEN 시스템 SHALL 즉시 게임을 일시정지하고 게임 오버 상태로 전환  
3. WHEN 플레이어가 person 장애물에 충돌 THEN 시스템 SHALL 즉시 게임을 일시정지하고 게임 오버 상태로 전환
4. WHEN 플레이어가 hole 장애물에 충돌하고 토끼가 아닌 상태 THEN 시스템 SHALL 즉시 게임을 일시정지하고 게임 오버 상태로 전환
5. WHEN 플레이어가 rock 장애물에 충돌하고 뱀이 아닌 상태 THEN 시스템 SHALL 즉시 게임을 일시정지하고 게임 오버 상태로 전환

### Requirement 2

**User Story:** 플레이어로서, 게임 오버 시 명확하고 일관된 UI를 통해 상황을 이해하고 다음 행동을 선택하고 싶습니다.

#### Acceptance Criteria

1. WHEN 게임 오버가 발생 THEN 시스템 SHALL ending.html과 동일한 스타일의 오버레이 화면을 표시
2. WHEN 게임 오버 화면이 표시 THEN 시스템 SHALL "Game Over" 텍스트를 ending.html과 동일한 폰트와 스타일로 표시
3. WHEN 게임 오버 화면이 표시 THEN 시스템 SHALL "🔄 다시 플레이" 버튼을 ending.html과 동일한 스타일로 제공
4. WHEN 게임 오버 화면이 표시 THEN 시스템 SHALL "🏠 타이틀로 돌아가기" 버튼을 ending.html과 동일한 스타일로 제공

### Requirement 3

**User Story:** 플레이어로서, 게임 오버 후 쉽게 재시작하거나 메인 메뉴로 돌아갈 수 있어야 합니다.

#### Acceptance Criteria

1. WHEN "다시 플레이" 버튼을 클릭 THEN 시스템 SHALL 게임을 초기 상태로 리셋하고 새 게임을 시작
2. WHEN "타이틀로 돌아가기" 버튼을 클릭 THEN 시스템 SHALL start.html 페이지로 이동
3. WHEN 게임 오버 화면에서 버튼 클릭 THEN 시스템 SHALL ending.html과 동일한 클릭 사운드 효과를 재생

### Requirement 4

**User Story:** 플레이어로서, 동물의 특수 능력이 적절히 작동하여 해당 장애물을 피할 수 있어야 합니다.

#### Acceptance Criteria

1. WHEN 토끼 상태에서 hole 장애물에 점프로 접근 THEN 시스템 SHALL 충돌을 무시하고 게임을 계속 진행
2. WHEN 뱀 상태에서 독으로 부식된 rock 장애물에 접근 THEN 시스템 SHALL 충돌을 무시하고 게임을 계속 진행
3. WHEN 코끼리 상태에서 박치기로 파괴된 stylized_tree 장애물에 접근 THEN 시스템 SHALL 충돌을 무시하고 게임을 계속 진행
4. WHEN 호랑이 상태에서 어흥으로 도망간 person 장애물에 접근 THEN 시스템 SHALL 충돌을 무시하고 게임을 계속 진행