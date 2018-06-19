---
title: Tür int | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ed3fcd9b11a76f8ff211bf8be5cf50ee6664cda
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389182"
---
# <a name="type-int"></a>Tür int
İşaretli veya işaretsiz bir `int` öğesinin boyutu, belirli bir makinedeki bir tamsayının standart boyutudur. Örneğin, 16 bit işletim sistemlerinde `int` türü genellikle 16 bit veya 2 bayttır. 32 bit işletim sistemlerinde, `int` türü genellikle 32 bit veya 4 bayttır. Bu nedenle, `int` türüdür ya da eşdeğer `short int` veya **uzun tamsayı** türü ve `unsigned int` türüdür ya da eşdeğer **kısa imzasız** veya `unsigned long` bağlı olarak hedef ortam türü. `int` türlerinin hepsi aksi belirtilmediği sürece işaretli değerleri temsil eder.  
  
 `int` ve `unsigned int` tür tanımlayıcıları (veya `unsigned`) C dilinin belirli özelliklerini tanımlar (örneğin, `enum` türü). Bu durumlarda, belirli bir uygulama için `int` ve unsigned int tanımları gerçek depolamayı belirler.  
  
 **Microsoft özel**  
  
 İşaretli tam sayılar ikiye tamamlayıcı biçimde temsil edilir. En anlamlı bit işareti tutar: negatif için 1, pozitif ve sıfır için 0. Değerleri aralığı verilen [C++ tamsayı sınırları](../c-language/cpp-integer-limits.md), sınırlamaları uygulanmaya alınır. H üstbilgi dosyası.  
  
 **SON Microsoft özel**  
  
> [!NOTE]
>  int ve unsigned int tanımlayıcıları C programlarında sık sık kullanılır, çünkü belirli bir makinenin tam sayı değerlerini o makine için en etkin şekilde işlemesine olanak verirler. Ancak, int ve unsigned int türlerinin boyutu değişebildiği için belirli bir int boyutuna bağlı olan programlar diğer makinelere taşınabilir olmayabilir. Programları daha taşınabilir hale getirmek için ifadeler ile sizeof işleci kullanabilirsiniz (anlatıldığı gibi [sizeof işleci](../c-language/sizeof-operator-c.md)) yerine sabit kodlanmış veri boyutları.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel Türleri Depolama](../c-language/storage-of-basic-types.md)