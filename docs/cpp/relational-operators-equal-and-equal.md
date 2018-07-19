---
title: 'İlişkisel işleçler: &lt;, &gt;, &lt;=, ve &gt;= | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- <
- '>'
dev_langs:
- C++
helpviewer_keywords:
- '> operator'
- less than operator
- relational operators [C++], syntax
- '>= operator'
- greater than or equal to operators [C++]
- greater than operators [C++]
- < operator
- less than or equal to operator
- <= operator
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56372764c70498aec4ccf7b23fc7d074d1df179e
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948113"
---
# <a name="relational-operators-lt-gt-lt-and-gt"></a>İlişkisel işleçler: &lt;, &gt;, &lt;=, ve &gt;=
## <a name="syntax"></a>Sözdizimi  
  
```  
expression < expression  
expression > expression  
expression <= expression  
expression >= expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İkili ilişkisel işleçleri aşağıdaki ilişkileri belirler:  
  
-   Küçüktür (**\<**)  
  
-   Büyüktür (**>**)  
  
-   Küçük veya eşittir (**\<=**)  
  
-   Büyüktür veya eşittir (**>=**)  
  
 İlişkisel işleçler, soldan sağa ilişkilendirilebilirlik vardır. Her iki işleneni de operatörler olmalıdır aritmetik veya işaretçi türü. Bunlar türü değerlerinin yield **bool**. Döndürülen değer **false** (0) ifade ilişkide Aksi takdirde false ise, döndürülen değer **true** (1).  
  
## <a name="example"></a>Örnek  
  
```cpp 
// expre_Relational_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << "The true expression 3 > 2 yields: "  
         << (3 > 2) << endl  
         << "The false expression 20 < 10 yields: "  
         << (20 < 10) << endl;  
}  
```  
  
 Önceki örnekte yer alan ifadeleri parantez içinde olduğundan alınmalıdır akış ekleme operatörü (**<<**) ilişkisel işleçler daha yüksek bir önceliğe sahiptir. Bu nedenle, ilk ifade parantezler olmadan olarak değerlendirilmesi:  
  
```cpp 
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");  
```  
  
 Olağan aritmetik dönüştürmeler ele [standart dönüştürmeler](standard-conversions.md) aritmetik türlerin işlenenlerini için uygulanır.  
  
## <a name="comparing-pointers"></a>İşaretçileri Kıyaslama  
 Nesneleri aynı türde iki işaretçileri karşılaştırıldığında sonucu programın adres alanında işaret nesnelerin konumu tarafından belirlenir. İşaretçileri de karşılaştırılabilir 0 veya işaretçi türü void döndüren bir sabit ifadesine *. İşaretçi karşılaştırması türünde bir işaretçi karşı void yapılması durumunda \*, diğer işaretçiyi void türüne örtük olarak dönüştürülür \*. Ardından karşılaştırma yapılır.  
  
 Sürece farklı türden iki işaretçisi karşılaştırılamaz:  
  
-   Bir tür diğer türden türetilmiş bir sınıf türüdür.  
  
-   En az bir işaretçi açıkça dönüştürülür (void türüne dönüştürme) *. (Diğer bir işaretçiyi void türüne örtük olarak dönüştürülür \* dönüştürme için.)  
  
 Karşılaştırılacak aynı nesneye işaret eden iki işaretçi aynı türden eşit garanti edilir. İki nesnenin statik olmayan üye işaretçileri karşılaştırıldığında, aşağıdaki kurallar geçerlidir:  
  
-   Sınıf türü bir birleşim değil ise ve iki üyesi tarafından ayrılmış değil ise bir *erişim belirticisi*, korumalı veya private, public gibi bildirilen üye işaretçisinin son bildirilen üye işaretçisinin büyüktür karşılaştırır daha önce.  
  
-   İki üyesi tarafından ayrılmış ise bir *erişim belirticisi*, sonuçlar tanımsızdır.  
  
-   Sınıf türü UNION varsa, bu birleşimde farklı veri üyeleri için işaretçiler eşit karşılaştırın.  
  
 İki dizinin aynı öğeleri ya da dizinin sonundan öğesi bir işaret ederseniz, daha yüksek alt simge olan nesneye işaretçi yüksek karşılaştırır. Yalnızca işaretçiler aynı dizisindeki nesnelere veya konuma bir dizinin bitişini geçen başvurduğunuzda işaretçileri karşılaştırma geçerli garanti edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C İlişkisel ve Eşitlik İşleçleri](../c-language/c-relational-and-equality-operators.md)