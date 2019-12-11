---
title: Derleyici Uyarısı (düzey 3 ve 4) C4244
ms.date: 11/04/2016
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
ms.openlocfilehash: a12bee4591df8a7a952dc741c4b26c637bb5256c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991079"
---
# <a name="compiler-warning-levels-3-and-4-c4244"></a>Derleyici Uyarısı (düzey 3 ve 4) C4244

' type1 ' öğesinden ' type2 ' öğesine dönüştürme, olası veri kaybı

Bir tamsayı türü, daha küçük bir tamsayı türüne dönüştürülür. Bu, *Type1* ' in `int` ve *type2* `int`daha küçükse bir düzey 4 uyarıdır. Aksi takdirde, bir düzey 3 (`unsigned int`türünde bir değişkene [__int64](../../cpp/int8-int16-int32-int64.md) türünde bir değer atanır). Olası bir veri kaybı oluşmuş olabilir.

C4244 alırsanız, programınızı uyumlu türler kullanacak şekilde değiştirmeniz veya kodunuzda bir mantık eklemeniz gerekir, bu da olası değerlerin aralığının her zaman kullandığınız türlerle uyumlu olmasını sağlar.

C4244 2. düzeyde de tetikde olabilir; daha fazla bilgi için bkz. [Derleyici Uyarısı (düzey 2) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md) .

Örtük dönüştürmeler nedeniyle dönüştürmeye bir sorun olabilir.

Aşağıdaki örnek C4244 oluşturur:

```cpp
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

Daha fazla bilgi için bkz. [normal aritmetik dönüştürmeler](../../c-language/usual-arithmetic-conversions.md).

```cpp
// C4244_level3.cpp
// compile with: /W3
int main() {
   __int64 i = 8;
   unsigned int ii = i;   // C4244
}
```

32-bit hedefler için derleme yaparken uyarı oluşturmamayan 64-bit hedefler için kod oluştururken uyarı C4244 meydana gelebilir. Örneğin, işaretçiler arasındaki fark, 32-bit platformlarda 32 bitlik bir miktardır, ancak 64-bit platformlarda 64 bitlik bir miktardır.

Aşağıdaki örnek 64-bit hedefler için derlendiğinde C4244 oluşturur:

```cpp
// C4244_level3_b.cpp
// compile with: /W3
int main() {
   char* p1 = 0;
   char* p2 = 0;
   int x = p2 - p1;   // C4244
}
```
