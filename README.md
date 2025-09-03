# 📱 코르도바(Cordova) 앱 개발 수업 정리

## 1. 코르도바 소개
- **Apache Cordova**: 웹 기술(HTML, CSS, JavaScript)을 사용해 모바일 앱을 개발할 수 있는 오픈소스 프레임워크
- **특징**
  - 하나의 코드베이스로 **iOS, Android 등 다양한 플랫폼** 지원
  - 웹 기술 기반 → 웹 개발자도 쉽게 앱 개발 가능
  - 네이티브 API 접근을 위한 **플러그인 제공**

---

## 2. 개발 환경 구축
### (1) 필수 설치 프로그램
- Node.js (npm 포함)
- Git
- Cordova CLI
- JDK (Java Development Kit)
- Android Studio (에뮬레이터 및 SDK 관리)

### (2) Cordova 프로젝트 생성
```bash
# Cordova CLI 설치
npm install -g cordova

# 새 프로젝트 생성
cordova create MyApp com.example.myapp MyApp

# Android 플랫폼 추가
cd MyApp
cordova platform add android
```

---

## 3. 기본 프로젝트 구조
```
MyApp/
├── hooks/            # 빌드 이벤트 스크립트
├── platforms/        # 플랫폼별 코드 (Android, iOS 등)
├── plugins/          # Cordova 플러그인
├── www/              # 앱의 웹 자원 (HTML, CSS, JS)
└── config.xml        # 앱 설정 파일
```

- **www/** 폴더 → 실제 앱 화면을 담당하는 핵심 (HTML 기반 UI)
- **config.xml** → 앱 이름, 버전, 권한, 플러그인 설정

---

## 4. 앱 실행 및 테스트
```bash
# Android 빌드
cordova build android

# 에뮬레이터 실행
cordova emulate android

# USB 연결된 기기에서 실행
cordova run android
```

---

## 5. 플러그인 활용
Cordova는 **네이티브 기능**을 플러그인으로 제공  
예시: 카메라, 파일, 네트워크, 알림 등

```bash
# 카메라 플러그인 설치
cordova plugin add cordova-plugin-camera
```

**JavaScript 코드 예시**
```javascript
navigator.camera.getPicture(onSuccess, onFail, {
    quality: 50,
    destinationType: Camera.DestinationType.DATA_URL
});

function onSuccess(imageData) {
    document.getElementById('myImage').src = "data:image/jpeg;base64," + imageData;
}

function onFail(message) {
    alert('Failed because: ' + message);
}
```

---

## 6. 장단점
### ✅ 장점
- 크로스 플랫폼 지원
- 빠른 프로토타입 제작 가능
- 웹 기술만으로 앱 개발 가능

### ❌ 단점
- 성능 한계 (네이티브 대비)
- 플러그인 의존성 높음
- 복잡한 UI/애니메이션 구현 시 제약

---

## 7. 수업 실습 예제
1. **Hello World 앱 제작**
   - 기본 Cordova 프로젝트 생성 및 실행
2. **디자인 수정**
   - `www/index.html` 편집
3. **네이티브 기능 사용**
   - 카메라, 파일 저장 등 플러그인 실습
4. **최종 프로젝트**
   - 간단한 ToDo 앱 또는 사진첩 앱 제작

---

## 8. 참고 자료
- [Cordova 공식 문서](https://cordova.apache.org/docs/en/latest/)
- [GitHub Cordova](https://github.com/apache/cordova)
- [플러그인 검색](https://www.npmjs.com/search?q=cordova+plugin)

---
✍️ **정리**:  
Cordova 수업은 웹 기술로 모바일 앱을 만드는 방법을 배우고, 플러그인을 통해 네이티브 기능을 활용하는 실습 중심으로 진행된다.
