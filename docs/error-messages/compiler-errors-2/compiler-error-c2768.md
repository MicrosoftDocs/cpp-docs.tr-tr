---
title: Derleyici Hatası C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: 9c0fb8fb0a98830aaf061ba980e7bdd7903f25e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626180"
---
# <a name="compiler-error-c2768"></a>Derleyici Hatası C2768

'function': açık şablon bağımsız değişkenlerinin geçersiz kullanımı

Derleyici bir işlev tanımı bir işlev şablonunun açık uzmanlığı olması gerekiyordu veya işlev tanımı için yeni bir işlev olması gerekiyordu belirleyemedi.

Bu hata, derleyici uyumluluğu yapılan geliştirmelerin bir parçası olarak Visual Studio .NET 2003'te sunulmuştur.

Aşağıdaki örnek, C2768 oluşturur:

```
// C2768.cpp
template<typename T>
void f(T) {}

void f<int>(int) {}   // C2768

// an explicit specialization
template<>
void f<int>(int) {}

// global nontemplate function overload
void f(int) {}
```