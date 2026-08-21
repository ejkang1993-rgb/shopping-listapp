# shopping-listapp

간단한 물품 체크리스트(쇼핑 리스트) 웹앱입니다. 순수 HTML/CSS/JavaScript로 만들어졌으며, 데이터는 [Supabase](https://supabase.com) 데이터베이스(`shopping_items` 테이블)에 저장됩니다.

## 기능
- 물품 추가
- 완료 체크 표시
- 항목 삭제
- 총 개수 / 완료 개수 표시
- Supabase를 통한 데이터 저장 (여러 기기/브라우저에서 동일한 목록 공유)

## 사용법
`index.html` 파일을 브라우저에서 열면 바로 사용할 수 있습니다. (인터넷 연결 필요)

## 데이터베이스 구조
Supabase `shopping_items` 테이블:

| 컬럼 | 타입 | 설명 |
| --- | --- | --- |
| id | uuid (PK) | 기본 키, 자동 생성 |
| name | text | 물품 이름 |
| checked | boolean | 완료 여부 (기본값 false) |
| created_at | timestamptz | 생성 시각 (기본값 now()) |

Row Level Security(RLS)가 활성화되어 있으며, 별도 로그인 없이 사용하는 공개 데모 앱 특성상 익명(anon) 역할에 대해 select/insert/update/delete를 모두 허용하는 정책이 적용되어 있습니다.
