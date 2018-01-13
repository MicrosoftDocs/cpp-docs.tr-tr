---
title: "Cdbpropıdset sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
dev_langs: C++
helpviewer_keywords: CDBPropIDSet class
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c75b357b912adc67351510e745fa46f246a74b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet Sınıfı
Öğesinden devralınan **DBPROPIDSET** yapısı ve anahtar alanları başlatır bir oluşturucu ekler yanı sıra [Addpropertyıd](../../data/oledb/cdbpropidset-addpropertyid.md) erişim yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Addpropertyıd](../../data/oledb/cdbpropidset-addpropertyid.md)|Bir özellik için özellik kimliği kümesi ekler.|  
|[Cdbpropıdset](../../data/oledb/cdbpropidset-cdbpropidset.md)|Oluşturucu.|  
|[Setguıd](../../data/oledb/cdbpropidset-setguid.md)|Özellik kimliği GUID ayarlar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../../data/oledb/cdbpropidset-operator-equal.md)|Atar başka bir özellik kimliği içeriğini ayarlayın.|  
  
## <a name="remarks"></a>Açıklamalar  
 OLE DB tüketicileri kullanım **DBPROPIDSET** özellik kimlikleri için tüketici istediği özellik bilgilerini almak bir dizi geçirmek için yapıları. Tek bir tanımlanan özellikler [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) yapısı bir özellik kümesine ait.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)