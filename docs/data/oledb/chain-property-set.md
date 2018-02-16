---
title: CHAIN_PROPERTY_SET | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CHAIN_PROPERTY_SET
dev_langs:
- C++
helpviewer_keywords:
- CHAIN_PROPERTY_SET macro
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f5a80f6c834c3359d3a4be40b892ff4e5600e9e1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="chainpropertyset"></a>CHAIN_PROPERTY_SET
Bu makrosu özellik grupları zincir oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
CHAIN_PROPERTY_SET(ChainClass)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 *ChainClass*  
 [in] Zincir özellikleri sınıfın adı. Bu, zaten bir harita (örneğin, bir oturum, komut veya veri kaynağı nesne sınıfı) içeren ATL Proje Sihirbazı tarafından oluşturulan bir sınıftır.  
  
## <a name="remarks"></a>Açıklamalar  
 Başka bir sınıftan kendi sınıfı bir özellik kümesi zincir sonra sınıfından doğrudan erişim özellikleri.  
  
> [!CAUTION]
>  Bu makrosu tutumlu kullanın. Hatalı kullanımı bir tüketici OLE DB uygunluk testlerini başarısız olmasına neden olabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonları için Makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)