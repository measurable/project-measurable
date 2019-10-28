---
title: "3. 파동함수"
date: 2019-09-19T12:28:32+09:00
categories:
    - 표현
tags:
    - 물리
    - qm
keywords:
    - 왜-복소수를-쓰나
inspired:
motivation:
draft: true
---

>고전적인 파동이 만족하는 미분 방정식은 시간에 대한 2차 편미분값이 공간에 대한 2차 편미분값에 비례한다는 것을 의미한다. 사인과 코사인 함수는 변수에 대한 2차 미분값이 자기 자신에 비례하므로 위 미분 방정식의 해가 될 수 있다. 재미있는 사실은 허수를 변수로 갖는 지수 함수도 위 미분 방정식의 해가 될 수 있다는 것이다. 하지만 그 이유는 약간 다르다. 지수 함수는 이전 글에서 보았듯이 변수에 대한 1차 미분값이 자기 자신에 비례한다. 1차 미분값이 자기 자신에 비례하면 2차 미분값도 자기 자신에 비례하므로, 위 방정식의 해가 될 수 있다. 이런 미묘한 차이가 왜 중요할까?

>상대성이론에 따르면 시간과 공간은 시공간이라는 하나의 개념으로 묶일 수 있다. 하지만 양자역학에서는 시간과 공간이 슈뢰딩거 방정식에서 나타나는 방식이 조금 다르다. 특히 슈뢰딩거 방정식은 시간에 대해서는 언제나 1차 미분 방정식이지만 공간에 대해서는 상황에 따라 미분 차수가 다를 수 있다. 슈뢰딩거 방정식을 상대성 이론과 일관되게 만들기 위해서는 시간과 공간에 대한 미분 차수를 동일하게 맞추는 것이 중요하다. 실제로 이러한 노력이 성공하여 만들어진 미분 방정식이 바로 그 유명한 디랙 방정식(Dirac equation)이다. 사실 슈뢰딩거 자신도 처음에는 상대성이론과 일관된 미분 방정식을 만들기 위해서 시간과 공간에 대해서 동시에 2차 미분이 들어가는 미분 방정식을 고려하였다. 하지만 이 시도는 아래 설명되는 문제로 인해서 실패하였고, 결국 상대성이론을 포기하는 대신에 시간에 대해서만 1차 미분 방정식인 슈뢰딩거 방정식을 만들게 되었다. 이후 디랙이 슈뢰딩거 방정식과 상대성이론을 일관되게 하여 디랙 방정식을 만들게 되었는데, 이 과정에는 물리학자들이 자연을 바라보는 매우 독특한 관점이 녹아 있다. 하지만 이를 이해하기 위해서는 현재로서 너무 복잡한 수학이 동원되어야 하므로...

>결론적으로, 파동 함수의 확률론적 해석을 받아들이는 순간, 슈뢰딩거 방정식은 시간에 대한 1차 미분 방정식이어야 했고, 이 상황에서 파동을 기술하기 위해서는 허수가 반드시 필요했다. 양자역학은 태생적으로 허수의 존재를 절실히 요구했던 것이다!

>그런데, 잠깐.
파동 함수의 절대값의 제곱, 즉 확률 분포만이 실제로 잴 수 있는 양이라면, 도대체 파동 함수의 위상각(phase angle)은 왜 필요한 것일까?

<span class="pretag">원문 링크</span>: <a href="https://horizon.kias.re.kr/archives/allarticles/naturalsciences/믿기-힘든-양자-incredible-quantum/" target="_blank">1. 들어가며</a> <a href="https://horizon.kias.re.kr/archives/allarticles/naturalsciences/%eb%af%bf%ea%b8%b0-%ed%9e%98%eb%93%a0-%ec%96%91%ec%9e%90incredible-quantum-2/" target="_blank">2. 가장 순수한 형태의 파동</a> <a href="https://horizon.kias.re.kr/archives/allarticles/naturalsciences/믿기-힘든-양자-incredible-quantum-3/" target="_blank">3. 파동 방정식</a> <a href="https://horizon.kias.re.kr/archives/allarticles/naturalsciences/%EB%AF%BF%EA%B8%B0-%ED%9E%98%EB%93%A0-%EC%96%91%EC%9E%90-incredible-quantum-4-%EA%B2%8C%EC%9D%B4%EC%A7%80-%EB%8C%80%EC%B9%AD%EC%84%B1/" target="_blank">4. 게이지 대칭성</a> <a href="https://horizon.kias.re.kr/archives/allarticles/naturalsciences/믿기-힘든-양자-incredible-quantum-5-양자-삼위일체-1부/" target="_blank">5. 양자 삼위일체 1부</a> <a href="https://horizon.kias.re.kr/archives/allarticles/naturalsciences/%EB%AF%BF%EA%B8%B0-%ED%9E%98%EB%93%A0-%EC%96%91%EC%9E%90-incredible-quantum-6-%EC%96%91%EC%9E%90-%EC%82%BC%EC%9C%84%EC%9D%BC%EC%B2%B4-2%EB%B6%80/" target="_blank">6. 양자 삼위일체 2부</a> <a href="https://horizon.kias.re.kr/archives/allarticles/naturalsciences/%EB%AF%BF%EA%B8%B0-%ED%9E%98%EB%93%A0-%EC%96%91%EC%9E%90-incredible-quantum-7-%EB%91%90-%EC%83%81%ED%83%9C-%EC%9D%B4%EC%95%BC%EA%B8%B0/" target="_blank">7. 두 상태 이야기</a> <a href="https://horizon.kias.re.kr/archives/allarticles/naturalsciences/믿기-힘든-양자-incredible-quantum-8-위상의-귀환/" target="_blank">8. 위상의 귀환</a> <span class="pretag">미간행</span>: <a href="#" target="_blank">9. 양자 얽힘</a> <a href="#" target="_blank">10. 더 높은 차원으로</a> <a href="#" target="_blank">11. 양자 물질 상태</a> <a href="#" target="_blank">12. 많음, 다름, 그리고 양자</a> <a href="#" target="_blank">13. 상대성과 양자, 통합되다</a> <a href="#" target="_blank">14. 파동의 두번째 양자화</a> <a href="#" target="_blank">15. 끝맺으며</a> (2019.09.19 현재)
