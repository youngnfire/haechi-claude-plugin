# haechi-handoff

Claude Code(Claude 앱의 Code 탭 또는 터미널)에서 하던 작업을 해치가 이어 받게 하는 플러그인입니다.

스킬을 부르면 Claude가 지금 대화와 작업 폴더를 정리해 작업 폴더에 인계 문서 `.haechi/handoff.md`를 씁니다. 해치 앱에서 「로컬 작업 가져오기」를 하면 해치가 그 문서를 읽고 이어서 일합니다.

인계 문서에는 목표, 끝난 것, 하던 것과 멈춘 자리, 다음 할 일, 관련 파일, 정한 것과 이유, 돌리던 명령, 확인하지 못한 것이 들어갑니다. 비밀(키·토큰·비밀번호)은 값 대신 이름만 적습니다.

## 설치

Claude Code 세션 안에서 한 줄로:

```
/plugin install haechi-handoff --marketplace youngnfire/haechi-claude-plugin
```

두 단계로 해도 됩니다:

```
/plugin marketplace add youngnfire/haechi-claude-plugin
/plugin install haechi-handoff@haechi-plugins
```

## 쓰는 법

1. 해치 대화의 「작업 위치」와 같은 폴더에서 Claude Code를 엽니다.
2. `/haechi-handoff`를 부르거나 「해치에게 넘겨줘」라고 말합니다.
3. 해치 앱에서 그 폴더가 작업 위치인 대화를 열고 「로컬 작업 가져오기」를 합니다.

## 개인정보

- 인계 문서는 내 컴퓨터의 작업 폴더에만 생깁니다. 플러그인은 어디로도 보내지 않습니다.
- `.haechi/` 폴더에는 `*` 한 줄짜리 `.gitignore`가 함께 생겨 git 저장소에 커밋되지 않습니다.
- 해치는 사용자가 「로컬 작업 가져오기」를 할 때만 그 파일을 읽습니다.
- 스킬은 `.haechi/handoff.md`와 `.haechi/.gitignore` 말고는 아무것도 쓰거나 실행하지 않도록 지시합니다. 파일 쓰기 허락은 평소처럼 Claude Code가 묻습니다.

## English

A Claude Code plugin that hands your current work over to Haechi. Run `/haechi-handoff` (or say "해치에게 넘겨줘") and Claude writes a handoff note to `.haechi/handoff.md` in the working folder, with keys and passwords named but never copied. Then use "로컬 작업 가져오기" (Import local work) in the Haechi app, in a conversation whose working folder is the same folder.

Install: `/plugin install haechi-handoff --marketplace youngnfire/haechi-claude-plugin`, or `/plugin marketplace add youngnfire/haechi-claude-plugin` then `/plugin install haechi-handoff@haechi-plugins`.

The note stays on your machine; `.haechi/` gets its own `.gitignore` so it is never committed, and Haechi reads it only when you ask it to.

## License

MIT
