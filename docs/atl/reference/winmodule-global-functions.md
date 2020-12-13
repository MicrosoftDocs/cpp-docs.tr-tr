---
description: 'Daha fazla bilgi edinin: WinModule genel Işlevleri'
title: WinModule genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 1ea232bd3db79f3be3d9dee32b5f9fa40df0eb79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138664"
---
# <a name="winmodule-global-functions"></a>WinModule genel Işlevleri

Bu işlevler, yapı işlemleri için destek sağlar `_AtlCreateWndData` .

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|Ad|Açıklama|
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|Bu işlev, bir yapıyı başlatmak ve eklemek için kullanılır `_AtlCreateWndData` .|
|[Atlwınmoduleextractcreatewnddata](#atlwinmoduleextractcreatewnddata)|Var olan bir yapıyı ayıklamak için bu işlevi çağırın `_AtlCreateWndData` .|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="atlwinmoduleaddcreatewnddata"></a><a name="atlwinmoduleaddcreatewnddata"></a> AtlWinModuleAddCreateWndData

Bu işlev, bir yapıyı başlatmak ve eklemek için kullanılır `_AtlCreateWndData` .

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>Parametreler

*pWinModule*<br/>
Modülün [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) yapısına yönelik işaretçi.

*pData*<br/>
Başlatılacak ve geçerli modüle eklenecek [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısına yönelik işaretçi.

*Nesnesini*<br/>
Nesne **`this`** işaretçisinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

`_AtlCreateWndData` **`this`** Sınıf örneklerine başvurmak için kullanılan işaretçiyi depolamak için kullanılan bir yapıyı başlatır ve bir modülün yapısı tarafından başvurulan listeye ekler `_ATL_WIN_MODULE70` . [CAtlWinModule:: AddCreateWndData](catlwinmodule-class.md#addcreatewnddata)tarafından çağırılır.

## <a name="atlwinmoduleextractcreatewnddata"></a><a name="atlwinmoduleextractcreatewnddata"></a> Atlwınmoduleextractcreatewnddata

Var olan bir yapıyı ayıklamak için bu işlevi çağırın `_AtlCreateWndData` .

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>Parametreler

*pWinModule*<br/>
Modülün [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev `_AtlCreateWndData` , bir modülün yapısı tarafından başvurulan listeden var olan bir yapıyı ayıklar `_ATL_WIN_MODULE70` .

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
