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
ms.openlocfilehash: 756cc7ba203a1655bf5112d9c03e84707644f1e5
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337576"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl Sınıfı
Bir uygulamasını sağlar [IDBCreateSession](https://msdn.microsoft.com/library/ms724076.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 TÜRETİLMİŞ SINIFINIZIN  
  
 *SessionClass*  
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
 Bkz: [IDBCreateSession::CreateSession](https://msdn.microsoft.com/library/ms714942.aspx) içinde *OLE DB Programcının Başvurusu*.   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)