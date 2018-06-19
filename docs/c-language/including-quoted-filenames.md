---
title: Dahil olmak üzere, dosya adları tırnak içine alınmış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80f6afbc503b52d1ef620050bf5592eb84e75fa9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383234"
---
# <a name="including-quoted-filenames"></a>Tırnak İşaretli Dosya Adlarını Dahil Etme
**ANSI 3.8.2** includable kaynak dosyaları için tırnak işaretli adları için destek  
  
 Dahil edilecek dosya için, çift tırnak (" ") işareti içine alarak belirsiz olmayan, tam bir yol belirtimi belirtirseniz, önişlemci yalnızca bu yol belirtimini arar ve standart dizinleri yoksayar.  
  
 Olarak belirtilen içerme dosyaları için [#include](../preprocessor/hash-include-directive-c-cpp.md) "spec yolu", dizin arama üst dosya dizinleri ile başlar, ardından iki üst dosyalarla dizinleri ile devam eder. Bu nedenle arama, işlenmekte olan kaynak dosyayı içeren dizine göre başlar. Dosya adı açılı ayraç gibi iki üst varlık dosyası yok ve dosya bulunamadı, aramaya devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)