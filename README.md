# yusunpark.github.io

## 디렉토리 구조

### 기본 디렉토리 구조 및 설명

- build_source      build에 필요한 모든 것이 들어있는 디렉토리
- build             문서를 패키지 하기위한 프로그램
- conf.py           sphinx 기본 환경 파일
- doc               패키지할 매뉴얼이 들어 있는 디렉토리
- lib               패키지시 사용되는 라이브러리

### 생성되는 디렉토리

- t_build           임시 디렉토리 - 빌드 전
- t_source          임시 디렉토리 - 빌드 후
- out               최종 컴파일된 문서 보관

### virtualenv 환경 구축하기

clone 받은 IRIS-Documentation 디렉토리 안에서 다음과 같이 명령어를 실행한다.

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

1. doc 디렉토리에 빌드하기를 원하는 문서를 저장

   `build_source/docs` 디렉토리에 빌드하기를 원하는 문서를 저장

    ```
    IRIS-Data-Discovery-Service_Doc
    IRIS-DB_Doc
    IRIS-WEB_Doc
    SMS_Doc
    ```

2.  문서 빌드 하기

    문서는 다음과 같은 방식으로 빌드를 진행함


    - for mac & linux

      ```shell
      (venv) $ ./build_web ALL
      ```

    - for windows

      ```powershell
      (venv) > build_web.bat
      ```


    빌드에 필요한 것들이 build_source에 있으므로 build_source 디렉토리로 이동 후 build_web 을 실행한다.
    
      ```shell
      (venv) $ cd build_source
      (venv) $ ./build_web ALL
      ```

    위와 같이 빌드를 완료할 경우 최종 결과 파일은 `out` 디렉토리에 파일이 저장된 후 루트폴더로 전부 이동됨.  

3. 빌드 문서 확인하기

   1. `index.html` 을 통해 최종 빌드된 문서를 웹으로 확인할 수 있음
   2. 빌드 후 모든 파일을 `push` 하면 `https://yusunpark.github.io/` 에서 확인 
