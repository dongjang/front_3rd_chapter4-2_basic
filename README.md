# 성능 개선 보고서

## 테스트 방법

### 배포 URL

- https://d2hnnj815xakwr.cloudfront.net/

### 성능 테스트

- PageSpeed Insights를 활용한 배포 URL 성능 테스트 : https://pagespeed.web.dev

## 목차

1. [개선 이유](#개선-이유)
2. [개선 대상](#개선-대상)
3. [개선 방법](#개선-방법)
4. [개선 후 향상된 지표](#개선-후-향상된-지표)

### 개선 이유

![alt text](</images/report/개선 전 성능.png>)

- 처음부터 최적화가 진행되지 않아 개선 필요
- 성능 보고서에서도 볼 수 있는 낮은 성능

### 개선 대상

- Images
- Fonts
- JavaScript

### 개선 방법

#### Images

- 압축 후 기존 .jpg, png 파일을 webp로 변경
- img 태그에서 width, height 지정
- lazy를 이용한 자원 최적화

#### Fonts

- URL을 직접 가져와 Fonts 호출하는 부분 제거
- WOFF와 WOFF2를 통한 Fonts 최적화

#### JavaScript

- defer를 이용한 script 호출로 JavaScript 최적화
- cookie-consent.js 저장 후 호출

### 개선 후 향상된 지표

- 개선 전 성능
  ![alt text](</images/report/개선 전 성능.png>)

- 개선 후 성능
  ![alt text](</images/report/개선 후 성능.png>)

| 대상                          | 개선 전 | 개선 후 | 개선율 |
| ----------------------------- | ------- | ------- | ------ |
| 성능                          | 79      | 96      | 21.52% |
| 접근성                        | 82      | 89      | 8.54%  |
| 권장사항                      | 96      | 96      | 0%     |
| 검색엔진 최적화               | 82      | 82      | 0%     |
| First Contentful Paint(FCP)   | 0.7초   | 0.3초   | 57.14% |
| Largest Contentful Paint(LCP) | 3.0초   | 1.0초   | 66.67% |
| Total Blocking Time(TBP)      | 0.17초  | 0.15초  | 11.76% |
| Cumulative Layout Shift(CLS)  | 0.016   | 0.013   | 18.75% |
| Speed Index                   | 0.8초   | 0.3초   | 62.5%  |

#### 요약

- Images, Fonts, JavaScript의 최적화로 인해 성능 및 접근성 개선
- Images 파일 압축 및 WOFF와 WOFF2 사용을 통해 FCP 및 LCP 성능이 크게 개선
- 외부 URL 대신 저장된 파일을 사용하고, defer 속성을 사용하여 스크립트 로딩을 최적화함으로써 TBT 성능 개선
- WOFF 글꼴 사용을 통해 CLS 성능이 향상되어 LCP 개선
- 전체적인 성능 개선으로 Speed Index가 크게 개선
