---
title: Kaynak Derleyicisi hatası RC2104 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2104
dev_langs:
- C++
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28beaad95cc33d8b014b22035f9ed641f1b6ab6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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