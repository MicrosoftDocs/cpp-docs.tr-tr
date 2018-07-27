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
ms.openlocfilehash: 558578a82f1906d7481abebc5e1f1719b1983724
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269943"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl Sınıfı
Bir uygulamasını sağlar [IGetDataSource](https://msdn.microsoft.com/library/ms709721.aspx) nesne.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
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
 Bkz: [IGetDataSource::GetDataSource](https://msdn.microsoft.com/library/ms725443.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı nesnesinin özelliklerine erişmek istiyorsanız kullanışlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
