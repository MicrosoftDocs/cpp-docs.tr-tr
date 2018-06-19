---
title: CDBPropSet sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d75715ed0dc65fbbf5b581bfea48816e5bd00ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096333"
---
# <a name="cdbpropset-class"></a>CDBPropSet Sınıfı
Öğesinden devralınan **DBPROPSET** yapısı ve anahtar alanları başlatır bir oluşturucu ekler yanı sıra `AddProperty` erişim yöntemi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CDBPropSet : public tagDBPROPSET  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|Bir özellik için özellik kümesi ekler.|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|Oluşturucu.|  
|[Setguıd](../../data/oledb/cdbpropset-setguid.md)|Ayarlar **guidPropertySet** alanını **DBPROPSET** yapısı.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../../data/oledb/cdbpropset-operator-equal.md)|Bir özellik kümesinden diğerine içeriğini atar.|  
  
## <a name="remarks"></a>Açıklamalar  
 OLE DB sağlayıcıları ve tüketicilerin kullanım **DBPROPSET** dizileri geçirmek için yapıları `DBPROP` yapıları. Her `DBPROP` yapısı ayarlanabilir tek bir özelliği temsil eder.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Cdbpropıdset sınıfı](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET yapısı](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [DBPROP yapısı](https://msdn.microsoft.com/en-us/library/ms717970.aspx)