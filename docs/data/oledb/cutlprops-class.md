---
title: "CUtlProps sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CUtlProps
dev_langs: C++
helpviewer_keywords: CUtlProps class
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0f57894bc22cc469e000663d871be7c4739db22e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cutlprops-class"></a>CUtlProps Sınıfı
OLE DB özelliği arabirimleri çeşitli özelliklerini uygular (örneğin, `IDBProperties`, `IDBProperties`, ve `IRowsetInfo`).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
|[Isvalidvalue](../../data/oledb/cutlprops-isvalidvalue.md)|Bir özelliğini ayarlamadan önce bir değer doğrulamak için kullanılır.|  
|[Onınterfacerequested](../../data/oledb/cutlprops-oninterfacerequested.md)|Bir tüketici nesnesi oluşturma arabirimdeki bir yöntem çağırdığında isteğe bağlı bir arabirim için isteklerini işler.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|Zincirleme özellikleri işlemek üzere bir özelliğe ayarladıktan sonra çağrılır.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|Bir özelliği bir özellik kümesi ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çoğu bu sınıf, bir uygulama ayrıntılarını olur.  
  
 `CUtlProps`özellikleri dahili olarak ayarlamak için iki üye içeriyor: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) ve [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 Bir özellik kümesi eşleminde kullanılan makroları hakkında daha fazla bilgi için bkz: [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) ve [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)