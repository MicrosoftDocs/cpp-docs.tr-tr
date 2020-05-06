---
title: sizeof İşleci (C)
ms.date: 11/04/2016
f1_keywords:
- sizeof
helpviewer_keywords:
- sizeof operator
ms.assetid: 70826d03-3451-41e4-bebb-a820ae66d53f
ms.openlocfilehash: 0bc0de5481cade10f89634d9e4ec78f4ec7b09f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158131"
---
# <a name="sizeof-operator-c"></a>sizeof İşleci (C)

`sizeof` işleci, işlenen türünde bir nesneyi depolamak için gereken depolama miktarını bayt cinsinden verir. Bu işleç, programlarınızda makineye bağımlı veri boyutları belirtmekten kaçınmanızı sağlar.

## <a name="syntax"></a>Sözdizimi

```
sizeof unary-expression
sizeof ( type-name )
```

## <a name="remarks"></a>Açıklamalar

İşlenen, *birli ifade*veya tür atama ifadesi (yani parantez içine alınmış bir tür Belirleyicisi) olan bir tanıtıcıdır. *Birli ifade* , bir bit alanı nesnesini, tamamlanmamış bir türü veya bir işlev göstergesini temsil edemez. Sonuç, işaretsiz bir tamsayı sabitidir. Standart üst bilgi STDDEF. H bu türü **size_t**olarak tanımlar.

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

Bu örnekte `strings`, bir `char` işaretçileri dizisidir. İşaretçilerin sayısı dizideki öğelerin sayısıdır, ancak belirtilmemiştir. Dizideki öğelerin sayısını hesaplamak üzere `sizeof` işlecini kullanarak işaretçilerin sayısını belirlemek kolaydır. **Const** tamsayı değeri `string_no` bu sayı olarak başlatılır. Bu bir **const** değeri `string_no` olduğundan değiştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[C Işleçleri](c-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
