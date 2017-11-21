---
title: "Genel işlevler WinModule | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
dev_langs: C++
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5435b9870a396f24cb2aca5889c9fcfbc90d879a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="winmodule-global-functions"></a>WinModule genel işlevler
Bu işlevler için destek sağlayan `_AtlCreateWndData` yapısı işlemleri.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarda aşağıdaki tabloda listelenen işlevleri kullanılamaz.  
  
|||  
|-|-|  
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Bu işlev başlatmak ve eklemek için kullanılan bir `_AtlCreateWndData` yapısı.|  
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Var olan ayıklamak için bu işlevi çağırmak `_AtlCreateWndData` yapısı.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  `            
##  <a name="atlwinmoduleaddcreatewnddata"></a>AtlWinModuleAddCreateWndData  
 Bu işlev başlatmak ve eklemek için kullanılan bir `_AtlCreateWndData` yapısı.  
   
```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWinModule`  
 Bir modülün işaretçi [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) yapısı.  
  
 `pData`  
 İşaretçi [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) başlatıldı ve geçerli modülüne eklenmiş yapısı.  
  
 `pObject`  
 Bir nesnenin işaretçi **bu** işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatır bir `_AtlCreateWndData` depolamak için kullanılan yapısı **bu** işaretçi sınıfı örneklerine başvurmak için kullanılan ve bir modülün tarafından başvurulan listesine ekler `_ATL_WIN_MODULE70` yapısı. Tarafından çağrılır [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).  
  
##  <a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData  
 Var olan ayıklamak için bu işlevi çağırmak `_AtlCreateWndData` yapısı.  
 
```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWinModule`  
 Bir modülün işaretçi [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varolan ayıklamak `_AtlCreateWndData` yapısı bir modülün tarafından başvurulan listeden `_ATL_WIN_MODULE70` yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
