---
title: Cdbpropıdset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropIDSet class
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67bfd11a46d8e0c852c1881ff8874b7fbd817164
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096957"
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet Sınıfı
Öğesinden devralınan **DBPROPIDSET** yapısı ve anahtar alanları başlatır bir oluşturucu ekler yanı sıra [Addpropertyıd](../../data/oledb/cdbpropidset-addpropertyid.md) erişim yöntemi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|Bir özellik için özellik kimliği kümesi ekler.|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|Oluşturucu.|  
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