---
title: "CUtlProps sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps
dev_langs:
- C++
helpviewer_keywords:
- CUtlProps class
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 291094cf913d9c64c91070a281968524227e1376
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cutlprops-class"></a>CUtlProps Sınıfı
OLE DB özelliği arabirimleri çeşitli özelliklerini uygular (örneğin, `IDBProperties`, `IDBProperties`, ve `IRowsetInfo`).  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İçeren sınıf `BEGIN_PROPSET_MAP`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)|Bir özelliği bir özellik kümesinden alır.|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|Bir özelliğini ayarlamadan önce bir değer doğrulamak için kullanılır.|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|Bir tüketici nesnesi oluşturma arabirimdeki bir yöntem çağırdığında isteğe bağlı bir arabirim için isteklerini işler.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|Zincirleme özellikleri işlemek üzere bir özelliğe ayarladıktan sonra çağrılır.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|Bir özelliği bir özellik kümesi ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çoğu bu sınıf, bir uygulama ayrıntılarını olur.  
  
 `CUtlProps` özellikleri dahili olarak ayarlamak için iki üye içeriyor: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) ve [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 Bir özellik kümesi eşleminde kullanılan makroları hakkında daha fazla bilgi için bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) ve [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)