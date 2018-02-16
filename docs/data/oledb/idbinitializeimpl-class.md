---
title: "Idbınitializeımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBInitializeImpl class
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e6ff3431934ef3a0c67d6465d22dfde4f7f0947b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="idbinitializeimpl-class"></a>IDBInitializeImpl Sınıfı
Bir uygulamasını sağlar [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>  
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IDBInitializeImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)|Oluşturucu.|  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[Initialize](../../data/oledb/idbinitializeimpl-initialize.md)|Sağlayıcıyı başlatır.|  
|[Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)|Sağlayıcı durdurur.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_dwStatus](../../data/oledb/idbinitializeimpl-m-dwstatus.md)|Veri kaynağı bayraklar.|  
|[m_pCUtlPropInfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md)|DB özellikleri bilgilerini uygulaması için bir işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Veri kaynağı nesneleri ve isteğe bağlı bir arabirim numaralandırıcılar üzerinde zorunlu bir arabirim.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)