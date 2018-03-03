---
title: "Kaynak Derleyicisi hatası RC2101 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d08e9ddb7b8cda127b1d05bfef52b52833534cb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2101"></a>Kaynak Derleyicisi Hatası RC2101
Önceden işlenmiş RC dosyasında geçersiz yönergesi  
  
 Kaynak Derleyicisi dosyasını içeren bir **#pragma** yönergesi.  
  
 Kullanım **#ifndef** önişlemci yönergesi kaynak derleyicisi bir içerme dosyası işlediğinde tanımlar RC_INVOKED sabit ile. Yer **#pragma** RC_INVOKED sabiti tanımlandığında işlenmez kod bloğunun bir yönerge. Kod bloğu içinde yalnızca C/C++ derleyicisi tarafından ve kaynak derleyicisi tarafından işlenir. Aşağıdaki örnek kod, bu tekniği gösterir:  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma** önişlemci yönergesi cinsinden hiçbir anlamı olan bir. RC dosyası. **#İnclude** önişlemci yönergesi kullanılır bir. (Bir proje tabanlı özel üstbilgi dosyası veya ürünlerinden biriyle Microsoft tarafından sağlanan standart üstbilgi dosyası) bir üst bilgi dosyasını dahil RC dosyası. Bunlardan bazıları dosyaları dahil etme içeren **#pragma** yönergesi. Bir veya daha fazla diğer üstbilgi dosyaları, sorunlu içeren dosyayı üstbilgi dosyası içerebildiklerinden **#pragma** yönergesi hemen belirgin olmayabilir.  
  
 **#İfndef** RC_INVOKED teknik proje tabanlı üstbilgi dosyaları üstbilgi dosyaları dahil olmak üzere denetleyebilirsiniz.