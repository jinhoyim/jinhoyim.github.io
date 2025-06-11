---
title: "Jetbrains Rider Test Runner Pending 문제"
date: 2024-11-07T13:39:00+09:00
lastmod: 2025-06-12T00:30:00+09:00
slug: "rider-test-runner-pending-issue"
categories: ["DevTools"]
tags: [".NET", "Issue"]
description: "MacOS에서 Jetbrains Rider를 사용해서 테스트할 때 네트워크 프로그램이나 환경에 따라 실행한 테스트가 Pending 상태로 유지되는 문제가 있다."
---

Arm64 MacOS Jetbrains Rider에서 테스트가 종료되지 않는 버그를 발견했다.

Rider 2024.1.6 이후 버전부터 증상이 나타났다. 단일 테스트는 중지 버튼이 나타나고 Theory와 함께 AutoData를 사용한 여러 개의 테스트를 실행하면 Pending 상태의 테스트를 명확하게 볼 수 있다. 중지를 눌러도 실행 중인 테스트의 상태는 풀리지 않는다.

임시 해결책으로 Rider 2024.1.6 버전을 사용하면 테스트가 정상적으로 동작한다.

> 2025-06-12 업데이트 : 현재까지 확인된 내용은 MacOS에서 VPN, AdGuard처럼 네트워크 내부에 프록시와 같은 개입이 있는 경우 Rider Test Runnder가 내부적으로 처리하는 통신에 실패하여 생기는 것으로, 네트워크 도구를 종료시키면 임시로 동작시킬 수 있다. 하지만 VPN 환경은 우회할 방법이 없다. 이 경우 Visual Studio Code를 사용하거나 dotnet CLI에서 테스트를 실행하는 방법을 사용했다.
