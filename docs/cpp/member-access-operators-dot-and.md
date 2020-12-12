---
description: "Daha fazla bilgi edinin: üye erişim Işleçleri:. '&gt;"
title: Üye erişim Işleçleri:. '&gt;
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
ms.openlocfilehash: 242ded47c22e0cacfc09659fca275c9e412c004e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276822"
---
# <a name="member-access-operators--and--gt"></a>Üye erişim Işleçleri:. '&gt;

## <a name="syntax"></a>Syntax

```
postfix-expression . name
postfix-expression -> name
```

## <a name="remarks"></a>Açıklamalar

Üye erişim işleçleri **.** ve **->** yapıların, birleşimlerin ve sınıfların üyelerine başvurmak için kullanılır. Üye erişim ifadelerinde seçili üyenin değeri ve türü vardır.

İki üye erişim ifadesi biçimi vardır:

1. İlk formda, *sonek ifadesi* struct, Class veya Union türündeki bir değeri temsil eder ve *ad* adları belirtilen yapının, birleşimin veya sınıfın bir üyesi olarak belirtilir. İşlemin değeri *ad* olur ve *sonek ifadesi* bir l-değeri ise bir l değeri olur.

1. İkinci formda, *sonek ifadesi* bir yapıya, birleşime veya sınıfa yönelik bir işaretçi ve *ad* adları belirtilen yapının, birleşimin veya sınıfın bir üyesini temsil eder. Değer, *ad* ve bir l değeri olur. **->** İşleci, işaretçiyi referans olarak kaldırır. Bu nedenle, ifadeler `e->member` ve `(*e).member` ( *e* bir işaretçiyi temsil eden), özdeş sonuçlar (operatörler **->** veya aşırı yüklenmiş olduğu durumlar dışında <strong>\*</strong> ) sonucu verir.

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

[Sonek Ifadeleri](../cpp/postfix-expressions.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)<br/>
[Yapı ve birleşim üyeleri](../c-language/structure-and-union-members.md)
