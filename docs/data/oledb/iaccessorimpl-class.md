---
title: IAccessorImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IAccessorImpl
- ATL.IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::IAccessorImpl
- IAccessorImpl::IAccessorImpl
- IAccessorImpl.IAccessorImpl
- IAccessorImpl
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
- IAccessorImpl::CreateAccessor
- CreateAccessor
- ATL::IAccessorImpl::CreateAccessor
- IAccessorImpl.CreateAccessor
- ATL.IAccessorImpl.CreateAccessor
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
- ReleaseAccessor
- IAccessorImpl::ReleaseAccessor
- ATL.IAccessorImpl.ReleaseAccessor
- ATL::IAccessorImpl::ReleaseAccessor
- IAccessorImpl.ReleaseAccessor
dev_langs:
- C++
helpviewer_keywords:
- IAccessorImpl class
- IAccessorImpl class, constructor
- IAccessorImpl constructor
- AddRefAccessor method
- CreateAccessor method
- GetBindings method
- ReleaseAccessor method
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 73e0b7646da57af679e7b3cbec3b0bb72d4ea8b8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42466085"
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl Sınıfı
Bir uygulamasını sağlar [IAccessor](/previous-versions/windows/desktop/ms719672\(v=vs.85\)) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, 
   class BindType = ATLBINDINGS,
   class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Satır kümesi ya da komut nesne sınıfı.  
  
 *BindType*  
 Bağlama bilgileri için depolama birimi. Varsayılan değer `ATLBINDINGS` yapısı (atldb.h bakın).  
  
 *BindingVector*  
 Sütun bilgileri için depolama birimi. Varsayılan değer [CAtlMap](../../atl/reference/catlmap-class.md) burada anahtar öğesi HACCESSOR değer, Değer öğesini bir işaretçi ise bir `BindType` yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  

## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[IAccessorImpl](#iaccessorimpl)|Oluşturucu.|  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[AddRefAccessor](#addrefaccessor)|Başvuru sayısı için mevcut bir erişimci ekler.|  
|[CreateAccessor](#createaccessor)|Erişimci bağlamaları kümesinden oluşturur.|  
|[GetBindings](#getbindings)|Bağlamaları bir erişimcisinde döndürür.|  
|[ReleaseAccessor](#releaseaccessor)|Erişimci serbest bırakır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu satır kümeleri ve komutları zorunludur. OLE DB sağlayıcıları bir HACCESSOR uygulamak gerektiren bir dizi için bir etiket olduğu [IAccessor::CreateAccessor'ı](/previous-versions/windows/desktop/ms716845\(v=vs.85\)) yapıları. Tarafından sağlanan HACCESSORs `IAccessorImpl` adresleri olan `BindType` yapıları. Varsayılan olarak, `BindType` olarak tanımlanan bir `ATLBINDINGS` içinde `IAccessorImpl`'s şablon tanımı. `BindType` tarafından kullanılan bir mekanizma sağlar `IAccessorImpl` içindeki öğelerin sayısını izlemek için kendi `DBBINDING` dizi yanı sıra bir başvuru sayısı ve erişimci bayrakları.  

## <a name="iaccessorimpl"></a> IAccessorImpl::IAccessorImpl
Oluşturucu.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
IAccessorImpl();  
```  

## <a name="addrefaccessor"></a> IAccessorImpl::addrefaccessor
Başvuru sayısı için mevcut bir erişimci ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::AddRefAccessor](/previous-versions/windows/desktop/ms714978\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.

## <a name="createaccessor"></a> IAccessorImpl::CreateAccessor
Erişimci bağlamaları kümesinden oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(CreateAccessor)(DBACCESSORFLAGS dwAccessorFlags,  
   DBCOUNTITEM cBindings,  
   const DBBINDING rgBindings[],  
   DBLENGTH cbRowSize,  
   HACCESSOR* phAccessor,  
   DBBINDSTATUS rgStatus[]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [DBBINDING](/previous-versions/windows/desktop/ms720969\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  

## <a name="getbindings"></a> IAccessorImpl::getbindings
Temel sütunları bağlamaları erişimci tüketicide döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(GetBindings)(HACCESSOR hAccessor,  
   DBACCESSORFLAGS* pdwAccessorFlags,  
   DBCOUNTITEM* pcBindings,  
   DBBINDING** prgBindings);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::GetBindings](/previous-versions/windows/desktop/ms721253\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*. 

## <a name="releaseaccessor"></a> IAccessorImpl::releaseaccessor
Erişimci serbest bırakır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::ReleaseAccessor](/previous-versions/windows/desktop/ms719717\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)