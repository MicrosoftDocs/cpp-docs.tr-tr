---
title: "İlişkisel işleçler: &lt;, &gt;, &lt;= ve &gt;= | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- <
- '>'
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 25ff07e3f80d51a0bfe06ae3b1c6dc7d5728bcf0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="relational-operators-lt-gt-lt-and-gt"></a>İlişkisel işleçler: &lt;, &gt;, &lt;= ve&gt;=
## <a name="syntax"></a>Sözdizimi  
  
```  
expression < expression  
expression > expression  
expression <= expression  
expression >= expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İkili ilişkisel işleçler aşağıdaki ilişkileri belirleyin:  
  
-   Küçüktür (**\<**)  
  
-   Büyüktür (**>**)  
  
-   Küçük veya eşit (**\<=**)  
  
-   Büyüktür veya eşittir (**>=**)  
  
 İlişkisel işleçler soldan sağa birleşim vardır. İlişkisel işleçler hem işlenenleri olmalıdır aritmetik veya işaretçi türü. Türü değerleri verim `bool`. Döndürülen değer **false** (0) ifade ilişkisinde aksi false ise, döndürülen değer olan **true** (1).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
 Önceki örnekte ifadeleri parantez içinde olduğundan alınmalıdır akış ekleme işleci (**<<**) ilişkisel işleçleri daha yüksek önceliğe sahiptir. Bu nedenle, parantezler olmadan ilk ifade olarak değerlendirilmesi:  
  
```  
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");  
```  
  
 Olağan aritmetik dönüştürmeler ele [standart dönüşümler](standard-conversions.md) aritmetik türündeki işlenenler için uygulanır.  
  
## <a name="comparing-pointers"></a>İşaretçileri karşılaştırma  
 Aynı türde nesne iki işaretçileri karşılaştırıldığında, sonuç programın adres alanında işaret nesnelerin konumu tarafından belirlenir. İşaretçileri de karşılaştırılabilir 0 veya bir işaretçi türü void sabit bir ifade için *. İşaretçi karşılaştırması türünde bir işaretçi karşı void yapılırsa, \*, diğer işaretçiyi void türüne örtük olarak dönüştürülür \*. Ardından karşılaştırma yapılır.  
  
 Farklı türlerdeki iki işaretçileri sürece karşılaştırılamaz:  
  
-   Diğer türden türetilmiş bir sınıf türü bir türüdür.  
  
-   İşaretçileri en az biri açıkça dönüştürülür (void türüne dönüştürme) *. (Diğer işaretçiyi void türüne örtük olarak dönüştürülür \* dönüştürme işlemi için.)  
  
 Aynı nesneye işaret iki işaretçileri aynı türde karşılaştırmak için eşit garanti. Bir nesnenin statik olmayan üye iki işaretçileri karşılaştırıldığında, aşağıdaki kurallar geçerlidir:  
  
-   Sınıf türü UNION değilse ve iki üyeleri tarafından ayrılmış değil ise bir *erişim belirticisi*, korumalı veya özel, genel gibi bildirilen üye işaretçisine son bildirilen üye işaretçisine büyük karşılaştırır daha önce.  
  
-   İki üyeleri tarafından ayrılmış ise bir *erişim belirticisi*, sonuçları tanımlanmamış.  
  
-   Sınıf türü UNION ise, bu Birleşimdeki farklı veri üye işaretçileri eşit karşılaştırın.  
  
 İki işaretçileri aynı dizideki öğeler veya dizinin sonuna ötesinde öğesi bir işaret, daha yüksek alt simge nesnesiyle işaretçisine yüksek karşılaştırır. Yalnızca işaretçileri aynı dizi nesneleri veya konuma bir dizinin sonuna geçmiş başvurduğunuzda işaretçileri karşılaştırma geçerli garanti edilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C ilişkisel ve eşitlik işleçleri](../c-language/c-relational-and-equality-operators.md)