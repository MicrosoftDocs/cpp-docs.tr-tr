---
title: Tür int
ms.date: 11/04/2016
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
ms.openlocfilehash: 2bfd9e108b36f073635c6d9e55e2299764dcb309
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87198872"
---
# <a name="type-int"></a>Tür int

Bir **`signed int`** veya öğesinin boyutu, **`unsigned int`** belirli bir makinedeki bir tamsayının standart boyutudur. Örneğin, 16 bit işletim sistemlerinde **`int`** tür genellikle 16 bit veya 2 bayttır. 32 bit işletim sistemlerinde **`int`** tür genellikle 32 bittir veya 4 bayttır. Bu nedenle, **`int`** türü **`short int`** ya da **`long int`** türüne eşdeğerdir ve **`unsigned int`** **`unsigned short`** **`unsigned long`** hedef ortama bağlı olarak tür ya da türüne eşdeğerdir. **`int`** Türler, aksi belirtilmediği takdirde, tüm imzalı değerleri temsil eder.

Tür belirticileri **`int`** ve **`unsigned int`** (veya yalnızca **`unsigned`** ) C dilinin belirli özelliklerini tanımlar (örneğin, **`enum`** türü). Bu durumlarda, **`int`** **`unsigned int`** belirli bir uygulama için ve tanımları gerçek depolamayı tespit ediyor.

**Microsoft'a Özgü**

İşaretli tam sayılar ikiye tamamlayıcı biçimde temsil edilir. En anlamlı bit işareti tutar: negatif için 1, pozitif ve sıfır için 0. Değer aralığı, LIMITLERDEN alınan [C ve C++ tamsayı sınırları](../c-language/cpp-integer-limits.md)içinde verilmiştir. H üstbilgi dosyası.

**SON Microsoft 'a özgü**

> [!NOTE]
> **`int`** Ve **`unsigned int`** tür belirticileri, belirli bir makinenin bu makine için en verimli şekilde tam sayı değerlerini Işlemesini sağladığından C programlarında yaygın olarak kullanılır. Ancak, **`int`** ve türlerinin boyutları farklı olduğundan, **`unsigned int`** belirli bir boyuta bağlı olan programlar **`int`** diğer makinelere taşınmayabilir. Programları daha taşınabilir hale getirmek için, **`sizeof`** sabit kodlanmış veri boyutları yerine işleçle ( [ `sizeof` işleçte](../c-language/sizeof-operator-c.md)anlatıldığı gibi) ifadeleri kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Temel türlerin depolanması](../c-language/storage-of-basic-types.md)
