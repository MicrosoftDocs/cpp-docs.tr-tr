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
ms.openlocfilehash: 8c4253d469c510f5e6eb996ed510ef836844899d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501393"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl Sınıfı

Aynı işlevleri `IObjectWithSite` gerçekleştirir, ancak OLE DB özellikleri `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`de sunar.

## <a name="syntax"></a>Sözdizimi

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfından türetilmiş `IRowsetCreator`bir sınıf.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[SetSite](#setsite)|Satır kümesi nesnesini içeren siteyi ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) 'dan devralınır ve [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)geçersiz kılınır. Bir sağlayıcı komutu veya oturum nesnesi bir satır kümesi oluşturduğunda, bir satır `QueryInterface` kümesi nesnesi üzerinde `IObjectWithSite` arama yapın ve çağıran satır `SetSite` kümesi nesnesinin `IUnkown` arabirimini site arabirimi olarak geçirerek çağırır.

## <a name="setsite"></a>Irowsetcreatorimpl:: SetSite

Satır kümesi nesnesini içeren siteyi ayarlar. Daha fazla bilgi için bkz. [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite).

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>Parametreler

*pCreator*<br/>
'ndaki Satır kümesi nesnesini `IUnknown` yöneten sitenin arabirim işaretçisine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Ayrıca, `IRowsetCreatorImpl::SetSite` OLE DB `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` özellikleri etkinleştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)