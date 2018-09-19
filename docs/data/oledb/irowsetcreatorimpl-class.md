---
title: Irowsetcreatorımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IRowsetCreatorImpl class
- SetSite method
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51534ffb027e35bbab5a9473cf4190c14b384808
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118160"
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

## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)