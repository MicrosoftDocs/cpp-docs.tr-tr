---
title: Derleyici Uyarısı (düzey 2) C4244
ms.date: 11/04/2016
f1_keywords:
- C4244
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
ms.openlocfilehash: a07adf37314a11cceb72d6675a66d82f7554bbb6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162068"
---
# <a name="compiler-warning-level-2-c4244"></a>Derleyici Uyarısı (düzey 2) C4244

' Argument ': ' type1 ' öğesinden ' type2 ' öğesine dönüştürme, olası veri kaybı

Kayan nokta türü bir tamsayı türüne dönüştürüldü.  Olası bir veri kaybı oluşmuş olabilir.

C4244 alırsanız, programınızı uyumlu türler kullanacak şekilde değiştirmeniz veya kodunuzda bir mantık eklemeniz gerekir, bu da olası değerlerin aralığının her zaman kullandığınız türlerle uyumlu olmasını sağlar.

C4244 Ayrıca 3. düzey ve 4 ' te de tetikde olabilir. daha fazla bilgi için bkz. [Derleyici Uyarısı (düzey 3 ve 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4244 oluşturur:

```cpp
// C4244_level2.cpp
// compile with: /W2

int f(int x){ return 0; }
int main() {
   double x = 10.1;
   int i = 10;
   return (f(x));   // C4244
   // try the following line instead
   // return (f(i));
}
```
