---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3241'
title: Derleyici hatası C3241
ms.date: 11/04/2016
f1_keywords:
- C3241
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
ms.openlocfilehash: c940599ccee67338c6a088793970b7a255d83ff2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307346"
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
