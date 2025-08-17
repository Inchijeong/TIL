# MCP Server
## MCP Server 만들기

1. https://docs.astral.sh/uv/getting-started/installation/ 들어가서 uv설치
	1. ![[Pasted image 20250707212209.png]]
	2. `curl -LsSf https://astral.sh/uv/install.sh | sh`
	3. 맥 사용자의 경우 brew 사용하는게 좋음. (전역으로 설치가 안될 경우 brew 이용합시다)
2. `uv init test-mcp` - 프로젝트를 생성
3. `cd test-mcp` - 생성한 프로젝트로 이동
4. `uv venv` - 가상 환경 설정
5. `source .venv/bin/activate` - 가상 환경 활성화
6. `uv add "mcp[cli]"` - mcp패키지 설치(cli옵션- cli도구 추가 옵션 추가)
7. `brew install node` - 노드 설치
8. `mcp dev server.py` - mcp 개발 모드 실행. 서버 이름은 현재 패키지에 있는 서버 파일 이름.
9. http://localhost:6274 접속
10. connect해서 resource, tool, prompt를 확인 및 테스트 할 수 있음



출처: [https://bcho.tistory.com/1471](https://bcho.tistory.com/1471) [조대협의 블로그:티스토리]

* 날씨 MCP 빠르게 만들어 볼 수 있음
	* https://bcho.tistory.com/1471
* Troubleshooting 포함
	* https://modulabs.co.kr/community/momos/8/feeds/653
* 파일 시스템
	* https://chinensis.tistory.com/entry/%EC%B4%88%EB%B3%B4%EC%9E%90%EB%A5%BC-%EC%9C%84%ED%95%9C-MCP-%EC%84%9C%EB%B2%84-%EC%82%AC%EC%9A%A9-%EA%B0%80%EC%9D%B4%EB%93%9C-%ED%81%B4%EB%A1%9C%EB%93%9C%EA%B0%80-%EB%82%B4-%EA%B0%9C%EC%9D%B8-%ED%8C%8C%EC%9D%BC%EA%B3%BC-%EC%9C%A0%ED%8A%9C%EB%B8%8C-%EC%98%81%EC%83%81%EC%9D%84-%EB%B6%84%EC%84%9D%ED%95%A0-%EC%88%98-%EC%9E%88%EA%B2%8C-%ED%95%B4%EB%B3%B4%EC%9E%90
* 개념부터 네이버 MCP
	* https://dytis.tistory.com/112

