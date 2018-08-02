---
title: AsyncResultType numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
dev_langs:
- C++
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8171c4a57621a4f17a5f0ddb0745faa70fde6524
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465291"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType Numaralandırması
Tarafından döndürülen sonuç türü belirtir `GetResults()` yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`MultipleResults`|Bir aşamalı olarak arasında sunulan birden çok sonuç kümesi `Start` durumu ve önce `Close()` çağrılır.|  
|`SingleResult`|Tam olay gerçekleştikten sonra sunulan tek bir sonuç.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)