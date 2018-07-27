---
title: Isessionpropertiesımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- GetProperties
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3759b67ef5d9ee9832649b3b0d516dbfb04440b
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322026"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl Sınıfı
Bir uygulamasını sağlar [ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `ISessionPropertiesImpl`.  
  
 *PropClass*  
 Varsayılan olarak bir kullanıcı tarafından tanımlanabilen özellik sınıfı *T*.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|Şu anda oturumda ayarlanan oturumu özellik grubundaki özelliklerinin listesini döndürür.|  
|[SetProperties](#setproperties)|Oturum özellik grubundaki özellikleri ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Oturumlarının üzerinde zorunlu bir arabirim. Bu sınıf tarafından tanımlanan statik bir işlev çağırarak oturum özellikleri uygulayan [özellik kümesi eşlemesini](../../data/oledb/begin-propset-map.md). Özellik kümesi eşlemesi oturumu Sınıfınız içinde belirtilmelidir.  
  
## <a name="getproperties"></a> Isessionpropertiesımpl::GetProperties
Özellikler listesini döndürür `DBPROPSET_SESSION` oturumda ayarlanan özellik grubu.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD(GetProperties)(ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [ISessionProperties::GetProperties](https://msdn.microsoft.com/library/ms723643.aspx) içinde *OLE DB Programcının Başvurusu*. 

## <a name="setproperties"></a> Isessionpropertiesımpl::SetProperties
Ayarlar özellikleri `DBPROPSET_SESSION` özellik grubu.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [ISessionProperties::SetProperties](https://msdn.microsoft.com/library/ms714405.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
