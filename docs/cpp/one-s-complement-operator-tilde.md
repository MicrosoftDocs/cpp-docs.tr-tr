---
title: 'Bir&#39;s tamamlama işleci: ~'
ms.date: 11/04/2016
f1_keywords:
- "~"
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: d8fb8ca56932669ff85646f2aa0c10691122013b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245042"
---
# <a name="one39s-complement-operator-"></a>Bir&#39;s tamamlama işleci: ~

## <a name="syntax"></a>Sözdizimi

```
~ cast-expression
```

## <a name="remarks"></a>Açıklamalar

Bazen "bit düzeyinde tamamlayıcı" işleci olarak anılan birinin tamamlayıcı işleci (`~`), bit düzeyinde birinin kendi işleneninin tamamlayıcısını oluşturur. Yani, işlenende 1 olan her bit sonuçta 0'dır. Buna karşılık, işlenende 0 olan her bit sonuçta 1'dir. Birinin tamamlayıcı işlecinin işleneni integral türünde olmalıdır.

## <a name="operator-keyword-for-"></a>~ için İşleç Anahtar Sözcüğü

**Compl** işlecidir öğesinin metin eşdeğeridir `~`. Erişmenin iki yöntemi vardır **compl** programlarınızda işleci: üstbilgi dosyasını dahil `iso646.h`, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md).

## <a name="example"></a>Örnek

```cpp
// expre_One_Complement_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main () {
   unsigned short y = 0xFFFF;
   cout << hex << y << endl;
   y = ~y;   // Take one's complement
   cout << hex << y << endl;
}
```

Bu örnekte, `y`'ye atanan yeni değer işaretsiz 0xFFFF değerinin veya 0x0000 için birinin tamamlayıcısıdır.

İntegral yükseltme, iç işlenenlerde gerçekleştirilir ve ortaya çıkan tür işlenenin yükseltildiği türdür. Bkz: [standart dönüştürmeler](standard-conversions.md) yükseltmenin nasıl yapılacağı hakkında daha fazla bilgi.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Birli Aritmetik İşleçler](../c-language/unary-arithmetic-operators.md)