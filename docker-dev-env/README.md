# 윈도우즈에서 도커 개발 환경 설정
윈도우즈에서 도커 기반 개발 환경을 설정하는 방법에 대해 설명합니다.

## WSL 설치
참고: [WSL을 사용하여 Windows에 Linux를 설치하는 방법](https://learn.microsoft.com/ko-kr/windows/wsl/install)

1. **관리자 모드**에서 *PowerShell* 또는 *Windows 명령 프롬프트*를 연다.
2. 프롬프트에 다음과 같이 명령어를 입력한다.
```powershell
wsl --install
```
3. 설치 시, **오류 코드: Wsl/InstallDistro/Service/RegisterDistro/CreateVm/HCS/HCS_E_SERVICE_NOT_AVAILABLE** 오류가 발생할 수 있다. 이는 윈도우즈에 필요한 기능이 비활성화 되어있을 때 주로 발생한다. 이 경우, 프롬프트에 다음과 같이 명령어를 입력하여, 기능을 활성화한다. 설치가 끝나면 컴퓨터를 재부팅한다. 그리고 다시 WSL 설치를 시도해본다.
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
dism.exe /online /enable-feature /featurename:Microsoft-Hyper-V-All /all /norestart
```
4. Ubuntu가 기본적으로 설치되고, 설치 시, 계정(user account)과 암호(password)를 설정한다.
5. WSL 설치가 끝나면 컴퓨터를 재부팅한다.