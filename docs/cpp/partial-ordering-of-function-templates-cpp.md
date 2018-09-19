---
title: (C++) işlev şablonlarının kısmi sıralanması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5b550cd0b76aa0a2e061536ae6bb0ea61063909
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087753"
---
# <a name="partial-ordering-of-function-templates-c"></a>İşlev Şablonlarının Kısmi Sıralanması (C++)

İşlev çağrısının bağımsız değişken listesiyle eşleşen birden fazla işlev şablonu kullanılabilir. C++, hangi işlevin çağrılması gerektiğini belirtmek için işlev şablonlarının kısmi bir sıralamasını tanımlar. Sıralama, eşit şekilde özel olarak kabul edilen bazı şablonlar olabileceği için kısmidir.

Derleyici, olası eşleşmeler arasından en özel şablon işlevini seçer. Örneğin, bir işlev şablonu bir türünü alan __T__ve başka bir işlev şablonu alma __T\*__  kullanılabilir __T\*__  sürüm söyledi Daha fazla özelleştirilmiş ve genel tercih edilen __T__ hem izin verilen eşleşme olsa bağımsız değişken işaretçi türünde olduğunda sürümü.

Bir işlev şablonu adayının daha özel olup olmadığını belirlemek için aşağıdaki işlemi kullanın:

1. T1 ve T2 işlev şablonlarını dikkate alın.

2. T1'deki parametreleri kuramsal bir benzersiz tür olan X ile değiştirin.

3. T1'deki parametre listesinde, T2'nin parametre listesi için geçerli bir şablon olup olmadığına bakın. Örtük dönüştürmeleri yoksayın.

4. Aynı işlemi T1 ve T2'yi ters çevirerek tekrarlayın.

5. Bir şablon diğer şablon için geçerli bir şablon bağımsız değişken listesiyse, ancak bunun tersi doğru değilse, bu şablon diğer şablona göre daha az özel olarak değerlendirilir. Önceki adım form geçerli bağımsız değişkenleri birbirine kullanan iki şablon, ardından bunların eşit şekilde özel olarak kabul edilir ve belirsiz bir çağrı sonuçları bunları kullanmak istediğinizde.

6. Bu kuralları kullanarak:

     1. Belirli bir tür için bir şablonu özelleştirme, genel türden bir bağımsız değişken alan özelleştirmeye göre daha özeldir.

     2. Bir şablon yalnızca alma __T\*__  yalnızca bir alan daha fazla özelleştirilmiş __T__, çünkü bir kuramsal türü __X\*__  için geçerli bir bağımsız değişken bir __T__ şablon bağımsız değişkeni, ancak __X__ için geçerli bir bağımsız değişken değil bir __T\*__  şablon bağımsız değişkeni.

     3. __const T__ göre daha özeldir __T__, çünkü __const X__ için geçerli bir bağımsız değişken bir __T__ şablon bağımsız değişkeni, ancak __X__ olduğu değil geçerli bir bağımsız değişken için bir __const T__ şablon bağımsız değişkeni.

     4. __const T\*__  göre daha özeldir __T\*__, çünkü __const X\*__  için geçerli bir bağımsız değişken bir __T\*__  şablon bağımsız değişkeni, ancak __X\*__  için geçerli bir bağımsız değişken değil bir __const T\*__  şablon bağımsız değişkeni.

## <a name="example"></a>Örnek

Aşağıdaki örnek, standart belirtildiği gibi çalışır:

```cpp
// partial_ordering_of_function_templates.cpp
// compile with: /EHsc
#include <iostream>

extern "C" int printf(const char*,...);
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