---
title: Derleyici Uyarısı (Düzey 2) C4244
ms.date: 11/04/2016
f1_keywords:
- C4244
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
ms.openlocfilehash: af821d80ff8c4c7717986f2ff4d0f3392cd6fca3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349730"
---
# <a name="compiler-warning-level-2-c4244"></a>Derleyici Uyarısı (Düzey 2) C4244

'bağımsız değişkeni': 'type1' öğesinden 'type2', olası veri kaybı dönüştürme

Bir kayan nokta türü bir tamsayı türüne dönüştürüldü.  Olası bir veri kaybı meydana gelebilir.

C4244 alırsanız, uyumlu türler kullanmak için programınızı değiştirmenize veya mantığa olası değerler aralığı her zaman kullanmakta olduğunuz türleri ile uyumlu olmasını sağlamak için kodunuzu ekleyin.

Ayrıca C4244 3 ve 4 düzeyinde özelliği kullanabilirsiniz; bkz: [Derleyici Uyarısı (Düzey 3 ve 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4244 oluşturur:

```
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