# Skills

Codex 등 AI 에이전트에서 사용하는 개인 스킬 모음 저장소입니다.  
모든 스킬은 `skills/<스킬명>` 구조로 관리하며, 앞으로 새로운 스킬도 이 저장소에 계속 추가합니다.

## 스킬 목록

| 스킬 | 호출명 | 용도 |
|---|---|---|
| [pdftomd](skills/pdftomd) | `$pdftomd` | 원문 구조와 의미를 보존해 PDF를 주제별 Markdown·Obsidian 노트로 변환·검수 |
| [task-analysis](skills/task-analysis) | `$task-analysis` / `/작업분석` | 업무 폴더·자료를 분석해 근거 있는 우선순위별 할 일 정리 및 업무일지 작성 |
| [task-execution](skills/task-execution) | `$task-execution` / `/작업처리` | 확정한 업무를 실행·검증하고 같은 업무일지 갱신 |

## 설치

### 전체 스킬 한 번에 설치

새 PC의 Codex에 아래 문장을 입력하세요.

```text
$skill-installer https://github.com/myflair77/Skills 저장소에서 skills/pdftomd, skills/task-analysis, skills/task-execution 세 경로의 스킬을 모두 설치해 줘.
```

### 특정 스킬만 개별 설치

원하는 스킬 경로만 지정해 설치할 수도 있습니다. (예: `pdftomd`)

```text
$skill-installer https://github.com/myflair77/Skills/tree/main/skills/pdftomd 에 있는 스킬을 설치해 줘.
```

설치 후 다음 대화 차례부터 바로 사용할 수 있으며, 목록에 나타나지 않으면 Codex를 다시 시작하세요.

## 스킬별 안내

### `pdftomd`

PDF를 요약하지 않고 원문 구조와 의미를 보존한 주제별 Markdown·Obsidian 노트로 변환하고 검수하는 스킬입니다.

```text
$pdftomd 이 PDF를 조사하고 분할 방식과 시범 변환을 준비해 줘: <PDF 경로>
```

- 목차 기준 분할 또는 분량 균형 분할을 선택하고 시범 결과를 확인한 뒤 전체 변환을 진행합니다.
- 실제 작업에는 PDF 읽기·렌더링과 파일 작성이 가능한 실행 환경이 필요합니다. (이 저장소는 관련 프로그램을 자동 설치하지 않습니다.)
- 사용 중 생성되는 `data/recommendation-history.jsonl`은 설치된 스킬 폴더의 개인 데이터이며 Git에서 제외합니다.

### `task-analysis` & `task-execution` (작업분석 / 작업처리)

업무 폴더의 요청·마감·현황을 분석하고(`task-analysis`), 확정된 실제 업무를 처리·검증(`task-execution`)하며 동일한 Obsidian 업무일지를 함께 관리하는 스킬입니다.

```text
$task-analysis 이 업무 폴더의 요청과 마감을 정리해 줘: <폴더 경로>
$task-execution 방금 정리한 목록으로 답변서를 작성하고 같은 업무일지를 갱신해 줘.
```

- 처음 사용할 때 현재 PC의 업무일지 폴더, 템플릿 파일, 부서 약칭을 함께 알려주면 두 스킬이 같은 노트를 사용합니다.
- 별도 설정 없이도 작업 폴더만 지정해 바로 시작할 수 있습니다.

## 배포 범위와 업데이트

- 이 저장소에는 각 스킬의 지침 파일(`SKILL.md`, `agents/openai.yaml`, `references/` 등)만 포함하며, 개인 문서·PDF·변환 노트·이미지·추천 이력 등 개인 데이터는 포함하지 않습니다.
- GitHub에 변경 사항을 올려도 이미 설치한 스킬이 자동으로 업데이트되지는 않습니다. 업데이트 시 개인 `data/` 폴더를 보존하고 지침 파일만 교체하세요.
