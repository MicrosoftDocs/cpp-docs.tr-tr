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
ms.openlocfilehash: 75b95f871023d7bfdea198a69377b1f360ab115f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637846"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl Sınıfı

Bir uygulamasını sağlar [IGetDataSource](/previous-versions/windows/desktop/ms709721) nesne.

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

Bkz: [IGetDataSource::GetDataSource](/previous-versions/windows/desktop/ms725443) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı nesnesinin özelliklerine erişmek istiyorsanız kullanışlıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)