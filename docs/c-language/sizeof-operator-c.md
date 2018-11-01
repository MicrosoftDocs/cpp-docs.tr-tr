---
title: sizeof İşleci (C)
ms.date: 11/04/2016
f1_keywords:
- sizeof
helpviewer_keywords:
- sizeof operator
ms.assetid: 70826d03-3451-41e4-bebb-a820ae66d53f
ms.openlocfilehash: 0b5d25e0316c710ce758479ad9417c92201d929d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577638"
---
# <a name="sizeof-operator-c"></a>sizeof İşleci (C)

`sizeof` işleci, işlenen türünde bir nesneyi depolamak için gereken depolama miktarını bayt cinsinden verir. Bu işleç, programlarınızda makine bağımlı veri boyutları belirtmekten kaçının olanak tanır.

## <a name="syntax"></a>Sözdizimi

```
sizeof unary-expression
sizeof ( type-name )
```

## <a name="remarks"></a>Açıklamalar

İşlenen, ya da bir tanımlayıcıdır bir *tekli ifade*, ya da bir tür atama ifadesidir (parantez içine alınmış diğer bir deyişle, bir tür belirleyici). *Tekli ifade* bir bit alanı nesnesini, tamamlanmamış bir türü veya bir işlev göstergesini gösteremez. Sonuç, işaretsiz bir tamsayı sabitidir. Standart üstbilgi STDDEF. Bu türü olarak H tanımlar **size_t**.

`sizeof` işlecini bir dizi tanımlayıcısına uyguladığınızda, sonuç dizi tanımlayıcısı tarafından temsil edilen işaretçinin boyutu değil, tüm dizinin boyutudur.

`sizeof` işlecini bir yapıya, birleşim türü adına veya bir yapı ya da birleşim türünün tanımlayıcısına uyguladığınızda; sonuç, iç ve sondaki doldurma dahil olmak üzere, yapı veya birleşimdeki bayt sayısıdır. Bu boyut, yapı veya bellek sınırları üzerindeki birleşim üyelerini hizalamak için kullanılan iç ve sondaki doldurmayı içerebilir. Bu şekilde, sonuç tek tek üyelerin depolama gereksinimlerini toplayarak hesaplanan boyuta karşılık gelmeyebilir.

Boyutsuz bir dizi bir yapının son öğesi ise, `sizeof` işleci dizi olmadan yapının boyutunu döndürür.

```
buffer = calloc(100, sizeof (int) );
```

Bu örnekte, bir `sizeof` öğesinin makineler arasında değişen boyutunu, `int` adlı bir çalışma zamanı işlevine yönelik bağımsız değişken olarak geçirmek için `calloc` işleci kullanılmaktadır. İşlev tarafından döndürülen değer `buffer` içinde depolanır.

```
static char *strings[] = {
      "this is string one",
      "this is string two",
      "this is string three",
   };
const int string_no = ( sizeof strings ) / ( sizeof strings[0] );
```

Bu örnekte `strings`, bir `char` işaretçileri dizisidir. İşaretçilerin sayısı dizideki öğelerin sayısıdır, ancak belirtilmemiştir. Dizideki öğelerin sayısını hesaplamak üzere `sizeof` işlecini kullanarak işaretçilerin sayısını belirlemek kolaydır. **Const** tamsayı değeri `string_no` bu sayı ile başlatılır. Çünkü bu bir **const** değeri `string_no` değiştirilemez.

## <a name="see-also"></a>Ayrıca Bkz.

[C İşleçleri](c-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
