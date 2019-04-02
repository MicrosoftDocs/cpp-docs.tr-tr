---
title: Derleyici Hatası C3611
ms.date: 11/04/2016
f1_keywords:
- C3611
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
ms.openlocfilehash: 2d4c5cb02b1b8c5472502380fe7c74ff4a91954a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781932"
---
# <a name="compiler-error-c3611"></a>Derleyici Hatası C3611

'function': korumalı bir işlevin saf belirticisi olamaz

Korumalı bir işlevin yanlış bildirildi.  Daha fazla bilgi için [korumalı](../../extensions/sealed-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3611 oluşturur.

```
// C3611.cpp
// compile with: /clr /c

ref struct V {
   virtual void Test() sealed = 0;   // C3611
   virtual void Test2() sealed;   // OK
   virtual void Test3() = 0;   // OK
};
```