<div align="center">

# 🎮 InputPatch

**네오지오 포켓 컬러 격투게임의 「손맛」 패치 모음** — 발동 프레임·후경직 같은 **입력 체감**을 고치는 IPS.

한글패치([KrPatch](https://github.com/rmdkdkr-png/KrPatch))가 *글*을 고친다면, 여기는 *손*을 고칩니다.
[**PocketCore 앱**](https://github.com/rmdkdkr-png/PocketCore/releases/tag/app)이면 「업데이트 확인」 한 번 → 설정 토글 한 번.

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/svc_kyo_hp_orig_vs_fastcd.webp" alt="SvC 쿄 강펀 원본 vs FastCD">

*SvC 쿄 서서 강펀 — 왼쪽 원본(판정 f14) · 오른쪽 FastCD(f08). 1/5 속도, HIT 는 판정이 나오는 프레임.*

</div>

## 목록

| 게임 | 패치 | 판 | |
|---|---|---|---|
| 정상결전 최강 파이터즈 | 빠른 기본기 (FastCD) | v1.4 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/download/mods/svc_fastcd_v1.4.ips) |
| 더 킹 오브 파이터즈 R-2 | 빠른 기본기 (FastCD) | v1.1 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/download/mods/kofr2_fastcd_v1.1.ips) |
| 사무라이 스피리츠! 2 | 평타 콤보 — 보통 [검수용] | t3 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/download/mods/ss2_combo_t3.ips) |
| 사무라이 스피리츠! 2 | 평타 콤보 — 넉넉 [검수용] | t1 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/download/mods/ss2_combo_t1.ips) |

md5·크기는 [릴리즈 `mods`](https://github.com/rmdkdkr-png/InputPatch/releases/tag/mods) 의 `mods.json` 에 있습니다.

## 왜 필요한가

네오지오 포켓은 버튼이 A·B 둘뿐이라 **길게 누르면 강**입니다. 그래서 강 기본기는 게임이 「길게 누르나 보자」며
기다리는 **6~8프레임**을 통째로 더 먹습니다 — 아케이드 원작엔 없는 손해. 여기 패치들은 **그 손해만큼만** 돌려주고,
누르는 길이로 약/강을 가르는 방식·대미지·판정은 그대로 둡니다.

## 빠른 기본기 — FastCD (SvC · KOF R-2)

서서 강펀·강킥 중 **유독 늘어진 기술**의 발동을 애니메이션 대본에서 당깁니다. 규칙: **강은 약보다 반드시 느리게(묵직)**,
캐릭터별 차이 보존, 원본이 이미 빠르면 손대지 않음. 여백은 두 게임 다 **펀치 +4 · 킥 +6**(원본 약→강 차이의 중앙값).

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/kof_kyo_hp_orig_vs_fastcd.webp" alt="KOF R-2 쿄 강펀 원본 vs FastCD v1.1">

*KOF R-2 쿄 서서 강펀 — 왼쪽 원본(f16) · 오른쪽 FastCD v1.1(f10).*

- SvC v1.4 — 11기술(하오마루 강펀 26→18, 레오나 강킥 18→12, 쿄 강펀 14→8 …), 16바이트.
- KOF R-2 v1.1 — 8기술(쿄 강펀 16→10, 레오나 강킥 20→14 …), 11바이트. 이식소 제작.
- 전 기술 에뮬레이터 실측(패치 후 재측정): 발동·피해·동작 흐름·강<약 역전 없음 확인.

## 평타 콤보 — SS2 (검수용)

사무라이 스피리츠! 2 는 **카운터가 아니면 평타 콤보가 안 들어갑니다** — 강베기 후경직이 상대 경직과 거의 같아서.
아수라 서서 강베기의 회복 틱을 **7→3(−8프레임)** 으로 줄이면 「강베기 → 살짝 전진 → 강베기」가 2타로 들어갑니다.
아직 **캐릭터 1명·기술 1개** 실증이라 `[검수용]` 입니다.

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/ss2_asura_combo_orig_vs_t3.webp" alt="SS2 아수라 콤보 원본 vs t3">

*아수라 강베기→강베기 — 왼쪽 원본(2타 전에 상대가 풀림) · 오른쪽 t3(2타가 경직 중 명중). 1/3 속도.*

## PocketCore 에서 쓰기

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/app_launcher.webp" alt="app_launcher.webp" width="240"> <img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/app_settings_svc_ingame.webp" alt="app_settings_svc_ingame.webp" width="240">

1. 롬 목록 화면 **「업데이트 확인」** — 이 저장소의 색인과 IPS 를 받습니다.
2. **설정** — 게임 안에서 열면 그 게임 것만 보입니다. 토글을 켭니다.
3. 게임을 다시 열면 원본은 그대로 두고 **사본**에 한글패치 위로 얹혀 실행됩니다.

직접 입히려면 IPS 를 순정 롬(또는 한글패치 롬 — 겹치는 바이트가 없어 어느 쪽이든)에 Lunar IPS 등으로 적용하세요.

## 더 보기

프레임은 램이 아니라 **롬의 애니메이션 대본**이 정합니다. 찾는 법·실측표는 [thinkbox](https://github.com/rmdkdkr-png/thinkbox) 의 `knowledge/` 에.

## 저작권 · 책임

게임과 그 그림·음악·이름의 권리는 **SNK 등 원 권리자**의 것입니다. 비영리 팬 패치이며 **롬을 배포하지 않습니다**(차분만).
있는 그대로 제공되며 사용에 따른 문제의 책임은 사용자에게 있습니다. 권리자 요청 시 즉시 내립니다.
