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
ms.openlocfilehash: 13f170aa27cdc52b98729b0953568575292f6f6b
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269592"
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
