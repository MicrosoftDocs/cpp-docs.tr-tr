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
ms.openlocfilehash: 777f253925caf38647863bdaa93fde8d5a03e3f9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177722"
---
# <a name="one39s-complement-operator-"></a>Bir&#39;s tamamlama işleci: ~

## <a name="syntax"></a>Sözdizimi

```
~ cast-expression
```

## <a name="remarks"></a>Açıklamalar

Bazen "bit düzeyinde tamamlayıcı" işleci olarak anılan birinin tamamlayıcı işleci (`~`), bit düzeyinde birinin kendi işleneninin tamamlayıcısını oluşturur. Yani, işlenende 1 olan her bit sonuçta 0'dır. Buna karşılık, işlenende 0 olan her bit sonuçta 1'dir. Birinin tamamlayıcı işlecinin işleneni integral türünde olmalıdır.

## <a name="operator-keyword-for-"></a>~ için İşleç Anahtar Sözcüğü

**Compl** işleci `~`metin eşdeğeridir. Programlarınızdaki **compl** işlecine erişmenin iki yolu vardır: `iso646.h`üst bilgi dosyasını dahil edin veya [/za](../build/reference/za-ze-disable-language-extensions.md)ile derleyin.

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

İntegral yükseltme, iç işlenenlerde gerçekleştirilir ve ortaya çıkan tür işlenenin yükseltildiği türdür. Yükseltmenin nasıl yapıldığı hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Birli Aritmetik İşleçler](../c-language/unary-arithmetic-operators.md)
