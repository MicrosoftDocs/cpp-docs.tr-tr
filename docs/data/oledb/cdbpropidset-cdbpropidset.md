---
title: CDBPropIDSet::CDBPropIDSet | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropIDSet class, constructor
ms.assetid: e68cc20e-fce2-4cc1-9e9d-05c542334cc8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 19fc024fc0edb11f5211ba51469adb622524454f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdbpropidsetcdbpropidset"></a>CDBPropIDSet::CDBPropIDSet
Oluşturucu. Başlatır **rgProperties**, **cProperties**ve (isteğe bağlı) **guidPropertySet** alanlarının [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDBPropIDSet(const GUID& guid);  

CDBPropIDSet(const CDBPropIDSet& propidset);  

CDBPropIDSet();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guid`  
 [in] Başlatmak için kullanılan bir GUID **guidPropertySet** alan.  
  
 *propidset*  
 [in] Başka bir `CDBPropIDSet` kopya oluşturma için nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDBPropIDSet Class](../../data/oledb/cdbpropidset-class.md)   
 [CDBPropIDSet::SetGUID](../../data/oledb/cdbpropidset-setguid.md)