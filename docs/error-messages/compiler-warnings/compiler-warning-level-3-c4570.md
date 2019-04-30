---
title: Derleyici Uyarısı (Düzey 3) C4570
ms.date: 11/04/2016
f1_keywords:
- C4570
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
ms.openlocfilehash: 386d7c210c77469d67a75d66f7d8ae35c105b3b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401793"
---
# <a name="compiler-warning-level-3-c4570"></a>Derleyici Uyarısı (Düzey 3) C4570

'type': soyut ancak soyut işlevler içeriyor olarak açıkça bildirilmedi

İçeren bir tür [soyut](../../extensions/abstract-cpp-component-extensions.md) işlevleri kendi işaretlenmemelidir soyut olarak.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4570 oluşturur.

```
// C4570.cpp
// compile with: /clr /W3 /c
ref struct X {   // C4570
// try the following line instead
// ref class X abstract {
   virtual void f() abstract;
};
```