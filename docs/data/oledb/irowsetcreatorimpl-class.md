---
title: IRowsetCreatorImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
helpviewer_keywords:
- IRowsetCreatorImpl class
- SetSite method
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
ms.openlocfilehash: 3dc5cb06b3eb7f01667e4e1ec09dd60f9befae77
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026610"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl Sınıfı

Aynı işlevleri gerçekleştiren `IObjectWithSite` ancak OLE DB özelliklerini de etkinleştirir `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`.

## <a name="syntax"></a>Sözdizimi

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Öğesinden türetilen bir sınıf `IRowsetCreator`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[SetSite](#setsite)|Satır kümesi nesnesi içeren siteyi ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf devraldığı [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) ve geçersiz kılmaları [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite). Bir satır kümesi sağlayıcı komut veya oturum nesnesi oluşturur, onu çağırır `QueryInterface` örnek kod satır kümesi nesnesi üzerinde `IObjectWithSite` ve çağrıları `SetSite` satır kümesi nesnenin geçirme `IUnkown` arabirimi site arabirim olarak.

## <a name="setsite"></a> Irowsetcreatorımpl::setsite

Satır kümesi nesnesi içeren siteyi ayarlar. Daha fazla bilgi için [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite).

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>Parametreler

*pCreator*<br/>
[in] İşaretçi `IUnknown` satır kümesi nesnesi yönetme sitenin arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Ayrıca, `IRowsetCreatorImpl::SetSite` OLE DB sağlayan `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` özellikleri.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)