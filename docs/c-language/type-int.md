---
title: Tür int
ms.date: 11/04/2016
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
ms.openlocfilehash: c69d2308abe2ee3d7e6b392f5a9e78a004791501
ms.sourcegitcommit: ea9d78dbb93bf3f8841dde93dbc12bd66f6f32ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72778367"
---
# <a name="type-int"></a>Tür int

İşaretli veya işaretsiz bir `int` öğesinin boyutu, belirli bir makinedeki bir tamsayının standart boyutudur. Örneğin, 16 bit işletim sistemlerinde `int` türü genellikle 16 bit veya 2 bayttır. 32 bit işletim sistemlerinde, `int` türü genellikle 32 bit veya 4 bayttır. Bu nedenle, `int` türü `short int` ya da **long int** türüne eşdeğerdir ve `unsigned int` türü hedef ortama bağlı olarak **işaretsiz short** ya da `unsigned long` türüne eşdeğerdir. `int` türlerinin hepsi aksi belirtilmediği sürece işaretli değerleri temsil eder.

`int` ve `unsigned int` tür tanımlayıcıları (veya `unsigned`) C dilinin belirli özelliklerini tanımlar (örneğin, `enum` türü). Bu durumlarda, belirli bir uygulama için `int` ve unsigned int tanımları gerçek depolamayı belirler.

**Microsoft 'a özgü**

İşaretli tam sayılar ikiye tamamlayıcı biçimde temsil edilir. En anlamlı bit işareti tutar: negatif için 1, pozitif ve sıfır için 0. Değer aralığı, LIMITLERDEN alınan [C ve C++ Integer sınırları](../c-language/cpp-integer-limits.md)içinde verilmiştir. H üstbilgi dosyası.

**SON Microsoft 'a özgü**

> [!NOTE]
>  int ve unsigned int tanımlayıcıları C programlarında sık sık kullanılır, çünkü belirli bir makinenin tam sayı değerlerini o makine için en etkin şekilde işlemesine olanak verirler. Ancak, int ve unsigned int türlerinin boyutu değişebildiği için belirli bir int boyutuna bağlı olan programlar diğer makinelere taşınabilir olmayabilir. Programları daha taşınabilir hale getirmek için, sabit kodlanmış veri boyutları yerine sizeof işleci ( [sizeof işleci](../c-language/sizeof-operator-c.md)içinde anlatıldığı gibi) ile ifadeleri kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Temel Türleri Depolama](../c-language/storage-of-basic-types.md)
