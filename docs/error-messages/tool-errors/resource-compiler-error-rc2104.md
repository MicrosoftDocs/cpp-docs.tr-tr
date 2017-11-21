---
title: "Kaynak Derleyicisi hatası RC2104 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2104
dev_langs: C++
helpviewer_keywords: RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0eb2c3c7dfc8bf9a86ae8d91103fd89b30559574
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-error-rc2104"></a>Kaynak Derleyicisi Hatası RC2104
Tanımsız anahtar veya anahtar adı: anahtar  
  
 Belirtilen anahtar veya anahtar adı tanımlı değil.  
  
 Bu hata genellikle kaynak tanımı'ndaki ya da dahil üstbilgi dosyasında bir yazım hatasından kaynaklanır. Eksik üstbilgi dosyası tarafından da oluşabilir.  
  
 Sorunu düzeltmek için tanımlanmış anahtar veya anahtar adını içeren ve kaynak dosyasında bulunur ve anahtar veya anahtar adının doğru yazıldığından doğrulamanız gerekir üst bilgi dosyasını bulun. Projenizi önceden derlenmiş üstbilgi ile oluşturulan ve daha sonra kaldırmanız, olduğundan emin olun kaynak dosyasının hala gerekli tüm üstbilgileri içerir.  
  
 Visual Studio'da, kaynak dosyanızdaki anahtar adlarını ve tanımlı anahtar sözcükler doğrulamak için açık **kaynak görünümü** penceresi — menü çubuğunda seçin **Görünüm**, **kaynak görünümü**— ve ardından .rc dosyası için kısayol menüsünü açın ve seçin **kaynak semboller** tanımlanmış simge listesini görüntülemek için. Dahil edilen üstbilgileri değiştirmek için .rc dosyası için kısayol menüsünü açın ve seçin **kaynağını içeren**.  
  
 Bu ileti karşılaşırsanız:  
  
```  
undefined keyword or key name: MFT_STRING   
```  
  
 \MCL\MFC\Include\AfxRes.h açın ve bu ekleyin yönergesi içerir:  
  
```  
#include <winresrc.h>  
```