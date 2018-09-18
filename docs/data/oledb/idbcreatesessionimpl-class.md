---
title: Idbcreatesessionımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7f148176b8d5d0c85f3e899cfd117bbb381794b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047401"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl Sınıfı

Bir uygulamasını sağlar [IDBCreateSession](/previous-versions/windows/desktop/ms724076\(v=vs.85\)) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
### <a name="parameters"></a>Parametreler  

*T*<br/>
TÜRETİLMİŞ SINIFINIZIN  
  
*SessionClass*<br/>
Oturum nesnesi.  

## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldb.h 
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[CreateSession](#createsession)|Veri kaynağı nesnesinin yeni bir oturum oluşturur ve yeni oluşturulan oturum istenen arabirim döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  

Veri kaynağı nesneleri üzerinde zorunlu bir arabirim.  

## <a name="createsession"></a> Idbcreatesessionımpl::createsession

Veri kaynağı nesnesinin yeni bir oturum oluşturur ve yeni oluşturulan oturum istenen arabirim döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession);  
```  
  
#### <a name="parameters"></a>Parametreler  

Bkz: [IDBCreateSession::CreateSession](/previous-versions/windows/desktop/ms714942\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.   
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)