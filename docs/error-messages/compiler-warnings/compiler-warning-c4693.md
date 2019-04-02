---
title: Derleyici Uyarısı C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: cac5918eb4a1689fd215e07272958eeca48247ad
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781906"
---
# <a name="compiler-warning-c4693"></a>Derleyici Uyarısı C4693

> 'class': kapalı bir soyut sınıf 'Test' örnek üyelerine sahip olamaz

Bir tür işaretlenmişse [korumalı](../../extensions/sealed-cpp-component-extensions.md) ve [soyut](../../extensions/abstract-cpp-component-extensions.md), yalnızca statik üyeleri olabilir.

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4693 oluşturur.

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```