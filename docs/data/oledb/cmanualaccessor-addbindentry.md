---
title: CManualAccessor::AddBindEntry | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
dev_langs:
- C++
helpviewer_keywords:
- AddBindEntry method
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5809773a6bcf8523f4b2cce07ca638c57e7c59bc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cmanualaccessoraddbindentry"></a>CManualAccessor::AddBindEntry
Çıkış sütunlarında bir BIND girdisi ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
void AddBindEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/en-us/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 `nOrdinal`  
 [in] Sütun numarası.  
  
 `wType`  
 [in] Veri türü.  
  
 `nColumnSize`  
 [in] Sütun boyutunu bayt cinsinden.  
  
 `pData`  
 [in] Arabellekte depolanan sütun veri için bir işaretçi.  
  
 `pLength`  
 [in] Alan uzunluğu gerekirse bir işaretçi.  
  
 `pStatus`  
 [in] Gerekli olursa sütun durumuna bağlanacak değişkeni için bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevi kullanmak için öncelikle çağırmalısınız [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md). Belirtilen sütun sayısından daha fazla girdi ekleyemezsiniz `CreateAccessor`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)   
 [DBVIEWER örneği](../../visual-cpp-samples.md)