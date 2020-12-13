---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2890'
title: Derleyici hatası C2890
ms.date: 11/04/2016
f1_keywords:
- C2890
helpviewer_keywords:
- C2890
ms.assetid: 49147375-182c-42b1-b170-f475cd436d47
ms.openlocfilehash: 4df022147b9e8b199fa2aea45c3af88525375690
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337445"
---
# <a name="compiler-error-c2890"></a>Derleyici hatası C2890

' class ': bir başvuru sınıfı yalnızca bir arabirim olmayan taban sınıfa sahip olabilir

Başvuru sınıfında yalnızca bir temel sınıf olabilir.

Aşağıdaki örnek C2890 oluşturur:

```cpp
// C2890.cpp
// compile with: /clr /c
ref class A {};
ref class B {};
ref class C : public A, public B {};   // C2890
ref class D : public A {};   // OK
```
