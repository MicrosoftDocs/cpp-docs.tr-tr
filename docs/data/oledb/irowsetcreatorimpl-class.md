---
title: "Irowsetcreatorımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetCreatorImpl class
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 751f4d41d63a11acd24911969b3649b3ecc46d03
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl Sınıfı
Aynı işlevleri gerçekleştiren `IObjectWithSite` ancak OLE DB özellikleri de etkinleştirir **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
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