---
title: "Irowsetcreatorımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
dev_langs: C++
helpviewer_keywords: IRowsetCreatorImpl class
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3a1a1c17ad9469ff31b5520ffadb3349f86827ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl Sınıfı
Aynı işlevleri gerçekleştiren `IObjectWithSite` ancak OLE DB özellikleri de etkinleştirir **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğesinden türetilmiş bir sınıf **IRowsetCreator**.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|Satır kümesi nesnesi içeren siteyi ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf devraldığı [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) ve geçersiz kılmalar [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). Bir satır kümesi sağlayıcı komutu veya oturum nesnesi oluşturduğunda, çağıran `QueryInterface` aramakta satır kümesi nesnesi üzerinde `IObjectWithSite` ve çağrıları `SetSite` satır kümesi nesnenin geçirme **IUnkown** arabirimi site arabirim olarak.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)