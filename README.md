# yusunpark.github.io

## 디렉토리 구조

### 기본 디렉토리 구조 및 설명

- **build_source 빌드를 위한 모든 것이 들어있는 디렉토리**
- build 문서를 패키지 하기위한 프로그램
- conf.py sphinx 기본 환경 파일
- doc 패키지할 매뉴얼이 들어 있는 디렉토리
- lib 패키지시 사용되는 라이브러리

### 생성되는 디렉토리

- t_build 임시 디렉토리 - 빌드 전
- t_source 임시 디렉토리 - 빌드 후
- out 최종 컴파일된 문서 보관

## 지원 문서 종류

rst, md 문서 포맷을 지원 하며, rst 로 작성하는 것을 추천

## 환경 구축 방법

### Python 환경 구축 하기

1. 기본적으로 사용중인 운영체제에 python 3.6이상을 설치 한다.

   - https://www.python.org/downloads/

   설치를 완료한 이후 `python`, `pip` 명령어가 정상적으로 동작하는지 확인한다. 만약 정상적으로 동작하지 않는다면, 환경 변수를 확인해야 한다.

2. `virtualenv` 를 설치한다. 만약 `virtualenv`가 설치되어 있다면 해당 과정을 생략할수 있다.

   ```
   pip install virtualenv
   ```

### git clone 받기

적당한 경로에 `yusunpark.github.io` 를 clone 받는다.

```
git clone https://github.com/YusunPark/yusunpark.github.io.git
```

### virtualenv 환경 구축하기

clone 받은 yusunpark.github.io 디렉토리 안에서 다음과 같이 명령어를 실행한다.

- for mac & linex

  ```
  $ python -m virtualenv venv
  $ source venv/bin/activate
  (venv) $ pip install -r requirements.txt
  ```

- for windows

  ```
  > python -m virtualenv venv
  > call venv\Scripts\activate
  (venv) > pip install -r requirements.txt
  ```

### 문서 빌드하기

다음과 같이 패키지 작업을 진행함

1. `build_source/doc` 디렉토리에 빌드하기를 원하는 문서를 저장

2. 문서 빌드 하기

   문서는 build_source 디렉토리 안에서 다음과 같은 방식으로 빌드를 진행함

   - for mac & linux

     ```shell
     (venv) $ ./build_web ALL
     ```

   - for windows

     ```powershell
     (venv) > build_web.bat
     ```

   위와 같이 빌드를 완료할 경우 최종 결과 파일은 `out` 디렉토리에 파일이 저장됨

3. 빌드 문서 확인하기

   - **`/index.html` 을 통해 최종 빌드된 문서를 웹으로 확인할 수 있음**
   - `out/IRIS/index.html` 에서도 같은 문서를 저장하고 있다.

   3-1. 테마 적용

   - `build_source/templates/web/layout.html` 와 `build_source/conf.py` 파일에 css 경로를 넣어주어야 한다.
<!-- 
   - 테마 미적용시
     ![image](https://user-images.githubusercontent.com/59571464/90234257-5ef8ad80-de5a-11ea-891e-09cac2714afe.png)

   - 기존 테마
     ![theme](https://user-images.githubusercontent.com/59571464/90233136-9fefc280-de58-11ea-8c87-f0045c6b9f70.png)

   - custom 테마
     ![theme_custom](https://user-images.githubusercontent.com/59571464/90233148-a3834980-de58-11ea-8de8-aa86a77b5126.png)

   ```plain text
   [테마 미적용]     theme.css와 theme_custom.css 모두 build_source/templates/web 디렉토리에 있을 경우
   [기존 테마]       theme.css만 build_source 디렉토리에 있을 경우
   [custom 테마]    theme_custom.css만 build_source 디렉토리에 있을 경우
   ``` -->

### info.conf

매뉴얼의 정보를 담고 있는 파일입니다.
해당 내용은 다음과 같은 구조로 되어있습니다.

```
[info]
title = IRIS-Doc Documentation
project = IRIS-DB Doc
copyright = 2018, team IRIS-DB
author = team IRIS-DB
version =
release = 0.1


[index]
doc/01.instruction.rst
doc/02.operating_command.rst
doc/03.system_management.rst
doc/04.monitoring.rst
```

`info` section에 대한 항목은 문서의 버전 및 title 등의 항목을 기재 합니다.

`index` section에 대한 항목은 각 문서의 목록을 기재 합니다.
