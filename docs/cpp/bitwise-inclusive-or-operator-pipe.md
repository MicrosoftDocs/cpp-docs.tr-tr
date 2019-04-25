---
title: 'Bit düzeyinde kapsamlı OR işleci: |'
ms.date: 06/14/2018
f1_keywords:
- bitor
- '|'
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 848bf3b2ec61084b59ab5b1ee6807f6066a4675e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184299"
---
# <a name="bitwise-inclusive-or-operator-"></a>Bit düzeyinde kapsamlı OR işleci: |

## <a name="syntax"></a>Sözdizimi

> *İfade1* **|** *expression2*

## <a name="remarks"></a>Açıklamalar

Bit düzeyinde kapsamlı OR işleci (**&#124;**) karşılık gelen bit ikinci işlenenin ilk işlenenin her bitini karşılaştırır. Her iki bit 1 ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç bit 0 olarak ayarlanır.

Bit düzeyinde kapsamlı OR işlecinin her iki işleneni de, integral türde olmalıdır. Olağan aritmetik dönüştürmeler ele [standart dönüştürmeler](standard-conversions.md) işlenenlere uygulanır.

## <a name="operator-keyword-for-124"></a>İçin işleç anahtar sözcüğü&#124;

**Bitor** işlecidir öğesinin metin eşdeğeridir **&#124;**. Erişmenin iki yöntemi vardır **bitor** programlarınızda işleci: üstbilgi dosyasını dahil \<iso646.h >, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.

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