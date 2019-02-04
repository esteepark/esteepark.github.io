---
layout: post
title: "mac - MySetting "
excerpt: ""
categories: [dev]
date: 2018-07-01 01:01:01
comments: true
---

##### Basic - subicura님 블로그
[쿠라갓님 블로그 주소](https://subicura.com/2017/11/22/mac-os-development-environment-setup.html)

---

###### 메일 계정 등록
    - esteepark8@gmail.com
    - dmf8icdi@gmail.com
    - qkrgidgml111@gmail.com

###### 앱설치
    - chrome
    - slack
    - kakaotalk
    - atom
    - photoshop
    - illustrator
    - ridi books
    - movist
    - coffee buzz
    - maple mind
    - parallels

###### 런치패드 배열 조정
    - defaults write com.apple.dock springboard-rows -int 13
    - defaults write com.apple.dock springboard-columns -int 17
    - defaults write com.apple.dock ResetLaunchPad -bool TRUE;killall Dock

###### 맥 시스템 설정
    - 미션 컨트롤
        - 스페이스 사용 내역 별로 자동 정렬 체크 해제
    - 트릭패드
        - 탭하여 클릭 선택
        - 클릭 세기 조절
        - 이동 속도 조절
    - 키보드
        - 텍스트 -> 맞춤법 자동 수정 체크 해제
        - 텍스트 -> 자동으로 문장을 대문자로 시작 체크 해제
        - 텍스트 -> 스페이스를 두 번 눌러 마침표 추가 체크 해제
        - 텍스트 -> 터치바 입력 제안 체크 해제
        - 텍스트 -> 스마트 인용 및 대시 사용 체크 해제
    - 손쉬운 사용
        -  마우스와 트릭패드 -> 트릭패드 옵션 -> 세 손가락 드래그 선택
    - 보안 및 개인 정보 보호3
        - 일반 -> 잠자기 화면 보호 ‘즉시’로 변경
    - App store
        - 자동으로 업데이트 확인 체크 해제
    - Dock
        - 크기 조절
        - 왼쪽 정렬
        - 도큐멘트 열 때 탭 사용 : 항상
        - 응용 프로그램 아이콘 속으로 윈도우 최소화 체크

###### 파인더 설정
    - 파인더 실행 - 커맨드+, - 일반 - 새로운 파인더 윈도우 대신 탭에서 열기 - 홈 폴더 지정(파인더 켜면 홈으로 열림)
    - 고급 - 모든 파일 확장자 보기 체크
    - 고급 - 30일 지난 휴지통 지우기
    - 고급 - 이름순 정렬시 폴더 위에 유지
    - 사이드바 - 원하는 것만 선택
    - 다운로드 폴더로 이동 - 커맨드+j - 정렬방식:수정일 - 정렬:이름 - 폰트:11 - 기본값으로 설정

###### xcode 설치
    - gcc, make 설치되어 있지 않기 때문에 command line tool이 필요하나 xcode는 용량이 크므로 ! 명령어 도구만 설치 !
        - xcode-select —install
        - 설치 확인: gcc
            - clang: error: no input files
###### home-brew 설치
    - https://brew.sh
    - 설치 확인
        - brew doctor
            - your system is ready to brew.
###### git 설치
    - brew install git git-lfs
    - git config --global user.name "Your Name"
    - git config --global user.email "you@your-domain.com"
    - git config --global core.precomposeunicode true
    - git config --global core.quotepath false

###### item 설치
    - brew cask install iterm2
    - iterm 테마: https://iterm2colorschemes.com
        - Dracula
    - iterm2 실행 - 커멘드+i - 컬러 - 컬러프리셋 - 임포트
    - item 실행 - 커멘드+, - 프로파일 - 컬러탭  - 추가한 테마 선택
    - item 환경설정 - appearance - thema: dark
    - item 환경설정 - appearance -window - hide scrollbars - 체크
    - item 환경설정 - appearance - window - show line under title bar when the tab bar is not visible - 체크해제 (타이틀바 밑 1라인)
    - item 환경설정 - appearance - advanced - height of top and bottom margins in terminal panes: 11
    - item 환경설정 - appearance - advanced - width of left and right margins in terminal panes: 13

###### zsh 설치
    - brew install zsh zsh-completions

###### oh-my-zsh설치
    - sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
    - chsh
    - #+
    - Shell: /bin/zsh
###### zsh 플러그인
    - 명령어 하이라이팅: zsh-syntax-highlighting
        - git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    - 자동완성 플러그인: zsh-autosuggestions
        - git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
    - vi ~/.zshrc
        - #+
        - plugins=( 
            git 
            zsh-syntax-highlighting 
            zsh-autosuggestions 
            )

    - 다양한 플러그인: https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins

###### oh-my-zsh 테마
    - https://github.com/robbyrussell/oh-my-zsh/wiki/Themes
        - sarin
        - kolo
        - theunraveler
        - avid
        - af-magic
    - pure 테마 : https://github.com/sindresorhus/pure
        - brew install nodejs
        - npm install --global pure-prompt
        - vi .zshrc
            - #+
            - ZSH_THEME=“refined” #pure 테마 이름 변경됨

###### vim 설치 -> neovim : 24bit true color 지원, 오래된 vim  소스 재코딩
    - brew install neovim
    - vi .zshrc
        - #+
        - alias v="nvim"
        - alias vi="nvim"
        - alias vim="nvim"
        - alias vimdiff="nvim -d"
        - export EDITOR=/usr/local/bin/nvim
    - 홈페이지: https://neovim.io

###### 개발용 폰트 설치
    - brew tap caskroom/fonts
    - brew cask install font-hack-nerd-font
    - iterm2 실행 - 커맨드+, - 프로파일 - 텍스트 - use a different font not-ASCII text 체크 - 다른탭선택했다가 다시 돌아와서 - Non-ASCII font 설정 - knack regular nerd font complete 선택
        - nerd 검색해서 선택 hack regular nerd font complete
        - 폰트사이즈 13
    - 깃헙 : https://github.com/ryanoasis/nerd-fonts

###### vim 강력 플러그인 - 초보를 위한 spacevim 설치
    - curl -sLf https://spacevim.org/install.sh | bash
    - 처음 실행시 1번 선택 : 다크테마
    - v ~/.SpaceVim/.SpaceVim.d/init.vim
        - #+
        - let g:spacevim_colorscheme = 'onedark'
    - 홈페이지: https://spacevim.org/documentation/
    - 깃헙: https://github.com/SpaceVim/SpaceVim

###### 터미널 멀티 플렉서 tmux 설치
    - .zshrc 의 plugins 에 tmux 추가
    - 테마:  https://github.com/gpakosz/.tmux
    - git clone https://github.com/gpakosz/.tmux.git
    - ln -s -f .tmux/.tmux.conf
    - cp .tmux/.tmux.conf.local .
    - 사용자 커스텀 설정: ~/.tmux.conf.local
            - set -g history-limit 10000  - 주석해제
            - set -g mouse on  - 주석해제
            - set -g status-keys vi  -주석해제
            - set -g mode-keys vi  -주석해제
    - tmux 개념
        - 세션session tmux가 관리하는 가장 큰 단위, tmux 실행단위
        - 윈도우window 세션안에 존재하는 탭같은 단위, 세션안의 탭
        - 팬pane 윈도우 안에 가로 세로로 분할한 단위, 탭안의 분할화면
    - 명령어  기능
        - tmux    세션 생성
        - tmux attach     생성되어 있는 세션에 진입
        - tmux ls 세션 목록 확인
    - 단축키  기능
        - ⌃ + b, c        새 창 만들기
        - ⌃ + b, d        tmux 환경에서 나오기
        - ⌃ + b, 1~9      해당 창으로 이동
        - ⌃ + b, %        세로로 창을 나눔 (좌/우)
        - ⌃ + b, "        가로로 창을 나눔 (위/아래)
        - ⌃ + b, 화살표   나뉘어진 창을 좌/우/위/아래로 움직임
    - tmux에 시스템 클립보드 복붙 돕는 tmux pasteboard
        - 깃헙: https://github.com/ChrisJohnsen/tmux-MacOSX-pasteboard
        - brew install reattach-to-user-namespace
            - 시스템에서 원하는 문장 복사 후 터미널에 $ pbpaste 하면 넣어짐
    - .zshrc 에 alias tx="tmux"  추가
    - 정리 잘 된 블로그
        - http://www.haruair.com/blog/2124
        - http://u-city.tistory.com/category/dummy/Tips?page=2
    - 명령어
        - sesstion
            - tx new -s <sess-name> : 세션생성
            - tx new -s <sess-name> -n <win-name> : 세션과 윈도우 함께 생성
                - alias txnew="tx new -s dev -n base"
                - dev 세션, base 윈도우 생성으로 txnew 등록
            - ctrl+b : tmux <prefix>
            - ctrl+b, $ : 세션 이름 수정
            - exit : 세션 종료
            - ctrl+b,d : 세션 중단(detach)
            - tx ls : 세션 목록
            - tx attach -t <num or sess name> : 중단한 세션에 연결
        - window
            - ctrl+b,c : 세션 내 윈도우 생성
            - ctrl+b, , : 윈도우 이름 수정
            - ctrl+d : 윈도우 닫기
            - ctrl+b, 0-9 : 윈도우 이동
        - pane
            - ctrl+b, % : 화면 횡 분할
            - ctrl+b, " : 화면 종 분할
            - ctrl+b, q : pane 번호 이동
            - ctrl+b, o : 영역 고정 pane 변경
            - ctrl+b, 화살표 : pane 화살표 방향 이동
            - ctrl + d : pane 삭제
            - ctrl + b, spacebar : pane 레이아웃 변경
            - ctrl + b, [ : copy mode

###### tmux 지원 프로그램 tmuxinator 설치
    - 깃헙: https://github.com/tmuxinator/tmuxinator
    - tmux manual: http://manpages.ubuntu.com/manpages/precise/en/man1/tmux.1.html#contenttoc6
    - brew install ruby
    - sudo gem install tmuxinator
        - mux new jekyll
        - mux start jekyll
        - mux ls
        - mux debug jekyll
        - mux delete jekyll

###### 로컬 서버 설정 지원 ngrok
    - <https://dashboard.ngrok.com/get-started>

###### 터미널 세션 녹화 asciinema
    - https://asciinema.org/
    - brew install asciinema
    - asciinema rec [filename]
    - asciinema play [filename]
        - asciinema play /path/filename.cast
        - asciinema play https://sample.com/filename.cast
        - asciinema play https://sample.com/filedir
            - <link rel="alternate" type="application/x-asciicast" href="/my/ascii.cast"> *
    - asciinema upload [filename]
    - asciinema auth 입력 후 url 따라 로그인하면 아스키네마 웹 사이트 계정과 로컬 연결됨

###### 시스템 정보 출력 neofetch
    - https://github.com/dylanaraps/neofetch/wiki/Customizing-Info
    - 설치: https://github.com/dylanaraps/neofetch/wiki/Installation#macos-homebrew
    - brew install neofetch
    - neofetch
    - cd ~/.config/neofetch
    - v config.conf

###### 프로젝트 버전관리 pyenv-virtualenv-autoenv 설치
    - https://wayhome25.github.io/django/2017/04/29/python-dev-environments/
    - 파이썬 버전 관리 프로그램 pyenv 설치
        - brew update
        - brew install pyenv
        - v .zshrc
            - #+
            - export PYENV_ROOT=/usr/local/var/pyenv
            - if which pyenv > /dev/null; then eval "$(pyenv init -)"; fi
            - if which pyenv-virtualenv-init > /dev/null; then eval "$(pyenv virtualenv-init -)"; fi
        - 파이썬 3.6.3 버전 설치
            - pyenv version
            - pyenv install --list
            - pyenv install 3.6.3
            - pyenv shell 3.6.3
            - python --version
            - pyenv global 3.6.3
    - 독립 개발 환경 제공해주는 가상 개발 환경 virtualenv 설치
        - brew install pyenv-virtualenv
        - v .zshrc
            - #+
            - eval "$(pyenv init -):
            - eval "$(pyenv virtualenv-init -)"
        - pyenv virtualenv 3.6.3 dev   #dev 가상환경 생성 파이썬 버전 3.6.3
        - pyenv activate dev #가상환경 실행
        - pyenv deactivate #가상환경 해제
        - pyenv shell dev #dev환경 기본으로 설정
        - pyenv global dev #dev환경 기본으로 설정
    - alias pydac="pyenv deactivate"
    - alias pyac="pyenv activate"
    - 갓보섭님 추천 자료: https://lhy.kr/configuring-the-python-development-environment-with-pyenv-and-virtualenv
        - virtualenv 3.6.3 생성 후 3.7로 잡히는 현상 생겨서 한 거
        - brew reinstall readline xz
        - pyenv uninstall dev
        - (pyenv install 3.6.3)
        - pyenv virtualenv 3.6.3 dev
        - pyenv activate dev
        - python --version

###### 아나콘다 설치
    - pyenv install anaconda3-3.5.2
    - pyenv virtualenv anaconda3-3.5.2 dev-ai


###### 아톰 설치: https://atom.io/
    - 아톰을 마크다운 에디터로 : http://futurecreator.github.io/2016/06/14/atom-as-markdown-editor/
    - 에디터 실행 - 커맨드+, - editor탭 - font famil - KoPubDotum 으로 변경, 사이즈 13
    - 에디터 실행 - 커맨드+, - editor탭 - scroll past end 체크(에디터 막줄에서도 스크롤 더 내릴 수 있음)
    - 에디터 실행 - 커맨드+, - editor탭 - soft wrap 체크(자동 줄바꿈)
    - 에디터 실행 - 커맨드+, - editor탭 - show line numbers 체크(줄번호)
    - 에디터 실행 - 커맨드+, - editor탭 - tab length 4로 변경(텝 깊이)
    - 에디터 실행 - 커맨드+, - install 탭 - markdown-preview-enhanced 다운
        - Previewer 자동 스크롤 (2-way Scroll)
        - 각종 수학식 입력
        - PDF와 HTML로 export
        - 마크다운 Previewer 커스터마이징 (css)
        - 이미지를 쉽게 넣을 수 있는 Image Helper
        - [TOC] 생성
        - 주석 입력
        - 기타 다양한 기능들
        - 커맨드+시프트+p   #커맨드 팔레트에 markdown preview enhanced 입력하면 실행 가능 명령어 출력
    - 에디터 실행 - 커맨드+, - install 탭 - markdown-format 다운
        - 마크다운 문서를 저장하면 자동으로 포맷에 맞춰주는 플러그인/항상 정리해줌
    - 에디터 실행 - 커맨드+, - install 탭 - Themes - genesis-ui 다운
    - 에디터 실행 - 커맨드+, - install 탭 - Themes - genesis-syntax 다운
    - 에디터 실행 - 커맨드+, - Themes 탭 - ui/syntax 테마 genesis 로 설정

###### jekyll 설치
    - cd; brew upgrade; brew install ruby; sudo gem install jekyll; mkdir blog; cd blog; git clone https://github.com/esteepark/esteepark.github.io.git; cd esteepark.github.io; jekyll serve
    - localhost:4000
    - esteepark.github.io

###### git 간편 설명서:
- <https://rogerdudler.github.io/git-guide/index.ko.html>

###### github markdown 사용법:
- https://gist.github.com/ihoneymon/652be052a0727ad59601



###### graphical 프로세스 리스트
    - brew install htop
    - htop



1. requirements.txt가 있는 디렉토리로 가서(cd 명령어)
2. virtualenv를 활성화 한 뒤
3. 쉘에서 pip install -r requirements.txt 해 주세요



---

```
pip freeze > requirements.txt  # 패키지 목록을 txt 파일로 만들기
pip install -r requirements.txt  # 한번에 패키지 설치
```

---

https://slideplayer.com/slide/5126304

###### cli의 가치 - 명령어 연속으로 실행
- https://opentutorials.org/module/2538/15818
- ;
    - 앞의 명령어가 실패해도 다음 명령어 실행
    - mkdir test; cd test
- &&
    - 앞의 명령어가 성공했을때 다음 명령어 실행
- &
    - 앞의 명령어를 백그라운드로 돌리고 동시에 뒤의 명령어를 실행
- 명령어 반환값: 리눅스의 모든 명령어는 종료할 때 성공 여부 알려줌
    - 0: 성공
    - 1: 실패
    - 127: 존재하지 않는 명령어
- 명령어 그룹핑 {} - 현재 쉘 / () - 서브쉘
    - mkdir test3 && { cd test3; touch abc; echo 'success!' } || echo 'There is no dir';
- 파이프라인 |
    - grep linux linux.txt   #linux.txt 파일 안의 linux 명령어 찾아서 출력
    - ls --help | grep sort   #ls --help 에서 sort라는 단어가 포함된 행만 출력
    - 파이프라인: 프로그램과 프로그램을 연결, 데이터 전달, 와..
        - ps aux   #현재 실행중인 프로그램 출력
        - ps aux | grep vim   #현재 실행중인 프로그램 중에 vim 만 출력
- 웹사이트에서 다운로드
    - wget -O [저장할이름] [다운받아올링크]
    - wget -O flower.jpg http://esteepark.github.io/flower.jpg
- git : 버전관리 시스템
    - git clone [url] [download-name]   #download-name으로 git 을 복사
- IO redirenction < >
    - output
        - ls -l > result.txt (= ls -l 1> result.txt)
        - rm rename2.txt 2> error.log   #에러를 error.log에 넣음
        - 1>    #standard output
        - 2>   #error output
    - input
        - cat hello.txt
            - cat 의 인자로 hello.txt 를 전달 : command-line argument
        - cat < hello.txt
            - cat에 인자가 아닌 표준 입력 : standard input 으로 hello.txt 전달
        - head -n1 < linux.txt > one.txt   #linux.txt의 첫번째 줄을 head의 standard input으로 전달하고 그것을 standard output으로 one.txt에 전달(저장)
    - >
        - redirection 결과 덮어쓰기
    - >>
        - redirection 결과 추가하기
    -  <<
        - redirection 입력 보내기


---

###### dotfiles 만들기
    - http://blog.appkr.kr/work-n-play/dotfiles/
    - 다음 초기화엔 dotfiles 만들기 도전!
