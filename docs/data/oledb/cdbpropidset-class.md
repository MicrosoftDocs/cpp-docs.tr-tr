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
ms.openlocfilehash: 996e1a04e9870a9cd3cf02ca6a8c7c05a1dc3e56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)