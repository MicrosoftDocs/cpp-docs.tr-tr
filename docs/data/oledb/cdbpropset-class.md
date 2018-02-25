---
title: "CDBPropSet sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 716b0785ba4f785063709d989eb95c5c4f390f4a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|Ayarlar **guidPropertySet** alanını **DBPROPSET** yapısı.|  
  
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
 [CDBPropIDSet Class](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET yapısı](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [DBPROP yapısı](https://msdn.microsoft.com/en-us/library/ms717970.aspx)