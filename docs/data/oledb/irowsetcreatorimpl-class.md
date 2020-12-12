---
description: 'Şu konuda daha fazla bilgi edinin: ırowsetcreatorimpl sınıfı'
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
ms.openlocfilehash: 6a478e86bdb09851afed091c99ed0d0931a9115e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317408"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl Sınıfı

Aynı işlevleri gerçekleştirir, `IObjectWithSite` ancak OLE DB özellikleri de sunar `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` .

## <a name="syntax"></a>Sözdizimi

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfından türetilmiş bir sınıf `IRowsetCreator` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[SetSite](#setsite)|Satır kümesi nesnesini içeren siteyi ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) 'dan devralınır ve [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)geçersiz kılınır. Bir sağlayıcı komutu veya oturum nesnesi bir satır kümesi oluşturduğunda, bir satır kümesi nesnesi üzerinde arama yapın `QueryInterface` `IObjectWithSite` ve çağıran `SetSite` satır kümesi nesnesinin `IUnkown` arabirimini site arabirimi olarak geçirerek çağırır.

## <a name="irowsetcreatorimplsetsite"></a><a name="setsite"></a> Irowsetcreatorimpl:: SetSite

Satır kümesi nesnesini içeren siteyi ayarlar. Daha fazla bilgi için bkz. [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite).

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>Parametreler

*pCreator*<br/>
'ndaki `IUnknown` Satır kümesi nesnesini yöneten sitenin arabirim işaretçisine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Ayrıca, `IRowsetCreatorImpl::SetSite` OLE DB `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` özellikleri etkinleştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
