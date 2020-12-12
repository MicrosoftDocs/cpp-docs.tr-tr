---
description: 'Şu konuda daha fazla bilgi edinin: IGetDataSourceImpl sınıfı'
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
ms.openlocfilehash: 24cf83b7eb799882f1c7da42854899bcf46fddf2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287274"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl Sınıfı

[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85)) nesnesinin bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IGetDataSourceImpl` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

| Ad | Açıklama |
|-|-|
|[GetDataSource](#getdatasource)|Oturumu oluşturan veri kaynağı nesnesinde bir arabirim işaretçisi döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu, veri kaynağı nesnesine bir arabirim işaretçisi almak için oturumdaki zorunlu bir arabirimdir.

## <a name="igetdatasourceimplgetdatasource"></a><a name="getdatasource"></a> IGetDataSourceImpl:: GetDataSource

Oturumu oluşturan veri kaynağı nesnesinde bir arabirim işaretçisi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetDataSource)(REFIID riid,
   IUnknown ** ppDataSource);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* bkz. [IGetDataSource:: GetDataSource](/previous-versions/windows/desktop/ms725443(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

Veri kaynağı nesnesindeki özelliklere erişmeniz gerekiyorsa yararlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
