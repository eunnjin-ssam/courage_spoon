# 방관 대신 용기 한 스푼

## 파일 구조
- index.html : 교사 화면 (프로젝터에 띄우는 화면)
- student.html : 학생 화면 (디벗에서 QR코드로 접속)
- images/ : 상황 이미지 폴더

## 이미지 파일 넣는 방법
images/ 폴더에 아래 파일명으로 이미지를 넣어주세요:
- situation1.png ~ situation6.png : 각 상황 일러스트
- situation1_resolved.png ~ situation6_resolved.png : 해결된 상황 이미지

이미지가 없어도 텍스트로 대체되어 작동합니다.

## GitHub Pages 배포 방법
1. GitHub에서 새 repository 생성 (예: courage-spoon)
2. 이 폴더의 파일을 모두 업로드
3. Settings → Pages → Branch: main 선택 → Save
4. 배포된 URL 확인

## Firebase 설정
- Firestore 규칙을 테스트 모드로 설정해주세요
- Firebase Console → Firestore Database → 규칙 탭에서 아래로 변경:
  rules_version = '2';
  service cloud.firestore {
    match /databases/{database}/documents {
      match /{document=**} {
        allow read, write: if true;
      }
    }
  }
