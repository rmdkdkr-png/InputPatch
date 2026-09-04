<div align="center">

# 🎮 InputPatch

**네오지오 포켓 컬러 격투게임의 「손맛」 패치 모음** — 발동 프레임·후경직 같은 **입력 체감**을 고치는 IPS.

한글패치([KrPatch](https://github.com/rmdkdkr-png/KrPatch))가 *글*을 고친다면, 여기는 *손*을 고칩니다. IPS 차분만 배포하며 롬은 없습니다.

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/svc_kyo_hp_orig_vs_fastcd.png" alt="SvC 쿄 강펀 — 같은 프레임의 원본 vs FastCD" width="900">

</div>

## 목록

| 게임 | 패치 | 판 | |
|---|---|---|---|
| 정상결전 최강 파이터즈 | 빠른 기본기 (FastCD) | v1.5 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/tag/svc-fastcd) |
| 사무라이 스피리츠! 2 | 평타 콤보 — 보통 [검수용] | t3 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/tag/ss2-combo) |
| 사무라이 스피리츠! 2 | 평타 콤보 — 넉넉 [검수용] | t1 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/tag/ss2-combo) |
| 더 킹 오브 파이터즈 R-2 | 빠른 기본기 (FastCD) | v1.2 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/tag/kofr2-fastcd) |
| 더 킹 오브 파이터즈 R-2 | 빠른 강펀 — −2 | v1.0 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/tag/kofr2-fastpunch) |
| 더 킹 오브 파이터즈 R-2 | 빠른 강펀 — −4 | v1.0 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/tag/kofr2-fastpunch) |
| 더 킹 오브 파이터즈 R-2 | 빠른 강펀 — −6 | v1.0 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/tag/kofr2-fastpunch) |
| 더 킹 오브 파이터즈 R-2 | 빠른 강펀 — −8 | v1.0 | [받기](https://github.com/rmdkdkr-png/InputPatch/releases/tag/kofr2-fastpunch) |

md5·크기는 [릴리즈 `mods`](https://github.com/rmdkdkr-png/InputPatch/releases/tag/mods) 의 `mods.json` 에 있습니다.

## 적용법

1. 위 표에서 IPS 를 받습니다. 대상 롬은 **순정 롬**이든 **이미 한글패치한 롬**이든 됩니다 — 한글패치와 겹치는 바이트가 없어 순서도 무관합니다.
2. 패치 도구로 IPS 를 롬에 적용합니다.
   - PC: [Floating IPS](https://www.romhacking.net/utilities/1040/) 또는 [Lunar IPS](https://www.romhacking.net/utilities/240/)
   - 웹(설치 없음): [ROM Patcher JS](https://www.marcrobledo.com/RomPatcher.js/) — 롬과 IPS 를 고르면 결과 파일을 내려줍니다
   - 안드로이드: UniPatcher (Play 스토어)
3. 결과 롬을 에뮬레이터나 카트에 넣습니다. 확장자(.ngc)는 그대로.
4. 되돌리기 = 원본 롬을 다시 쓰면 됩니다. 한글패치와 인풋패치를 둘 다 원하면 **한글패치 IPS → 인풋패치 IPS** 순으로 두 번 적용하세요.

주의: 같은 게임의 패치 두 개가 **같은 바이트**를 고치는 경우(사무라이 스피리츠! 2 「보통」·「넉넉」)는 하나만 고르세요.
받은 IPS 가 최신인지는 릴리즈의 md5 로 확인합니다(IPS 파일 자체의 md5 — 결과 롬 해시는 원본 덤프 종류마다 달라서 적지 않습니다).

## 왜 필요한가

네오지오 포켓은 버튼이 A·B 둘뿐이라 **길게 누르면 강**입니다. 게임은 버튼을 8프레임 눌러 본 뒤에야 강 모션을 시작하고
(쿄: 누른 뒤 8프레임째), 거기에 기술 자체의 발동이 붙습니다. 그래서 쿄 서서 강펀은 격겜 관례의 스타트업으로 **17프레임**
(아케이드 KOF'98 쿄 원거리 강펀 12), 버튼을 누른 순간부터 재면 **24프레임**, 하오마루는 35프레임입니다. 여기 패치들은 모션
쪽에서 홀드 판정이 먹는 몫(6~8프레임)만 돌려주고, 누르는 길이로 약/강을 가르는 방식·판정 상자·대미지·약공격은 그대로 둡니다.
홀드 문턱 자체를 낮추는 입력 쪽 롬 수정도 시험했지만 약/강 구분이 무너져 접었습니다.

## 빠른 기본기 — FastCD (SvC · KOF R-2)

서서 강펀·강킥 중 **유독 늘어진 기술**의 발동을 애니메이션 대본에서 당깁니다. 규칙: **강은 약보다 반드시 느리게(묵직)**,
캐릭터별 차이 보존, 원본이 이미 빠르면 손대지 않음. 여백은 두 게임 다 **펀치 +4 · 킥 +6**(원본 약→강 차이의 중앙값).

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/kof_kyo_hp_orig_vs_fastcd.png" alt="KOF R-2 쿄 강펀 — 같은 프레임의 원본 vs FastCD v1.1" width="900">

- SvC v1.4 — 11기술, 16바이트. **누름→명중(순정 2버튼 홀드, 버튼이 눌린 첫 프레임 → 맞는 프레임, 에뮬 실측, 위상에 따라 ±1)**: 강펀 쿄 24→18 · 하오마루 35→27 · 나코루루 24→20 · 장기에프 22→18 · 모리간 22→18 · 이오리 22→18 / 강킥 레오나 28→22 · 하오마루 27→21 · 나코루루 30→26 · 셰르미 24→22 · 야시로 22→20. 나머지는 원본 그대로, 약공격은 손대지 않음. 격겜 관례의 **스타트업(모션 첫 프레임을 1로 세어 첫 판정까지)**으로는 쿄 강펀 **17 → 11**, 약펀 7.
- KOF R-2 v1.1 — 8기술, 11바이트. 같은 잣대로 쿄 강펀 누름→명중 **23 → 17**, 스타트업 17 → 11. 나머지 7기술도 각 6프레임 단축.
- 전 기술 에뮬레이터 실측(패치 후 재측정): 발동·피해·동작 흐름·강<약 역전 없음 확인.

## 평타 콤보 — SS2 (검수용)

사무라이 스피리츠! 2 는 **카운터가 아니면 평타 콤보가 안 들어갑니다** — 약베기(B 탭) 후경직이 상대 경직과 거의 같아서.
아수라 서서 약베기의 회복 틱을 **7→3(−8프레임)** 으로 줄이면 「약베기 → 살짝 전진 → 약베기」가 2타로 들어갑니다.
아직 **캐릭터 1명·기술 1개** 실증이라 `[검수용]` 입니다.

<img src="https://raw.githubusercontent.com/rmdkdkr-png/InputPatch/main/docs/img/ss2_asura_combo_orig_vs_t3.png" alt="SS2 아수라 약베기 콤보 — 2타 시점의 원본 vs t3" width="900">

## 더 보기

프레임은 램이 아니라 **롬의 애니메이션 대본**이 정합니다. 찾는 법·실측표는 [thinkbox](https://github.com/rmdkdkr-png/thinkbox) 의 `knowledge/` 에.

## 저작권 · 책임

게임과 그 그림·음악·이름의 권리는 **SNK 등 원 권리자**의 것입니다. 비영리 팬 패치이며 **롬을 배포하지 않습니다**(차분만).
있는 그대로 제공되며 사용에 따른 문제의 책임은 사용자에게 있습니다. 권리자 요청 시 즉시 내립니다.
