---
title: "Dahil olmak üzere, dosya adları tırnak içine alınmış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17c40e74a31341fc3a725c5e5b3823058e403cff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="including-quoted-filenames"></a>Tırnak İşaretli Dosya Adlarını Dahil Etme
**ANSI 3.8.2** includable kaynak dosyaları için tırnak işaretli adları için destek  
  
 Dahil edilecek dosya için, çift tırnak (" ") işareti içine alarak belirsiz olmayan, tam bir yol belirtimi belirtirseniz, önişlemci yalnızca bu yol belirtimini arar ve standart dizinleri yoksayar.  
  
 Olarak belirtilen içerme dosyaları için [#include](../preprocessor/hash-include-directive-c-cpp.md) "spec yolu", dizin arama üst dosya dizinleri ile başlar, ardından iki üst dosyalarla dizinleri ile devam eder. Bu nedenle arama, işlenmekte olan kaynak dosyayı içeren dizine göre başlar. Dosya adı açılı ayraç gibi iki üst varlık dosyası yok ve dosya bulunamadı, aramaya devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işleme yönergeleri](../c-language/preprocessing-directives.md)