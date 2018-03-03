---
title: "(C++) işlev şablonlarının kısmi sıralaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cddc0f1680a3354276a2135dd28c31a2037a8202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="partial-ordering-of-function-templates-c"></a>İşlev Şablonlarının Kısmi Sıralanması (C++)

İşlev çağrısının bağımsız değişken listesiyle eşleşen birden fazla işlev şablonu kullanılabilir. C++, hangi işlevin çağrılması gerektiğini belirtmek için işlev şablonlarının kısmi bir sıralamasını tanımlar. Sıralama, eşit şekilde özel olarak kabul edilen bazı şablonlar olabileceği için kısmidir.

Derleyici, olası eşleşmeler arasından en özel şablon işlevini seçer. Örneğin, bir işlev şablon türü sürerse __T__ve başka bir işlev şablonu alma __T\*__  kullanılabilir __T\*__  sürüm söyledi Daha fazla özel ve genel tercih edilir olmasını __T__ hem izin verilen eşleşmeleri olacaktır olsa bile bağımsız değişkeni bir işaretçi türü olduğunda sürümü.

Bir işlev şablonu adayının daha özel olup olmadığını belirlemek için aşağıdaki işlemi kullanın:

1. T1 ve T2 işlev şablonlarını dikkate alın.

2. T1'deki parametreleri kuramsal bir benzersiz tür olan X ile değiştirin.

3. T1'deki parametre listesinde, T2'nin parametre listesi için geçerli bir şablon olup olmadığına bakın. Örtük dönüştürmeleri yoksayın.

4. Aynı işlemi T1 ve T2'yi ters çevirerek tekrarlayın.

5. Bir şablon diğer şablon için geçerli bir şablon bağımsız değişken listesiyse, ancak bunun tersi doğru değilse, bu şablon diğer şablona göre daha az özel olarak değerlendirilir. Ne zaman önceki adımı form geçerli bağımsız değişkenleri birbirine kullanarak her iki şablon sonra bunlar eşit oranda özelleştirilmiş kabul edilir ve belirsiz bir çağrı sonuçları değilse bunları kullanmayı dener.

6. Bu kuralları kullanarak:

     1. Belirli bir tür için bir şablonu özelleştirme, genel türden bir bağımsız değişken alan özelleştirmeye göre daha özeldir.

     2. Yalnızca alma şablon __T\*__  yalnızca bir alan daha fazla özel __T__, bir kuramsal türü __X\*__  için geçerli bir bağımsız değişken bir __T__ şablon bağımsız değişken, ancak __X__ için geçerli bir bağımsız değişken değil bir __T\*__  şablon bağımsız değişken.

     3. __const T__ 'den fazla özelleştirilmiş __T__, çünkü __const X__ için geçerli bir bağımsız değişken bir __T__ şablon bağımsız değişken, ancak __X__ için geçerli bir bağımsız değişken değil bir __const T__ şablon bağımsız değişken.

     4. __const T\*__  'den fazla özelleştirilmiş __T\*__, çünkü __const X\*__  için geçerli bir bağımsız değişken bir __T\*__  şablon bağımsız değişken, ancak __X\*__  için geçerli bir bağımsız değişken değil bir __const T\*__  şablon bağımsız değişken.

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
  
```  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.

[İşlev Şablonları](../cpp/function-templates.md)
