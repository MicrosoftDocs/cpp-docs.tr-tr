---
title: CHAIN_PROPERTY_SET | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CHAIN_PROPERTY_SET
dev_langs:
- C++
helpviewer_keywords:
- CHAIN_PROPERTY_SET macro
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9db57535f3f0bc7653c80b83c3e0115727eed707
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094341"
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