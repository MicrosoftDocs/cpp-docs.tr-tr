---
title: "FILETIME yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FILETIME
dev_langs:
- C++
helpviewer_keywords:
- FILETIME structure [MFC]
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f23f9d4a508158b392de6eb5c872f0b5762e1ae3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="filetime-structure"></a>FILETIME Yapısı
`FILETIME` 1 Ocak 1601'den bu yana 100 nano saniyelik aralıkların sayısını temsil eden bir 64-bit değer yapısıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct _FILETIME {  
    DWORD dwLowDateTime;   /* low 32 bits */  
    DWORD dwHighDateTime;  /* high 32 bits */  
} FILETIME, *PFILETIME, *LPFILETIME;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *dwLowDateTime*  
 Düşük 32 bit dosya süreyi belirtir.  
  
 *dwHighDateTime*  
 Yüksek 32 bit dosya süreyi belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** windef.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

