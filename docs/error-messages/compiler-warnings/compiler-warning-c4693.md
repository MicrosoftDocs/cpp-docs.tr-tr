---
title: Derleyici Uyarısı C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: 71c3db18b400ce94bff3c643d6728a6613061039
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165138"
---
# <a name="compiler-warning-c4693"></a>Derleyici Uyarısı C4693

> ' class ': kapalı bir soyut sınıf ' test ' örnek üyelerine sahip olamaz

Bir tür [Sealed](../../extensions/sealed-cpp-component-extensions.md) ve [abstract](../../extensions/abstract-cpp-component-extensions.md)olarak işaretlenmişse yalnızca statik üyeleri olabilir.

Bu uyarı otomatik olarak bir hataya yükseltilir. Bu davranışı değiştirmek isterseniz [#pragma uyarı](../../preprocessor/warning.md)kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4693 oluşturur.

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```
