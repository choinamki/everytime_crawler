# everytime_crawler
에브리타임(https://everytime.kr) 크롤러입니다.
아이디 비밀번호를 입력하면 게시판을 수집하여 json 파일로 저장해줍니다.
에브리타임 게시판의 워드 클라우드를 만들어서 보고자 만들었습니다.
사용하기 위해서는 크롬드라이버와 워드클라우드에 한글을 표시할 수 있는 폰트가 필요합니다.
현재 제작중입니다.


# infomation
해당하는 코드를 작동하면

1. 수집한 자유게시판의 접속 링크를 현재 디렉토리에 everytime_link.txt 로 저장합니다.

2. 저장한 자유게시판의 접속 링크와 자유게시판 url 을 더해서 각각의 게시글의 접속합니다.

3. 게시글에 접속하여 

  json_data['title'] = title                     글 제목
  json_data['text'] = text                       글 내용
  json_data['tex_time'] = text_time              글 작성 시간
  json_data['now_time'] = str(time_now)          글 수집 시간
        
  json_data['comment_text'] = comment_text       댓글 내용
  json_data['comment_time'] = comment_time       댓글 시간

  을 저장하여 현재 디렉토리 안 Result 디렉토리에 test + 숫자.txt 형태로 저장합니다.

4. 저장한 json 파일의 텍스트 정보를 불러와서 하나의 str 로 만든 뒤 워드클라우드를 만듭니다.


사용한 웹 드라이버는 크롬드라이버(http://chromedriver.chromium.org/downloads)
워드클라우드에 사용한 폰트는 나눔고딕(https://hangeul.naver.com/font)
단어 빈도수 분석을 위해서 KR-WordRank(https://github.com/lovit/KR-WordRank) 입니다.
