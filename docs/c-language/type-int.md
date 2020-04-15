---
title: Tür int
ms.date: 11/04/2016
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
ms.openlocfilehash: ebce276c8c4efa822601fe36652057b37e922570
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334443"
---
# <a name="type-int"></a>Tür int

İşaretli veya işaretsiz bir `int` öğesinin boyutu, belirli bir makinedeki bir tamsayının standart boyutudur. Örneğin, 16 bit işletim sistemlerinde `int` türü genellikle 16 bit veya 2 bayttır. 32 bit işletim sistemlerinde, `int` türü genellikle 32 bit veya 4 bayttır. Bu `int` nedenle, tür veya `short int` uzun **int** türüne eşdeğerdir ve `unsigned int` tür, hedef ortama bağlı olarak **imzalanmamış kısa** veya `unsigned long` türe eşdeğerdir. `int` türlerinin hepsi aksi belirtilmediği sürece işaretli değerleri temsil eder.

`int` ve `unsigned int` tür tanımlayıcıları (veya `unsigned`) C dilinin belirli özelliklerini tanımlar (örneğin, `enum` türü). Bu durumlarda, belirli bir uygulama için `int` ve unsigned int tanımları gerçek depolamayı belirler.

**Microsoft'a Özgü**

İşaretli tam sayılar ikiye tamamlayıcı biçimde temsil edilir. En anlamlı bit işareti tutar: negatif için 1, pozitif ve sıfır için 0. Değerler aralığı, LIMITlerden alınan [C ve C++ İnteger Limitleri'nde](../c-language/cpp-integer-limits.md)verilir. H üstbilgi dosyası.

**END Microsoft Özel**

> [!NOTE]
> int ve unsigned int tanımlayıcıları C programlarında sık sık kullanılır, çünkü belirli bir makinenin tam sayı değerlerini o makine için en etkin şekilde işlemesine olanak verirler. Ancak, int ve unsigned int türlerinin boyutu değişebildiği için belirli bir int boyutuna bağlı olan programlar diğer makinelere taşınabilir olmayabilir. Programları daha taşınabilir hale getirmek için, sabit kodlu veri boyutları yerine işleç boyutları [(Operatör boyutlarında](../c-language/sizeof-operator-c.md)belirtildiği gibi) boyutları olan ifadeleri kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Temel Türlerin Saklanması](../c-language/storage-of-basic-types.md)
