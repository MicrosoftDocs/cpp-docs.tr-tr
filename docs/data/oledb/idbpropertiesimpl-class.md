---
title: "Idbpropertiesımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
dev_langs: C++
helpviewer_keywords: IDBPropertiesImpl class
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 98dd7c0ea8000d2f86283cadb9a92fd2caa059a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl Sınıfı
Bir uygulamasını sağlar `IDBProperties` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IDBPropertiesImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|Şu anda veri kaynağı nesnesi veya üzerinde şu anda ayarlanmış başlatma özellik grubundaki özelliklerinin değerlerini ayarlamak veri kaynağı, veri kaynağı bilgileri ve başlatma özellik grupları özelliklerinin değerlerini döndürür Numaralandırıcı.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|Sağlayıcı tarafından desteklenen tüm özellikler hakkındaki bilgileri döndürür.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|Özellikleri veri kaynağı ve başlatma özellik grupları için veri kaynağı nesneleri veya başlatma özellik grubu sıralayıcısını ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) veri kaynağı nesneleri için zorunlu bir arabirim ve numaralandırmalar için isteğe bağlı bir arabirim. Ancak, bir numaralandırıcı gösterir, [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx), kullanıma gerekir `IDBProperties`. `IDBPropertiesImpl`uygulayan `IDBProperties` tarafından tanımlanan statik işlevini kullanarak [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)