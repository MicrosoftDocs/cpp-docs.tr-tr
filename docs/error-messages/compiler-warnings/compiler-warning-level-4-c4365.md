---
title: Derleyici Uyarısı (düzey 4) C4365
ms.date: 11/04/2016
f1_keywords:
- C4365
helpviewer_keywords:
- C4365
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
ms.openlocfilehash: 554ead2d26a090eb1ffc86e532841143483b365a
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683033"
---
# <a name="compiler-warning-level-4-c4365"></a>Derleyici Uyarısı (düzey 4) C4365

' Action ': ' type_1 ' değerinden ' type_2 ' öğesine dönüştürme, imzalanmış/imzasız uyuşmazlığı

Örneğin, işaretsiz bir değeri işaretli bir değere dönüştürmeye çalıştınız.

C4365 varsayılan olarak kapalıdır.  Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4365 oluşturur.

```cpp
// C4365.cpp
// compile with: /W4
#pragma warning(default:4365)

int f(int) { return 0; }
void Test(size_t i) {}

int main() {
   unsigned int n = 10;
   int o = 10;
   n++;
   f(n);   // C4365
   f(o);   // OK

   Test( -19 );   // C4365
}
```