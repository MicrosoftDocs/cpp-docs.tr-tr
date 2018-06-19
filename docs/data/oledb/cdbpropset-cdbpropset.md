---
title: CDBPropSet::CDBPropSet | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class, constructor
ms.assetid: 02ae5d9e-c067-47ca-8111-a03e86b5626b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 58c3639d6c849a4b57ba1b0a75a7840def977556
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090480"
---
# <a name="cdbpropsetcdbpropset"></a>CDBPropSet::CDBPropSet
Oluşturucu. Başlatır **rgProperties**, **cProperties**, ve **guidPropertySet** alanlarının [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDBPropSet(const GUID& guid);  

CDBPropSet(const CDBPropSet& propset);  

CDBPropSet();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guid`  
 [in] Başlatmak için kullanılan bir GUID **guidPropertySet** alan.  
  
 *propset*  
 [in] Başka bir `CDBPropSet` kopya oluşturma için nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDBPropSet sınıfı](../../data/oledb/cdbpropset-class.md)   
 [CDBPropSet::setguıd](../../data/oledb/cdbpropset-setguid.md)   
 [DBPROP yapısı](https://msdn.microsoft.com/en-us/library/ms717970.aspx)