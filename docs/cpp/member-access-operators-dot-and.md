---
title: Üye erişim Işleçleri:. ve-&gt;
ms.date: 11/04/2016
f1_keywords:
- .
- ->
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
ms.openlocfilehash: 05bab55e1646783e0f8ab9b414d608c912f60a0f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178021"
---
# <a name="member-access-operators--and--gt"></a>Üye erişim Işleçleri:. ve-&gt;

## <a name="syntax"></a>Sözdizimi

```
postfix-expression . name
postfix-expression -> name
```

## <a name="remarks"></a>Açıklamalar

Üye erişim işleçleri **.** ve **->** yapıların, birleşimlerin ve sınıfların üyelerine başvurmak için kullanılır. Üye erişim ifadelerinde seçili üyenin değeri ve türü vardır.

İki üye erişim ifadesi biçimi vardır:

1. İlk formda, *sonek ifadesi* struct, Class veya Union türündeki bir değeri temsil eder ve *ad* adları belirtilen yapının, birleşimin veya sınıfın bir üyesi olarak belirtilir. İşlemin değeri *ad* olur ve *sonek ifadesi* bir l-değeri ise bir l değeri olur.

1. İkinci formda, *sonek ifadesi* bir yapıya, birleşime veya sınıfa yönelik bir işaretçi ve *ad* adları belirtilen yapının, birleşimin veya sınıfın bir üyesini temsil eder. Değer, *ad* ve bir l değeri olur. **->** işleci işaretçiye başvurur. Bu nedenle, `e->member` ve `(*e).member` ifadesi ( *e* bir işaretçiyi temsil eden), aynı sonuçları (işleçler **->** veya <strong>\*</strong> aşırı yüklendiği durumlar dışında) oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, her iki üye erişim işlecinin biçimini gösterir.

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[Son Ek İfadeleri](../cpp/postfix-expressions.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)<br/>
[Yapı ve Birleşim Üyeleri](../c-language/structure-and-union-members.md)
