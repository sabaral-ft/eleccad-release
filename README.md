# eleccad-release

전기캐드(GstarCAD · AutoCAD 플러그인)의 **자동 업데이트 배포 자리**입니다.

> 여기는 **프로그램이 스스로 확인하는 곳**입니다. 사람이 받아 쓰는 곳이 아닙니다.
> 설치 파일과 안내는 블로그를 보십시오.

## 어떻게 도나

1. 캐드를 켜면 프로그램이 잠시 뒤(백그라운드로) 아래 주소를 읽습니다.

   ```
   https://github.com/sabaral-ft/eleccad-release/releases/latest/download/manifest.txt
   ```

   이 주소는 **새 판을 올려도 바뀌지 않습니다**(`latest` 가 늘 최신 릴리스를 가리킵니다).

2. `manifest.txt` 의 `sha256` 이 지금 쓰는 파일과 다르면 새 판을 받습니다.
3. 받은 파일은 **SHA256 검사를 통과해야만** 씁니다. 한 바이트라도 다르면 버립니다.
4. 돌고 있는 프로그램 파일은 잠겨 있어 그때는 못 바꿉니다.
   그래서 옆에 `.new` 로 두었다가 **다음에 캐드를 켤 때** 바꿔 끼웁니다.
5. 옛 판은 `.bak` 으로 남습니다. 새 판이 제대로 안 올라오면 **그것으로 되돌립니다.**

## 쓰는 분이 알아 두실 것

- **동의하지 않으면 인터넷을 전혀 쓰지 않습니다.** 설치할 때 물어보고, 그 답만 따릅니다.
- 확인은 **하루에 한 번**입니다. 캐드를 켤 때마다 통신하지 않습니다.
- 통신이 안 되거나 막혀도 **캐드는 그대로 뜹니다.** 조용히 넘어가고 다음에 다시 해 봅니다.
- 끄고 싶으시면 설치 파일(`설치.bat`)을 다시 실행하고 **아니요**를 고르시면 됩니다.

## manifest.txt 형식

키=값 한 줄씩입니다. `#` 로 시작하는 줄은 주석입니다.

```
schema=1
built=2026-09-13 18:52
gstar.version=...
gstar.sha256=...
gstar.size=...
gstar.url=https://github.com/sabaral-ft/eleccad-release/releases/latest/download/EleccadGstar.dll
acad.version=...
acad.sha256=...
acad.size=...
acad.url=https://github.com/sabaral-ft/eleccad-release/releases/latest/download/EleccadAcad.dll
```

이 파일은 **출고할 때 자동으로 만들어집니다.** 손으로 고치지 마십시오.

## 소스 코드

이 저장소에는 **소스가 들어 있지 않습니다.** 배포용 파일만 올라갑니다.
