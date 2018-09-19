---
title: Iconverttypeımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
dev_langs:
- C++
helpviewer_keywords:
- IConvertTypeImpl class
- CanConvert method
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ed4eefe8c05e2b5b027ba1d7c1fec022c9e44409
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104952"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl Sınıfı

Bir uygulamasını sağlar [IConvertType](/previous-versions/windows/desktop/ms715926\(v=vs.85\)) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
### <a name="parameters"></a>Parametreler  

*T*<br/>
Sınıfınız, türetilen `IConvertTypeImpl`.  

## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[CanConvert](#canconvert)|Bir komutu veya bir satır kümesi tür dönüştürmeleri kullanılabilirliği hakkında bilgi sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  

Bu arabirim, komutları, satır kümeleri ve dizin satır kümeleri zorunludur. `IConvertTypeImpl` OLE DB tarafından sağlanan dönüştürme nesne temsilci atayarak arabirimini uygular.  

## <a name="canconvert"></a> Iconverttypeımpl::canconvert

Bir komutu veya bir satır kümesi tür dönüştürmeleri kullanılabilirliği hakkında bilgi sağlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IConvertType::CanConvert](/previous-versions/windows/desktop/ms711224\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  

OLE DB veri dönüştürme kullanan `MSADC.DLL`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)