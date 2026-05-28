# EV Thunder BMS System

**BMS (Battery Management System) 기반의 UDS 진단통신 및 OTA 업데이트 시스템**

---

## 🎯 프로젝트 개요

이 프로젝트는 배터리 관리 시스템(BMS)을 중심으로 UDS(Unified Diagnostic Services)를 통한 진단통신과 OTA(Over-The-Air) 방식의 펌웨어 업데이트 기능을 제공하는 통합 시스템입니다.

### 주요 기능

- **BMS (배터리 관리 시스템)**: Main-BMS와 Sub-BMS로 구분된 멀티 ECU 구조
- **UDS 진단통신**: 차량 진단 프로토콜 기반 실시간 모니터링 및 진단
- **OTA 업데이트**: 무선으로 펌웨어 업데이트 가능 (TriCore 및 Windows 플랫폼)
- **시뮬레이션 환경**: BMS 동작을 테스트할 수 있는 시뮬레이터 및 유니티 디스플레이

---

## 📁 프로젝트 구조

| 프로젝트                 | 설명                                   | 담당자         |
| ------------------------ | -------------------------------------- | -------------- |
| **Main-BMS-System**      | 메인 BMS 제어 로직 (TriCore 기반)      | 강현수         |
| **Sub-BMS-System**       | 서브 BMS 제어 로직 (TriCore 기반)      | 강현수         |
| **BMS-Simulator-System** | BMS 시뮬레이션 및 통신 테스트 (Python) | 강현수         |
| **BMS-Unity-Display**    | 배터리 상태 표시 UI (Unity)            | 강현수         |
| **UDS_Tool**             | UDS 진단통신 도구                      | 이무석, 장혜나 |
| **OTA**                  | OTA 업데이트 시스템                    | 황선안, 김정연 |

---

## 👥 팀 구성

### BMS 시스템 개발

- **강현수** (`@kang-hyun-su`)
  - Main-BMS-System 개발
  - Sub-BMS-System 개발
  - BMS-Simulator-System 개발
  - BMS-Unity-Display 개발

### UDS 진단통신

- **이무석** (`@lee-mu-seok`)
- **장혜나** (`@jang-hye-na`)
  - UDS_Tool 개발
  - UDS 프로토콜 구현
  - 진단통신 인터페이스 개발

### OTA 업데이트 시스템

- **황선안** (`@hwang-sun-an`)
- **김정연** (`@kim-jung-yeon`)
  - OTA 업데이트 엔진 개발
  - TriCore OTA 구현 (OTA_TC375)
  - Windows OTA 구현 (OTA_Win)
  - Bootloader (OTA_Ras) 개발

---

## 🛠️ 기술 스택

### BMS & 시뮬레이션

- **Language**: C (TriCore), Python, C#
- **Framework**: AUTOSAR (TriCore), Unity (UI)
- **Tools**: TASKING Toolchain, GCC TriCore

### UDS & OTA

- **Protocol**: UDS (ISO 14229-1), CAN, TCP/IP
- **Language**: Python, C, C#
- **Architecture**: Multi-core (TriCore TC375)

---

## 📋 시스템 동작 흐름

```
┌─────────────────────────────────────────────────────┐
│                  BMS Control Logic                  │
│            (Main-BMS & Sub-BMS Systems)             │
└────────────────┬────────────────────────────────────┘
                 │
       ┌─────────┴─────────┐
       │                   │
       ▼                   ▼
┌─────────────────┐ ┌──────────────────┐
│  UDS Diagnostic │ │ OTA Update       │
│  Communication  │ │ System           │
│ (이무석, 장혜나) │ │(황선안, 김정연) │
└─────────────────┘ └──────────────────┘
       │                   │
       └─────────┬─────────┘
                 │
       ┌─────────┴──────────┐
       │                    │
       ▼                    ▼
┌──────────────────┐ ┌──────────────────┐
│ BMS Simulator    │ │ Unity Display    │
│ (Python)         │ │ (강현수)        │
└──────────────────┘ └──────────────────┘
```

---

## 🚀 빠른 시작

### 개발 환경 설정

1. **TriCore 개발 환경**: TASKING Toolchain 설치
2. **Python 환경**: Python 3.8+ 필요
3. **Unity 환경**: Unity 2022 LTS 이상

### 빌드 및 실행

#### Main BMS System

```bash
cd Main-BMS-System
# TASKING IDE 또는 make를 통한 빌드
make build
```

#### BMS Simulator

```bash
cd BMS-Simulator-System
python -m src.simulator.main
```

#### UDS Tool

```bash
cd UDS_Tool
# UDS 진단 도구 실행
```

#### OTA Update

```bash
cd OTA
# OTA 업데이트 프로세스 실행
```

---

## 📚 문서

각 프로젝트별 상세 문서는 다음 위치에서 확인할 수 있습니다:

- [BMS Simulator 시뮬레이션 정책](BMS-Simulator-System/docs/User_Simulation_Drive_Control_Policy_V0.1.md)
- [Main BMS README](Main-BMS-System/README.md)
- [Sub BMS README](Sub-BMS-System/README.md)
- [OTA 시스템 README](OTA/README.md)
- [UDS Tool README](UDS_Tool/README.md)

---

## 📞 문의 및 지원

각 팀별 담당자:

- **BMS 관련**: 강현수
- **UDS 진단**: 이무석, 장혜나
- **OTA 업데이트**: 황선안, 김정연

---

**Last Updated**: 2026-05-28
