---
title: Derleyici hatası C3241
ms.date: 11/04/2016
f1_keywords:
- C3241
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
ms.openlocfilehash: 6a618a9c538558d2aa4b995cbc9071bb8e94a5bc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754588"
---
# <a name="compiler-error-c3241"></a>Derleyici hatası C3241

' Method ': Bu yöntem ' Interface ' tarafından tanıtılmadı

Bir işlevi açıkça geçersiz kıldığınızda, işlev imzası, geçersiz kıldığınız işlevin bildirimiyle tam olarak eşleşmelidir.

Aşağıdaki örnek C3241 oluşturur:

```cpp
// C3241.cpp
#pragma warning(disable:4199)

__interface IX12A {
   void mf();
};

__interface IX12B {
   void mf(int);
};

class CX12 : public IX12A, public IX12B { // C3241
   void IX12A::mf(int);
};
```
