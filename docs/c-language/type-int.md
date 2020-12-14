---
description: 'Daha fazla bilgi edinin: tür int'
title: Tür int
ms.date: 11/04/2016
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
ms.openlocfilehash: e6ec94877dad3dd49bb5e9b11f77ceb2a734ab1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242775"
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
