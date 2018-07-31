---
title: Icommandpropertiesımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b360b56066ecbb5cc605012b234c0ac11afb2a11
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339418"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl Sınıfı
Bir uygulamasını sağlar [ICommandProperties](https://msdn.microsoft.com/library/ms723044.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Türetilmiş sınıfınızın  
  
 *PropClass*  
 Özellikleri sınıfınıza.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|Şu anda satır kümesi için istenen satır kümesi özelliği grubunda özelliklerinin listesini döndürür.|  
|[SetProperties](#setproperties)|Satır kümesi özelliği grubunda özelliklerini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu, komutları zorunludur. Uygulama tarafından tanımlanan statik işlev tarafından sağlanan [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) makrosu.  

## <a name="getproperties"></a> Icommandpropertiesımpl::GetProperties
Komutun özellik eşlemesi kullanarak tüm istenen özellik kümeleri döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [ICommandProperties::GetProperties](https://msdn.microsoft.com/library/ms723119.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="setproperties"></a> Icommandpropertiesımpl::SetProperties
Komut nesnesi için özelliklerini ayarlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [ICommandProperties::SetProperties](https://msdn.microsoft.com/library/ms711497.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)