---
title: Üye erişim işleçleri:. ve -&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c02183b3dc03c785ef5a6a08da80dd8435288b0a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112778"
---
# <a name="member-access-operators--and--gt"></a>Üye erişim işleçleri:. ve -&gt;

## <a name="syntax"></a>Sözdizimi

```
postfix-expression . name
postfix-expression -> name
```

## <a name="remarks"></a>Açıklamalar

Üye erişim işleçleri **.** ve **->** yapılar, birleşimler ve sınıfların üyelerine başvurmak için kullanılır. Üye erişimi ifadeleri, seçili üyenin türü ve değerine sahip.

Üye erişimi ifadeleri iki tür vardır:

1. İlk biçiminde *sonek ifadesi* yapısı, sınıfı ya da birleşim türünün bir değeri temsil eder ve *adı* belirtilen yapı, birlik veya üye adları. İşlem, değeri *adı* ve bir l-değeri ise *sonek ifadesi* bir l değeridir.

1. İkinci biçiminde *sonek ifadesi* yapı, birleşim veya sınıf, bir işaretçiyi temsil eder ve *adı* belirtilen yapı, birlik veya üye adları. Değer budur *adı* ve bir l değeridir. **->** İşleci işaretçinin başvurusunu kaldırır. Bu nedenle, ifadeleri `e->member` ve `(*e).member` (burada *e* bir işaretçiyi temsil eder) aynı sonuçları (olmadığı dışında işleçleri **->** veya <strong>\*</strong> aşırı).

## <a name="example"></a>Örnek

Aşağıdaki örnek, üye erişim işleci, her iki biçimi gösterir.

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