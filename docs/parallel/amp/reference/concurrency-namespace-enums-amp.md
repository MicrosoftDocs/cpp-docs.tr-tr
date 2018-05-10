---
title: Eşzamanlılık ad alanı numaralandırmalar (AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a67b5e77b8ab8c52e55dea96e64a3f16a4d70e39
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="concurrency-namespace-enums-amp"></a>Eşzamanlılık ad alanı numaralandırmalar (AMP)
|||  
|-|-|  
|[access_type numaralandırması](#access_type)|[queuing_mode numaralandırması](#queuing_mode)|  
  
##  <a name="access_type"></a>  access_type numaralandırması  
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
