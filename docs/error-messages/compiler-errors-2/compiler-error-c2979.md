---
title: Derleyici Hatası C2979
ms.date: 11/04/2016
f1_keywords:
- C2979
helpviewer_keywords:
- C2979
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
ms.openlocfilehash: 5d9b8e025d96e448ec9494834eb1766cafd8b677
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531050"
---
# <a name="compiler-error-c2979"></a>Derleyici Hatası C2979

Açık uzmanlık'nda genel türler için desteklenmez.

Genel sınıf yanlış bildirildi.  Bkz: [genel türler](../../windows/generics-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2979 oluşturur.

```
// C2979.cpp
// compile with: /clr /c
generic <>
ref class Utils {};   // C2979 error

generic <class T>
ref class Utils2 {};   // OK
```