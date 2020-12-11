---
description: 'Daha fazla bilgi edinin: sizeof Işleci (C)'
title: sizeof İşleci (C)
ms.date: 11/04/2016
f1_keywords:
- sizeof
helpviewer_keywords:
- sizeof operator
ms.assetid: 70826d03-3451-41e4-bebb-a820ae66d53f
ms.openlocfilehash: a67a7068d6fa14ad3fc35fc9909251ff7e304341
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162410"
---
# <a name="sizeof-operator-c"></a>sizeof İşleci (C)

**`sizeof`** İşleci, işlenen türünde bir nesneyi depolamak için gereken depolama alanı miktarını bayt olarak verir. Bu işleç, programlarınızda makineye bağımlı veri boyutları belirtmekten kaçınmanızı sağlar.

## <a name="syntax"></a>Syntax

```
sizeof unary-expression
sizeof ( type-name )
```

## <a name="remarks"></a>Açıklamalar

İşlenen, *birli ifade* veya tür atama ifadesi (yani parantez içine alınmış bir tür Belirleyicisi) olan bir tanıtıcıdır. *Birli ifade* , bir bit alanı nesnesini, tamamlanmamış bir türü veya bir işlev göstergesini temsil edemez. Sonuç, işaretsiz bir tamsayı sabitidir. Standart üst bilgi STDDEF. H bu türü **size_t** olarak tanımlar.

**`sizeof`** İşleci bir dizi tanımlayıcısına uyguladığınızda, sonuç dizi tanımlayıcısı tarafından temsil edilen işaretçinin boyutu yerine tüm dizinin boyutudur.

**`sizeof`** İşleci bir yapıya veya birleşim türü adına veya yapı ya da birleşim türü tanımlayıcısına uyguladığınızda, sonuç, iç ve sondaki doldurma dahil olmak üzere yapıda veya birleşimde bayt sayısıdır. Bu boyut, yapı veya bellek sınırları üzerindeki birleşim üyelerini hizalamak için kullanılan iç ve sondaki doldurmayı içerebilir. Bu şekilde, sonuç tek tek üyelerin depolama gereksinimlerini toplayarak hesaplanan boyuta karşılık gelmeyebilir.

Boyutlandırılmış olmayan bir dizi bir yapının son öğesi ise, **`sizeof`** işleci dizi olmadan yapının boyutunu döndürür.

```
buffer = calloc(100, sizeof (int) );
```

Bu örnek, **`sizeof`** **`int`** adlı bir çalışma zamanı işlevine bağımsız değişken olarak makineler arasında farklılık gösteren bir olan boyutunu geçirmek için işlecini kullanır `calloc` . İşlev tarafından döndürülen değer `buffer` içinde depolanır.

```
static char *strings[] = {
      "this is string one",
      "this is string two",
      "this is string three",
   };
const int string_no = ( sizeof strings ) / ( sizeof strings[0] );
```

Bu örnekte, `strings` işaretçilerin bir dizisidir **`char`** . İşaretçilerin sayısı dizideki öğelerin sayısıdır, ancak belirtilmemiştir. **`sizeof`** Dizideki öğe sayısını hesaplamak için işlecini kullanarak işaretçilerin sayısını kolayca saptayabilirsiniz. **`const`** Tamsayı değeri `string_no` Bu sayı olarak başlatılır. **`const`** Değer olduğundan, `string_no` değiştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[C Işleçleri](c-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
