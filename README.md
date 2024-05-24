# demand_forecasting_with_ml-stage0
demand_forecasting_with_ml

# 도커 vs 도커 컴포즈
도커는 단일 컨테이너를 관리하는 데 초점을 둔 도구입니다. 기본적으로 컨테이너를 생성, 실행, 중지 등의 작업을 수행 vs
도커 컴포즈는 여러 컨테이너로 구성된 애플리케이션의 관리를 단순화하는 도구입니다. docker-compose.yml 파일을 통해 서비스를 정의하고, 한 번의 명령으로 여러 컨테이너를 시작하거나 중지할 수 있다.

# step1) 다운로드
```console
git clone https://github.com/unerue/ml-system-design.git
```
# step2) powershell로 choco설치
```console
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

# step3) make 설치
```console
choco install make
```

# step4) make 설치
```console
choco install make
```

# step5) makefile에서 ABSOLUTE_PATH := $(shell pwd)의미


ABSOLUTE_PATH := $(shell pwd)는 Makefile에서 현재 작업 디렉토리의 절대 경로를 변수 ABSOLUTE_PATH에 할당하는 구문이다. 각 부분의 의미는 다음과 같다.

ABSOLUTE_PATH: 변수 이름으로, 현재 작업 디렉토리의 절대 경로를 저장한다.
:=: "단순 치환(Simple Assignment)" 연산자이다. ABSOLUTE_PATH 변수에 값을 할당할 때 한 번만 평가된다.
$(shell pwd): pwd 명령을 쉘에서 실행하고, 그 결과를 반환한다. pwd 명령은 현재 작업 디렉토리의 절대 경로를 출력한다.
따라서, 이 구문은 현재 작업 디렉토리의 절대 경로를 ABSOLUTE_PATH 변수에 저장하여 나중에 Makefile 내에서 해당 경로를 참조할 수 있도록 한다. 예를 들어, 파일 경로를 지정하거나 다른 쉘 명령에서 경로를 사용할 때 유용하다.

** 왜인지는 모르나 오류가 나니 직접 절대 경로를 적었습니다. **

# step6) Dockerfile에서 수정할것
현재 필자는 64bit 컴퓨터를 사용중임으로
FROM ${FROM_IMAGE}을 
FROM --platform=linux/amd64 ${FROM_IMAGE}
로 바꾸어준다.

# step7) ERROR: failed to solve: operating system is not supported 가 떠서
![image](https://github.com/creepereye1204/demand_forecasting_with_ml-stage0/assets/112455232/1d50fb8b-2e40-473d-84f9-d2ba4db199fe)
을 사용했다.
