---
title: WinModule Genel İşlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 3d7d001a2835514cc5385a7069c0bcda58cdd88e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329354"
---
# <a name="winmodule-global-functions"></a>WinModule Genel İşlevleri

Bu işlevler `_AtlCreateWndData` yapı işlemleri için destek sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler Windows Runtime'da çalışan uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Bu işlev, bir `_AtlCreateWndData` yapıyı başlatmave eklemek için kullanılır.|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|Varolan `_AtlCreateWndData` bir yapıyı ayıklamak için bu işlevi çağırın.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="atlwinmoduleaddcreatewnddata"></a><a name="atlwinmoduleaddcreatewnddata"></a>AtlWinModuleAddCreateWndData

Bu işlev, bir `_AtlCreateWndData` yapıyı başlatmave eklemek için kullanılır.

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>Parametreler

*pWinModule*<br/>
Modülün [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) yapısına işaretçi.

*Pdata*<br/>
[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısının başharfe ve geçerli modüle eklenmesine işaretçi.

*Pobject*<br/>
Bir nesneye işaretçi **bu** işaretçidir.

### <a name="remarks"></a>Açıklamalar

Sınıf örneklerine `_AtlCreateWndData` başvurmak için kullanılan **bu** işaretçiyi depolamak için kullanılan bir yapıyı başolarak karşılar `_ATL_WIN_MODULE70` ve modülün yapısı tarafından başvurulan listeye ekler. [CAtlWinModule tarafından çağrılan:AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).

## <a name="atlwinmoduleextractcreatewnddata"></a><a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData

Varolan `_AtlCreateWndData` bir yapıyı ayıklamak için bu işlevi çağırın.

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>Parametreler

*pWinModule*<br/>
Modülün [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir `_AtlCreateWndData` modülün `_ATL_WIN_MODULE70` yapısı tarafından başvurulan listeden varolan bir yapı ayıklar.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
