---
title: sizeof Operator (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- sizeof
dev_langs:
- C++
helpviewer_keywords:
- sizeof operator
ms.assetid: 70826d03-3451-41e4-bebb-a820ae66d53f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b1698703c20c90a2f66592deb2b5e04f539f4db
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32388331"
---
# <a name="sizeof-operator-c"></a>sizeof İşleci (C)
`sizeof` işleci, işlenen türünde bir nesneyi depolamak için gereken depolama miktarını bayt cinsinden verir. Bu işleç, makine bağımlı veri boyutları programlarınıza belirtmekten kaçının olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
sizeof unary-expression  
sizeof ( type-name )  
```  
  
## <a name="remarks"></a>Açıklamalar  
İşlenen olan ya da bir tanımlayıcıdır bir *Tek terimli ifadesi*, veya bir cast türünü ifadesi (parantez içindeki başka bir deyişle, bir tür belirteci). *Tek terimli ifadesi* bir bit alanı nesnesi, tamamlanmamış bir tür veya işlev Belirleyicisi temsil edilemez. Sonuç, işaretsiz bir tamsayı sabitidir. Standart üstbilgi STDDEF. H olarak bu türü tanımlayan **size_t**.  
  
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
  
Bu örnekte `strings`, bir `char` işaretçileri dizisidir. İşaretçilerin sayısı dizideki öğelerin sayısıdır, ancak belirtilmemiştir. Dizideki öğelerin sayısını hesaplamak üzere `sizeof` işlecini kullanarak işaretçilerin sayısını belirlemek kolaydır. **Const** tamsayı değeri `string_no` bu sayıya başlatılır. Çünkü bir **const** değeri `string_no` değiştirilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[C İşleçleri](c-operators.md)  
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)  
  