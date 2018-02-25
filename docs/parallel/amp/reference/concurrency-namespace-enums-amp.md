---
title: "Eşzamanlılık ad alanı numaralandırmalar (AMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d17378a34698cc80d356983898e0023b76877140
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="concurrency-namespace-enums-amp"></a>Eşzamanlılık ad alanı numaralandırmalar (AMP)
|||  
|-|-|  
|[access_type numaralandırması](#access_type)|[queuing_mode Enumeration](#queuing_mode)|  
  
##  <a name="access_type">access_type numaralandırması</a>  
 Veri erişimi çeşitli türlerde belirtmek için kullanılan numaralandırma türü.  
  
```  
enum access_type;  
```  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`access_type_auto`|Otomatik olarak en iyi seçin `access_type` Hızlandırıcı için.|  
|`access_type_none`|Ayrılmış. Ayırma Hızlandırıcı ve CPU değil, yalnızca erişilebilir.|  
|`access_type_read`|Paylaşılan. Ayırma Hızlandırıcı üzerinde erişilebilir olduğundan ve CPU üzerinde okunabilir.|  
|`access_type_read_write`|Paylaşılan. Ayırma Hızlandırıcı üzerinde erişilebilir olduğundan ve CPU üzerinde yazılabilir.|  
|`access_type_write`|Paylaşılan. Ayırma Hızlandırıcı üzerinde erişilebilir olduğundan ve okunabilir ve yazılabilir CPU üzerinde.|  

  
##  <a name="queuing_mode"></a>  queuing_mode numaralandırması  
 Hızlandırıcı üzerinde desteklenen sıralama modları belirtir.  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`queuing_mode_immediate`|Örneğin, herhangi bir belirten bir sıralama modu komutları [parallel_for_each işlevi (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), karşılık gelen Hızlandırıcı aygıta çağırana döndürmeleri hemen sonra gönderilir.|  
|`queuing_mode_automatic`|Komutları karşılık gelen bir komut sırasına sıraya olduğunu belirten bir sıralama modu [accelerator_view](accelerator-view-class.md) nesnesi. Komutları cihaza gönderilen zaman [accelerator_view::flush](accelerator-view-class.md#flush) olarak adlandırılır.|   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
