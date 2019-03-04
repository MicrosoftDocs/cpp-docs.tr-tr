---
title: WinModule genel işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 0e7450ea2a42c0b35dc5a6d1b77dfb0f2acb9520
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265098"
---
# <a name="winmodule-global-functions"></a>WinModule genel işlevleri

Bu işlevler için destek sağlayan `_AtlCreateWndData` yapı işlemleri.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Bu işlev, başlatmak ve eklemek için kullanılan bir `_AtlCreateWndData` yapısı.|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Mevcut bir ayıklamak için bu işlevi çağırın `_AtlCreateWndData` yapısı.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="atlwinmoduleaddcreatewnddata"></a>  AtlWinModuleAddCreateWndData

Bu işlev, başlatmak ve eklemek için kullanılan bir `_AtlCreateWndData` yapısı.

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>Parametreler

*pWinModule*<br/>
Bir modülün işaretçisine [_atl_wın_module70](../../atl/reference/atl-win-module70-structure.md) yapısı.

*pData*<br/>
İşaretçi [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısı başlatılamadı ve geçerli modülüne eklendi.

*pObject*<br/>
Bir nesnenin işaretçisine **bu** işaretçi.

### <a name="remarks"></a>Açıklamalar

Başlatan bir `_AtlCreateWndData` depolamak için kullanılan yapı **bu** işaretçiyi sınıf örneklerinin başvurmak için kullanılan ve bir modülün tarafından başvurulan listesine ekler `_ATL_WIN_MODULE70` yapısı. Çağıran [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).

##  <a name="atlwinmoduleextractcreatewnddata"></a>  AtlWinModuleExtractCreateWndData

Mevcut bir ayıklamak için bu işlevi çağırın `_AtlCreateWndData` yapısı.

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>Parametreler

*pWinModule*<br/>
Bir modülün işaretçisine [_atl_wın_module70](../../atl/reference/atl-win-module70-structure.md) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, mevcut bir ayıklayacaksınız `_AtlCreateWndData` yapısı bir modülün tarafından başvurulan listeden `_ATL_WIN_MODULE70` yapısı.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
