---
title: İşlev Şablonlarının Kısmi Sıralanması (C++)
ms.date: 07/30/2019
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
ms.openlocfilehash: 0c4f11b4b3e02504c4786ea34441362b542959d6
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682419"
---
# <a name="partial-ordering-of-function-templates-c"></a>İşlev Şablonlarının Kısmi Sıralanması (C++)

İşlev çağrısının bağımsız değişken listesiyle eşleşen birden fazla işlev şablonu kullanılabilir. C++, hangi işlevin çağrılması gerektiğini belirtmek için işlev şablonlarının kısmi bir sıralamasını tanımlar. Sıralama, eşit şekilde özel olarak kabul edilen bazı şablonlar olabileceği için kısmidir.

Derleyici, olası eşleşmeler arasından en özel şablon işlevini seçer. Örneğin, bir işlev şablonu bir tür `T` alırsa ve kullanılabilir başka bir işlev şablonu `T*` varsa, `T*` sürüm daha özelleştirilmiş olarak kabul edilir. Bağımsız değişken bir işaretçi türü olduğunda `T` , her ikisi de izin verilen eşleşmeler olsa da, genel sürüm üzerinden tercih edilir.

Bir işlev şablonu adayının daha özel olup olmadığını belirlemek için aşağıdaki işlemi kullanın:

1. T1 ve T2 işlev şablonlarını dikkate alın.

1. T1'deki parametreleri kuramsal bir benzersiz tür olan X ile değiştirin.

1. T1'deki parametre listesinde, T2'nin parametre listesi için geçerli bir şablon olup olmadığına bakın. Örtük dönüştürmeleri yoksayın.

1. Aynı işlemi T1 ve T2'yi ters çevirerek tekrarlayın.

1. Bir şablon diğer şablon için geçerli bir şablon bağımsız değişken listese, ancak bu değer doğru değilse, bu şablon diğer şablondan daha az özelleştirilmiş olarak değerlendirilir. Önceki adımı kullanarak her iki şablon da bir diğeri için geçerli bağımsız değişkenler oluşturduklarında, eşit olarak özelleştirilmiş olarak değerlendirilir ve bunları kullanmaya çalıştığınızda belirsiz bir çağrı sonucu oluşur.

1. Bu kuralları kullanarak:

   1. Belirli bir tür için bir şablonu özelleştirme, genel türden bir bağımsız değişken alan özelleştirmeye göre daha özeldir.

   1. Bir şablon bağımsız değişkeni `T*` `X*` `T` için`X` geçerli bir bağımsız değişken olduğundan, yalnızca bir alma işlemi yalnızca bir tane daha özelleştirilmiştir. `T` `T*`şablon bağımsız değişkeni.

   1. `const T``T`, bir `const T` `const X` `X` şablon bağımsız değişkeni için geçerli bir bağımsız değişken olduğundan, ancak şablon bağımsız değişkeni için geçerli bir bağımsız değişken olmadığından, daha özelleştirilmiş. `T`

   1. `const T*``T*`, bir `const T*` `const X*` `X*` şablon bağımsız değişkeni için geçerli bir bağımsız değişken olduğundan, ancak şablon bağımsız değişkeni için geçerli bir bağımsız değişken olmadığından, daha özelleştirilmiş. `T*`

## <a name="example"></a>Örnek

Aşağıdaki örnek, standart olarak belirtilen şekilde çalışmaktadır:

```cpp
// partial_ordering_of_function_templates.cpp
// compile with: /EHsc
#include <iostream>

template <class T> void f(T) {
   printf_s("Less specialized function called\n");
}

template <class T> void f(T*) {
   printf_s("More specialized function called\n");
}

template <class T> void f(const T*) {
   printf_s("Even more specialized function for const T*\n");
}

int main() {
   int i =0;
   const int j = 0;
   int *pi = &i;
   const int *cpi = &j;

   f(i);   // Calls less specialized function.
   f(pi);  // Calls more specialized function.
   f(cpi); // Calls even more specialized function.
   // Without partial ordering, these calls would be ambiguous.
}
```

### <a name="output"></a>Çıkış

```Output
Less specialized function called
More specialized function called
Even more specialized function for const T*
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlev Şablonları](../cpp/function-templates.md)
