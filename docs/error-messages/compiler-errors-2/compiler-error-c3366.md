---
title: Derleyici hatası C3366
ms.date: 11/04/2016
f1_keywords:
- C3366
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
ms.openlocfilehash: 5173b1c0df7de6a4e8d9993e680b961a82bb10a7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738472"
---
# <a name="compiler-error-c3366"></a>Derleyici hatası C3366

' Variable ': yönetilen veya Wınrttypes 'ın statik veri üyeleri sınıf tanımı içinde tanımlanmalıdır

Bir WinRT veya .NET sınıfının veya arabiriminin bir statik üyesine bu sınıfın veya arabirimin tanımının dışında başvurulmasına çalıştınız.

Derleyicinin sınıfın tam tanımını (bir geçiş sonrasında meta verileri göstermek için) bilmeleri gerekir ve statik veri üyelerinin sınıf içinde başlatılmasını gerektirir.

Örneğin, aşağıdaki örnek C3366 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```
