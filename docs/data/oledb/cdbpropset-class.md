---
title: "CDBPropSet sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
dev_langs: C++
helpviewer_keywords: CDBPropSet class
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b2523e37c3015bb49d123e99f39c1ea4bdb9045
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropset-class"></a>CDBPropSet Sınıfı
Öğesinden devralınan **DBPROPSET** yapısı ve anahtar alanları başlatır bir oluşturucu ekler yanı sıra `AddProperty` erişim yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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