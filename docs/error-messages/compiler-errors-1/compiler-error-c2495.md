---
title: Derleyici Hatası C2495
ms.date: 11/04/2016
f1_keywords:
- C2495
helpviewer_keywords:
- C2495
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
ms.openlocfilehash: 83a0359fce175b12dd18e2500d63d7a86bed9f0b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360859"
---
# <a name="compiler-error-c2495"></a>Derleyici Hatası C2495

'identifier': 'nothrow' yalnızca işlev bildirimlerine veya tanımlarına uygulanabilir

[Nothrow](../../cpp/nothrow-cpp.md) işlev bildirimlerine veya tanımlarına yalnızca genişletilmiş öznitelik uygulanabilir.

Aşağıdaki örnek, C2495 oluşturur:

```
// C2495.cpp
// compile with: /c
__declspec(nothrow) class X {   // C2495
   int m_data;
} x;

__declspec(nothrow) void test();   // OK
```