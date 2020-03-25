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
ms.openlocfilehash: a53cd653258980d21e9dd297ae61c458732b7250
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210554"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl Sınıfı

`IObjectWithSite` aynı işlevleri gerçekleştirir, ancak OLE DB özellikleri `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`de etkinleştirilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
`IRowsetCreator`türetilen bir sınıf.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[SetSite](#setsite)|Satır kümesi nesnesini içeren siteyi ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) 'dan devralınır ve [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)geçersiz kılınır. Bir sağlayıcı komutu ya da oturum nesnesi bir satır kümesi oluşturduğunda, `IObjectWithSite` ve çağrıları arayan satır kümesi nesnesinde `QueryInterface` çağırır `SetSite` satır kümesi nesnesinin `IUnkown` arabirimini site arabirimi olarak geçirme.

## <a name="irowsetcreatorimplsetsite"></a><a name="setsite"></a>Irowsetcreatorimpl:: SetSite

Satır kümesi nesnesini içeren siteyi ayarlar. Daha fazla bilgi için bkz. [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite).

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>Parametreler

*pCreator*<br/>
'ndaki Satır kümesi nesnesini yöneten sitenin `IUnknown` arabirimi işaretçisine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Ayrıca, `IRowsetCreatorImpl::SetSite` OLE DB `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` özelliklerini de sunar.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
