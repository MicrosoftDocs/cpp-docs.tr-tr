---
title: "Kaynak Derleyicisi hatası RW2001 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW2001
dev_langs: C++
helpviewer_keywords: RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a14cd36ab87297cf5bc0aa547bdea5ef23260e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rw2001"></a>Kaynak Derleyicisi Hatası RW2001
Önceden işlenmiş RC dosyasında geçersiz yönergesi  
  
 RC dosyasını içeren bir **#pragma** yönergesi.  
  
 Kullanım **#ifndef** önişlemci yönergesiyle **RC_INVOKED** sabit kaynak derleyicisi bir içerme dosyası işlediğinde tanımlar. Yer **#pragma** değil kod bloğunun bir yönerge ne zaman işlenen **RC_INVOKED** sabiti tanımlanır. Kod bloğu içinde yalnızca C/C++ derleyicisi tarafından ve kaynak derleyicisi tarafından işlenir. Aşağıdaki örnek kod, bu tekniği gösterir:  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma** önişlemci yönergesi cinsinden hiçbir anlamı olan bir. RC dosyası. **#İnclude** önişlemci yönergesi kullanılır bir. (Bir proje tabanlı özel üstbilgi dosyası veya ürünlerinden biriyle Microsoft tarafından sağlanan standart üstbilgi dosyası) bir üst bilgi dosyasını dahil RC dosyası. Bunlardan bazıları dosyaları dahil etme içeren **#pragma** yönergesi. Bir veya daha fazla diğer üstbilgi dosyaları, sorunlu içeren dosyayı üstbilgi dosyası içerebildiklerinden **#pragma** yönergesi hemen belirgin olmayabilir.  
  
 **#İfndef RC_INVOKED** teknik proje tabanlı üstbilgi dosyaları üstbilgi dosyaları dahil olmak üzere denetleyebilirsiniz.