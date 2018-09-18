---
title: Irowsetıdentityımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IsSameRow
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
dev_langs:
- C++
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1431fb9b35ab83f6cb0fc167eff4ba4508f2e301
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036195"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl Sınıfı

OLE DB uygulayan [IRowsetIdentity](/previous-versions/windows/desktop/ms715913\(v=vs.85\)) satır kimliği için test sağlayan arabirim.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class RowClass = CSimpleRow>  
class ATL_NO_VTABLE IRowsetIdentityImpl   
   : public IRowsetIdentity  
```  
  
### <a name="parameters"></a>Parametreler  

*T*<br/>
Öğesinden türetilen bir sınıf `IRowsetIdentityImpl`.  
  
*RowClass*<br/>
Depolama birimi için `HROW`.  

## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Issamerow](#issamerow)|Bunlar aynı satıra başvurmak için iki satır işleyicilerini karşılaştırır.|  
  
## <a name="issamerow"></a> Irowsetıdentityımpl::ıssamerow

Bunlar aynı satıra başvurmak için iki satır işleyicilerini karşılaştırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,  
   HROW hThatRow);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  

Satır işleyicilerini karşılaştırmak için bu yöntem bıraktığı `HROW` için işleme `RowClass` üyeleri ve çağrıları `memcmp` işaretçileri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)