---
title: CManualAccessor::AddParameterEntry | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
dev_langs:
- C++
helpviewer_keywords:
- AddParameterEntry method
ms.assetid: 9048b164-052b-41b1-a861-227fc529e0b5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e0b730ad81eb827fb86b77b95d4abb96ac73b3c3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cmanualaccessoraddparameterentry"></a>CManualAccessor::AddParameterEntry
Parametre giriş parametresi giriş yapılara ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
void AddParameterEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL,  
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/en-us/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 `nOrdinal`  
 [in] Numaralı parametre.  
  
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
  
 *eParamIO*  
 [in] Bağlama ilişkilendirildiği parametresi bir giriş, giriş/çıkış veya çıktı parametresi olup olmadığını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevi kullanmak için öncelikle çağırmalısınız [CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)   
 [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)   
 [DBVIEWER örneği](../../visual-cpp-samples.md)