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
ms.openlocfilehash: 2056b93fd6c1d32b72996970352e87670ff406de
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034215"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl Sınıfı

Bir uygulamasını sağlar [IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85)) nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IGetDataSourceImpl`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetDataSource](#getdatasource)|Bir arabirim işaretçisi oturum oluşturduğunuz veri kaynağı nesnesi döndürür.|

## <a name="remarks"></a>Açıklamalar

Veri kaynağı nesnesi için bir arabirim işaretçisini almak için oturum zorunlu bir arabirim budur.

## <a name="getdatasource"></a> Igetdatasourceımpl::getdatasource

Bir arabirim işaretçisi oturum oluşturduğunuz veri kaynağı nesnesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetDataSource)(REFIID riid,
   IUnknown ** ppDataSource);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IGetDataSource::GetDataSource](/previous-versions/windows/desktop/ms725443(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı nesnesinin özelliklerine erişmek istiyorsanız kullanışlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)