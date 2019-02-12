---
title: Tür int
ms.date: 11/04/2016
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
ms.openlocfilehash: 848c9799e7ab5cfdfd2b25cc84e55de02c673f3e
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150018"
---
# <a name="type-int"></a>Tür int

İşaretli veya işaretsiz bir `int` öğesinin boyutu, belirli bir makinedeki bir tamsayının standart boyutudur. Örneğin, 16 bit işletim sistemlerinde `int` türü genellikle 16 bit veya 2 bayttır. 32 bit işletim sistemlerinde, `int` türü genellikle 32 bit veya 4 bayttır. Bu nedenle, `int` türüdür ya da eşdeğer `short int` veya **long int** türü ve `unsigned int` türüdür ya da eşdeğer **işaretsiz** veya `unsigned long` hedef ortama bağlı olarak türü. 
  `int` türlerinin hepsi aksi belirtilmediği sürece işaretli değerleri temsil eder.


  `int` ve `unsigned int` tür tanımlayıcıları (veya `unsigned`) C dilinin belirli özelliklerini tanımlar (örneğin, `enum` türü). Bu durumlarda, belirli bir uygulama için `int` ve unsigned int tanımları gerçek depolamayı belirler.

**Microsoft'a özgü**

İşaretli tam sayılar ikiye tamamlayıcı biçimde temsil edilir. En anlamlı bit işareti tutar: Negatif için 1, 0 pozitif ve sıfır. Değerleri aralığı verilen [C++ tamsayı sınırları](../c-language/cpp-integer-limits.md), SINIRLARI alınır. H üst bilgi dosyası.

**END Microsoft özgü**

> [!NOTE]
>  int ve unsigned int tanımlayıcıları C programlarında sık sık kullanılır, çünkü belirli bir makinenin tam sayı değerlerini o makine için en etkin şekilde işlemesine olanak verirler. Ancak, int ve unsigned int türlerinin boyutu değişebildiği için belirli bir int boyutuna bağlı olan programlar diğer makinelere taşınabilir olmayabilir. Programları daha taşınabilir yapmak için sizeof işleci ile ifadeleri kullanabilirsiniz (açıklandığı gibi [sizeof işleci](../c-language/sizeof-operator-c.md)) sabit kodlanmış veri boyutları yerine.

## <a name="see-also"></a>Ayrıca bkz.

[Temel Türleri Depolama](../c-language/storage-of-basic-types.md)
