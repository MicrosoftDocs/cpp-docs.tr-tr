---
title: Derleyici Uyarısı (Düzey 3 ve 4) C4244
ms.date: 11/04/2016
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
ms.openlocfilehash: af06dbf5bb4a1dd133c277d63c40da2a8a54770b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359936"
---
# <a name="compiler-warning-levels-3-and-4-c4244"></a>Derleyici Uyarısı (Düzey 3 ve 4) C4244

'type1' öğesinden 'type2', olası veri kaybı 'conversion' dönüştürme

Bir tamsayı türü daha küçük bir tamsayı türüne dönüştürülür. Bu düzey 4 uyarısı ise *type1* olduğu `int` ve *type2* küçük olduğuna `int`. Aksi takdirde, bir düzey 3 olur (türünde bir değer atanmış [__int64](../../cpp/int8-int16-int32-int64.md) türünde bir değişkene `unsigned int`). Olası bir veri kaybı meydana gelebilir.

C4244 alırsanız, uyumlu türler kullanmak için programınızı değiştirmenize veya mantığa olası değerler aralığı her zaman kullanmakta olduğunuz türleri ile uyumlu olmasını sağlamak için kodunuzu ekleyin.

Ayrıca C4244 2 düzeyinde özelliği kullanabilirsiniz; bkz: [Derleyici Uyarısı (Düzey 2) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md) daha fazla bilgi için.

Dönüştürmenin örtük dönüştürmelerin nedeniyle bir sorun olabilir.

Aşağıdaki örnek, C4244 oluşturur:

```
// C4244_level4.cpp
// compile with: /W4
int aa;
unsigned short bb;
int main() {
   int b = 0, c = 0;
   short a = b + c;   // C4244

   bb += c;   // C4244
   bb = bb + c;   // C4244
   bb += (unsigned short)aa;   // C4244
   bb = bb + (unsigned short)aa;   // OK
}
```

Daha fazla bilgi için [olağan aritmetik dönüştürmeler](../../c-language/usual-arithmetic-conversions.md).

```
// C4244_level3.cpp
// compile with: /W3
int main() {
   __int64 i = 8;
   unsigned int ii = i;   // C4244
}
```

64-bit hedefler için kod oluşturma uyarısı 32-bit hedefler için derleme yaparken oluşturmaz C4244 uyarı oluşabilir. Örneğin, işaretçiler arasında bir fark, 32-bit platformlarda 32-bit miktarı, ancak bir 64-bit miktarı 64-bit platformlarda olur.

Aşağıdaki örnek, 64-bit hedefleri için derlendiğinde C4244 oluşturur:

```
// C4244_level3_b.cpp
// compile with: /W3
int main() {
   char* p1 = 0;
   char* p2 = 0;
   int x = p2 - p1;   // C4244
}
```