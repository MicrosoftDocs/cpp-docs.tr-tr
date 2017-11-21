---
title: "AsyncResultType numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncResultType
dev_langs: C++
helpviewer_keywords: AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 32cb9a76a9415fc051faf11ecd3268d461297450
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType Numaralandırması
GetResults() yöntemi tarafından döndürülen sonuç türü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`MultipleResults`|Başlangıç durumu arasında ve çağrısının çağrılmadan önce aşamalı olarak sunulan birden çok sonuç kümesi.|  
|`SingleResult`|Tamamlama olayı tamamlandıktan sonra sunulan tek bir sonuç.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)