---
title: IGetDataSourceImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
ms.openlocfilehash: 596dd2ea7f65040ae526662974d210c1f99a0cf2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210619"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl Sınıfı

[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85)) nesnesinin bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `IGetDataSourceImpl`türetilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetDataSource](#getdatasource)|Oturumu oluşturan veri kaynağı nesnesinde bir arabirim işaretçisi döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu, veri kaynağı nesnesine bir arabirim işaretçisi almak için oturumdaki zorunlu bir arabirimdir.

## <a name="igetdatasourceimplgetdatasource"></a><a name="getdatasource"></a>IGetDataSourceImpl:: GetDataSource

Oturumu oluşturan veri kaynağı nesnesinde bir arabirim işaretçisi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetDataSource)(REFIID riid,
   IUnknown ** ppDataSource);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda*bkz. [IGetDataSource:: GetDataSource](/previous-versions/windows/desktop/ms725443(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

Veri kaynağı nesnesindeki özelliklere erişmeniz gerekiyorsa yararlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
