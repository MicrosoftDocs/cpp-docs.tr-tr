---
title: Derleyici Hatası C2890
ms.date: 11/04/2016
f1_keywords:
- C2890
helpviewer_keywords:
- C2890
ms.assetid: 49147375-182c-42b1-b170-f475cd436d47
ms.openlocfilehash: 43c05fba15ee78c8e1454c115246f557f98f897e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311715"
---
# <a name="compiler-error-c2890"></a>Derleyici Hatası C2890

'class': başvuru sınıfı yalnızca arabirim olmayan bir taban sınıfı olabilir

Başvuru sınıfı, yalnızca bir temel sınıf olabilir.

Aşağıdaki örnek, C2890 oluşturur:

```
// C2890.cpp
// compile with: /clr /c
ref class A {};
ref class B {};
ref class C : public A, public B {};   // C2890
ref class D : public A {};   // OK
```
