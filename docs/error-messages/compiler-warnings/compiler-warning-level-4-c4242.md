---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4242'
title: Derleyici Uyarısı (düzey 4) C4242
ms.date: 11/04/2016
f1_keywords:
- C4242
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
ms.openlocfilehash: 7eabb546e2dff11b52be20e1a791aa31e9373a69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334850"
---
# <a name="compiler-warning-level-4-c4242"></a>Derleyici Uyarısı (düzey 4) C4242

' tanımlayıcı ': ' type1 ' değerinden ' type2 ' öğesine dönüştürme, olası veri kaybı

Türler farklıdır. Tür dönüştürme, veri kaybına neden olabilir. Derleyici tür dönüştürmeyi yapar.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

C4242 hakkında daha fazla bilgi için bkz. [yaygın derleyici hataları](/windows/win32/WinProg64/common-compiler-errors).

Aşağıdaki örnek C4242 oluşturur:

```cpp
// C4242.cpp
// compile with: /W4
#pragma warning(4:4242)
int func() {
   return 0;
}

int main() {
   char a;
   a = func();   // C4242, return type and variable type do not match
}
```
