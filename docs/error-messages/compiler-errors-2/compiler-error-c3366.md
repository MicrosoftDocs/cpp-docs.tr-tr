---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3366'
title: Derleyici hatası C3366
ms.date: 11/04/2016
f1_keywords:
- C3366
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
ms.openlocfilehash: 922fa882efcaead4df87bbfc104394e12b797955
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150845"
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
