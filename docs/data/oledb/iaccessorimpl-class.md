---
title: "IAccessorImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IAccessorImpl
dev_langs:
- C++
helpviewer_keywords:
- IAccessorImpl class
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7cfc33432d12ac00c834d16f83cc26404e92c63e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl Sınıfı
Bir uygulamasını sağlar [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, 
          class BindType = ATLBINDINGS,
          class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Satır kümesi ya da komut nesne sınıfı.  
  
 `BindType`  
 Bağlama bilgileri için depolama birimi. Varsayılan değer **ATLBINDINGS** yapısı (atldb.h bakın).  
  
 `BindingVector`  
 Sütun bilgileri için depolama birimi. Varsayılan değer [CAtlMap](../../atl/reference/catlmap-class.md) anahtar öğesi olduğu bir **HACCESSOR** değeri ve Değer öğesini olduğunu gösteren bir işaretçi bir `BindType` yapısı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|Oluşturucu.|  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|Bir başvuru sayısı varolan erişimci ekler.|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|Erişimci bağlamaları kümesinden oluşturur.|  
|[GetBindings](../../data/oledb/iaccessorimpl-getbindings.md)|Bağlamaları bir erişimci döndürür.|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|Erişimci serbest bırakır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Satır kümeleri ve komutlar, bu zorunludur. OLE DB sağlayıcıları uygulamak gerektiren bir **HACCESSOR**, bir dizi etiket olduğu [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/en-us/library/ms716845.aspx) yapıları. **HACCESSOR**tarafından sağlanan s `IAccessorImpl` adresleri olan `BindType` yapıları. Varsayılan olarak, `BindType` olarak tanımlanan bir **ATLBINDINGS** içinde `IAccessorImpl`'s şablon tanımı. `BindType` tarafından kullanılan bir mekanizma sağlar `IAccessorImpl` öğe sayısı izlemek için kendi **IAccessor::CreateAccessor'ı** dizisi, başvuru sayımı ve erişimci bayrakları yanı sıra.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)