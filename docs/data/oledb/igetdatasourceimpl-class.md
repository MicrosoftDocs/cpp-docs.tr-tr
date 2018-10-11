---
title: Igetdatasourceımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
dev_langs:
- C++
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0101f0d32ebf5fa5a46d735f64fea03b7e5208da
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082585"
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