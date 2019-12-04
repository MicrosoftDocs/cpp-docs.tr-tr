---
title: Derleyici hatası C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: bcc801bb5802598e936d577f08729214bb7e13a1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759795"
---
# <a name="compiler-error-c2768"></a>Derleyici hatası C2768

' function ': açık şablon bağımsız değişkenlerinin geçersiz kullanımı

Derleyici, bir işlev tanımının bir işlev şablonunun açık özelleştirmesi olup olmadığını veya işlev tanımının yeni bir işlev için olması gerekip gerekmediğini belirleyemedi.

Bu hata, derleyicinin uyumluluk geliştirmelerinin bir parçası olarak Visual Studio .NET 2003 ' de sunulmuştur.

Aşağıdaki örnek C2768 oluşturur:

```cpp
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
