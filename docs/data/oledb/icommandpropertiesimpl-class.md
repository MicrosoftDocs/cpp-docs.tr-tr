---
title: "Icommandpropertiesımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
dev_langs: C++
helpviewer_keywords: ICommandPropertiesImpl class
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5878e7fa6345e294025b45474b1b384d01283c49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl Sınıfı
Bir uygulamasını sağlar [ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Türetilmiş sınıfınız  
  
 `PropClass`  
 Özellikler sınıfınız.  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)|Şu anda satır kümesi için istenen satır kümesi özellik grubundaki özellikler listesini döndürür.|  
|[SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)|Satır kümesi özellik grubundaki özellikleri ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu komutlar hakkında zorunludur. Uygulama tarafından tanımlanan statik bir işlev tarafından sağlanan [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) makrosu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)