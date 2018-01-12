---
title: "Isessionpropertiesımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ISessionPropertiesImpl
dev_langs: C++
helpviewer_keywords: ISessionPropertiesImpl class
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9ff8eda4d593ff0c6064313a7be243ec498b15c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl Sınıfı
Bir uygulamasını sağlar [ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `ISessionPropertiesImpl`.  
  
 `PropClass`  
 Varsayılan olarak bir kullanıcı tarafından tanımlanabilen özellik sınıfı `T`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|Oturumda şu anda ayarlanmış oturum özellik grubundaki özellikler listesini döndürür.|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|Oturum özellik grubundaki özellikleri ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Oturumlar üzerinde zorunlu bir arabirim. Bu sınıf tarafından tanımlanan statik işlevini çağırarak oturum özellikleri uygulayan [özellik kümesi eşlemesini](../../data/oledb/begin-propset-map.md). Özellik kümesi eşlemesini oturum sınıfınızda belirtilmesi gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)