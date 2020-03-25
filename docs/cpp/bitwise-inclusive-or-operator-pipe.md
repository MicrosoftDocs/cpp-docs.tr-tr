---
title: 'Bit düzeyinde kapsamlı OR işleci: |'
ms.date: 06/14/2018
f1_keywords:
- '|'
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 38def2b1ac585c751699227d2a065b45145d290d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190761"
---
# <a name="bitwise-inclusive-or-operator-"></a>Bit düzeyinde kapsamlı OR işleci: |

## <a name="syntax"></a>Sözdizimi

> *ifade1* **|** *İfade2*

## <a name="remarks"></a>Açıklamalar

Bit düzeyinde kapsamlı OR işleci ( **&#124;** ), ilk işleneninin her bir bitini ikinci işleneninin karşılık gelen bitine karşılaştırır. Her iki bit de 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç biti 0 olarak ayarlanır.

Bit düzeyinde kapsamlı OR işlecinin her iki işleneni de, integral türde olmalıdır. [Standart dönüştürmelerde](standard-conversions.md) ele alınan Olağan aritmetik dönüştürmeler işlenenlere uygulanır.

## <a name="operator-keyword-for-124"></a>İçin işleç anahtar sözcüğü&#124;

**Bitor** işleci, öğesinin **&#124;** metin eşdeğeridir. Programlarınızdaki **bitor** işlecine erişmenin iki yolu vardır: \<iso646. h > üst bilgi dosyasını dahil edin veya [/za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneğiyle derleyin.

## <a name="example"></a>Örnek

```cpp
// expre_Bitwise_Inclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise inclusive OR
#include <iostream>
using namespace std;

int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Bit Düzeyinde İşleçler](../c-language/c-bitwise-operators.md)
