---
title: "Üye erişimi işleçleri:. ve -&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- .
- ->
dev_langs:
- C++
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4dc08bce80d27493a8a13ac24bce7011282d7cd3
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="member-access-operators--and--gt"></a>Üye erişimi işleçleri:. ve -&gt;
## <a name="syntax"></a>Sözdizimi  
  
```  
postfix-expression . name  
postfix-expression -> name  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye erişimi işleçleri **.** ve  **->**  yapılar, birleşimler ve sınıflar üyelerine başvurmak için kullanılır. Üye erişimi ifadeleri seçilen üye türü ve değeri sahip.  
  
 Üye erişimi ifadeleri iki tür vardır:  
  
1.  İlk formunda *sonek ifade* yapısı, sınıf veya birleşim türü değerini temsil eder ve *adı* belirtilen yapısı, UNION veya sınıf üyesi adları. İşlemi, değeri *adı* ve bir l-değeri ise *sonek ifade* l-değeri.  
  
2.  İkinci formunda *sonek ifade* bir işaretçi yapısı, UNION veya sınıfı temsil eder ve *adı* belirtilen yapısı, UNION veya sınıf üyesi adları. Değer budur *adı* ve bir l-değeri.  **->**  İşleci dereferences işaretçi. Bu nedenle, ifadeler * e * **->**  `member` ve **(\****e***)**.`member` (burada *e* bir işaretçi temsil eder) verim aynı sonuçları (olmadığı dışında işleçleri  **->**  veya  **\***  aşırı yüklenmiş olan iş).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, her iki üye erişimi işleci biçimlerinin gösterir.  
  
```  
// expre_Selection_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Date {  
   Date(int i, int j, int k) : day(i), month(j), year(k){}  
   int month;  
   int day;  
   int year;  
};  
  
int main() {  
   Date mydate(1,1,1900);  
   mydate.month = 2;     
   cout  << mydate.month << "/" << mydate.day  
         << "/" << mydate.year << endl;  
  
   Date *mydate2 = new Date(1,1,2000);  
   mydate2->month = 2;  
   cout  << mydate2->month << "/" << mydate2->day  
         << "/" << mydate2->year << endl;  
   delete mydate2;  
}  
```  
  
```Output  
2/1/1900  
2/1/2000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonek ifadeleri](../cpp/postfix-expressions.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Sınıflar ve yapılar](../cpp/classes-and-structs-cpp.md)   
 [Yapı ve Birleşim Üyeleri](../c-language/structure-and-union-members.md)