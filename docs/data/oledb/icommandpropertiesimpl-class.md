---
title: Icommandpropertiesımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- ICommandPropertiesImpl class
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 25be1548bd41f832a007f102c138fc01f8818774
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099007"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl Sınıfı
Bir uygulamasını sağlar [ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
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