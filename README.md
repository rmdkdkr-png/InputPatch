<div align="center">

# 🎮 InputPatch

**네오지오 포켓 컬러 격투게임의 「손맛」 패치 모음** — 발동 프레임·후경직 같은 **입력 체감**을 고치는 IPS.

한글패치([KrPatch](https://github.com/rmdkdkr-png/KrPatch))가 *글*을 고친다면, 여기는 *손*을 고칩니다.
[**PocketCore 앱**](https://github.com/rmdkdkr-png/PocketCore/releases/tag/app)이면 「업데이트 확인」 한 번 → 설정 토글 한 번으로 켜집니다.

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/svc_kyo_hp_orig_vs_fastcd.png" alt="SvC 쿄 강펀 원본 vs FastCD" width="900">

</div>

## 왜 필요한가 — 이 기종의 입력 손해

네오지오 포켓은 버튼이 A·B 둘뿐이라 **강공격을 「길게 누르면 강」**으로 가릅니다. 그래서 강 기본기는 버튼을 누른 뒤
**게임이 "길게 누르나 보자"며 기다리는 6~8프레임**을 통째로 더 먹습니다. 아케이드 원작은 강이 별도 버튼이라 안 내는
손해입니다. 여기 패치들은 **그 손해만큼만** 돌려주고, 누르는 길이로 약/강을 가르는 방식·대미지·판정은 그대로 둡니다.

| 게임 | 패치 | 판 | IPS md5 | |
|---|---|---|---|---|
| 정상결전 최강 파이터즈 | 빠른 기본기 (FastCD) | v1.3 | `148ae0966230` | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/download/mods/svc_fastcd_v1.3.ips) |
| 더 킹 오브 파이터즈 R-2 | 빠른 기본기 (FastCD) | v1.1 | `47df4b49e1ce` | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/download/mods/kofr2_fastcd_v1.1.ips) |
| 사무라이 스피리츠! 2 | 평타 콤보 — 보통 [검수용] | t3 | `af6c3ed6bd2b` | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/download/mods/ss2_combo_t3.ips) |
| 사무라이 스피리츠! 2 | 평타 콤보 — 넉넉 [검수용] | t1 | `7a2c9c38fb77` | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/download/mods/ss2_combo_t1.ips) |

## 빠른 기본기 — FastCD (SvC · KOF R-2)

서서 강펀·강킥 중 **유독 늘어진 기술**의 발동을 애니메이션 대본(WAIT 틱)에서 당깁니다.
규칙은 유저가 직접 정했습니다 — **강은 같은 캐릭터의 약보다 반드시 느리게(묵직)**, **캐릭터별 차이는 보존**, **원본이 이미
빠르면 손대지 않음**. SvC 는 약+4, KOF R-2 는 원본 중앙값을 따라 펀치 +4 · 킥 +6.

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/svc_kyo_hp_orig_vs_fastcd.png" alt="SvC 쿄 강펀 원본 vs FastCD" width="900">

*SvC 쿄 서서 강펀 — 위: 원본(누름→판정 14프레임), 아래: FastCD(8프레임). 2프레임 간격 필름.*

- SvC v1.3: 16기술 단축(하오마루 강펀 26→18, 레오나 강킥 18→10, 쿄 강펀 14→8·강킥 14→12 …), 22바이트.
- KOF R-2 v1.1: 8기술 단축(쿄 강펀 16→10, 레오나 강킥 20→14, 셰르미 강펀 16→12 …), 11바이트 — 이식소 제작.
- 검증: 전 기술 에뮬레이터 실측(패치 후 재측정) — 발동 프레임·피해·동작 흐름·**강<약 역전 없음** 확인.

## 평타 콤보 — SS2 (검수용 실증판)

사무라이 스피리츠! 2 는 **카운터가 아니면 평타 콤보가 안 들어갑니다** — 강베기 후경직(34f)이 상대 경직(36f)과 거의 같아서.
아수라 서서 강베기의 **회복 셀 틱을 7→3(−8f)** 으로 줄이면 「강베기 → 살짝 전진 → 강베기」가 상대가 경직에서 못 나온 채
2타로 들어갑니다(실측: 2타 명중 + 상대 중립 복귀 없음). 아직 **캐릭터 1명·기술 1개**짜리 실증이라 `[검수용]` 입니다.

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/ss2_asura_combo_orig_vs_t3.png" alt="SS2 아수라 콤보 원본 vs t3" width="900">

*아수라 강베기→강베기 — 위: 원본(2타 전에 상대가 풀림), 아래: t3(2타가 경직 중 명중). 4프레임 간격 필름.*

## PocketCore 에서 쓰기

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/app_launcher.png" alt="app_launcher.png" width="300"> <img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/app_settings_ss2_ingame.png" alt="app_settings_ss2_ingame.png" width="300"> <img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/app_settings_svc_ingame.png" alt="app_settings_svc_ingame.png" width="300">

1. 롬 목록 화면 **「업데이트 확인」** — 이 저장소의 색인(`mods.json`)과 IPS 를 받습니다.
2. **설정** — 게임 안에서 열면 그 게임 것만, 런처에서 열면 게임별로 묶여 보입니다. 토글을 켭니다.
3. 게임을 다시 열면 **원본은 그대로 두고 사본**(`PocketCore/.patched/`)에 한글패치 위로 얹혀 실행됩니다.

직접 입히려면 IPS 를 순정 롬(또는 한글패치 롬 — 겹치는 바이트가 없어 어느 쪽이든)에 Lunar IPS 등으로 적용하세요.

## 어떻게 찾았나

- 프레임은 램이 아니라 **롬의 애니메이션 대본**이 정합니다. SVC·KOF 는 `00 03 NN`(WAIT NN틱, 1틱=2프레임) 문법,
  SS2 는 다른 엔진 — 4바이트 레코드 `[틱][플래그][셀][00]` 에 램 틱 카운트다운.
- 문법 추측·커서 역산은 자주 샙니다. 최종 판정은 늘 **패치 → 재측정**: 후보 바이트를 하나씩 −1 해 보고 「정확히
  2프레임 줄고 피해·동작이 그대로」인 것만 다이얼로 채택합니다.
- 상세 실측표·방법론은 [thinkbox](https://github.com/rmdkdkr-png/thinkbox) 의 `knowledge/` 에 있습니다.

## 저작권 · 책임

게임과 그 그림·음악·이름의 권리는 **SNK 등 원 권리자**의 것입니다. 비영리 팬 패치이며 **롬을 배포하지 않습니다**(차분만).
있는 그대로 제공되며 사용에 따른 문제의 책임은 사용자에게 있습니다. 권리자 요청 시 즉시 내립니다.
