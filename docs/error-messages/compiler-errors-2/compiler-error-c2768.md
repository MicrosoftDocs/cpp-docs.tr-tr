---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2768'
title: Derleyici hatası C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: 0911153b9b89996631433d8a19bde9d19fc5f6b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239473"
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
