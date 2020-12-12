---
description: 'Daha fazla bilgi edinin: yöneltme Işleci: *'
title: 'Yönlendirme İşleci: *'
ms.date: 11/04/2016
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
ms.openlocfilehash: d82e65676178fcfc9a62b10a780360c0c69d0d2b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113915"
---
# <a name="indirection-operator-"></a>Yönlendirme İşleci: *

## <a name="syntax"></a>Syntax

```
* cast-expression
```

## <a name="remarks"></a>Açıklamalar

Birli yöneltme işleci ( <strong>\*</strong> ) bir işaretçiye başvurur; diğer bir deyişle, bir işaretçi değerini bir l değerine dönüştürür. Yöneltme işlecinin işleneni, bir tür işaretçisi olmalıdır. Yöneltme ifadesinin sonucu, işaretçi türünün türetildiği türüdür. <strong>\*</strong>Bu bağlamda işlecinin kullanımı, çarpının, çarpma olan bir ikili işleç olarak farklıdır.

İşlenen bir işleve işaret ediyorsa, sonuç bir işlev göstergesidir. Bir depolama konumuna işaret ediyorsa, sonuç depolama konumunu gösteren l değeridir.

Yöneltme işleci, işaretçilere yönelik işaretçileri başvurusu için üst üste kullanılabilir. Örneğin:

```cpp
// expre_Indirection_Operator.cpp
// compile with: /EHsc
// Demonstrate indirection operator
#include <iostream>
using namespace std;
int main() {
   int n = 5;
   int *pn = &n;
   int **ppn = &pn;

   cout  << "Value of n:\n"
         << "direct value: " << n << endl
         << "indirect value: " << *pn << endl
         << "doubly indirect value: " << **ppn << endl
         << "address of n: " << pn << endl
         << "address of n via indirection: " << *ppn << endl;
}
```

İşaretçi değeri geçersizse, sonuç tanımsızdır. Aşağıdaki liste, işaretçi değerini geçersiz kılan en yaygın koşulların bazılarını içermektedir.

- İşaretçi, bir null işaretçidir.

- İşaretçi, başvuru sırasında görünür olmayan yerel bir öğrenin adresini belirtir.

- İşaretçi, işaret edilen nesnenin türü için uygun olmayan bir şekilde hizalanmış bir adresi belirtir.

- İşaretçi, yürütülen program tarafından kullanılmayan bir adresi belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Address-of İşleci: &](../cpp/address-of-operator-amp.md)<br/>
[Yöneltme ve adres Işleçleri](../c-language/indirection-and-address-of-operators.md)
