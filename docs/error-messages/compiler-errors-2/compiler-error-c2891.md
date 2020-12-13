---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2891'
title: Derleyici hatası C2891
ms.date: 11/04/2016
f1_keywords:
- C2891
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
ms.openlocfilehash: e546340d0ba035da50dd36b18b870b565b6e1bc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337433"
---
# <a name="compiler-error-c2891"></a>Derleyici hatası C2891

' Parameter ': bir şablon parametresinin adresi alınamaz

Bir lvalue olmadığı takdirde şablon parametresinin adresini alamazsınız. Tür parametreleri hiçbir adresi olmadığı için lvalues değildir. Lvalues olmayan şablon parametresi listelerindeki tür olmayan değerler de bir adrese sahip değil. Bu, parametre parametresi olarak geçirilen değer şablon bağımsız değişkeninin derleyicinin ürettiği bir kopyası olduğundan, derleyici hatası C2891 neden olan kodun bir örneğidir.

```
template <int i> int* f() { return &i; }
```

Başvuru türleri gibi lvalues olan şablon parametrelerinin adresleri alınmış olabilir.

```
template <int& r> int* f() { return &r; }
```

Bu hatayı düzeltmek için, bir lvalue olmadığı takdirde şablon parametresinin adresini kullanmayın.
