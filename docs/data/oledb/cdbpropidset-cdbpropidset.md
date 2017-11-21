---
title: "Cdbpropıdset::cdbpropıdset | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
dev_langs: C++
helpviewer_keywords: CDBPropIDSet class, constructor
ms.assetid: e68cc20e-fce2-4cc1-9e9d-05c542334cc8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 310d5eb22c2fb57b001a9a5e40599c163358319f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdbpropidsetcdbpropidset"></a>CDBPropIDSet::CDBPropIDSet
Oluşturucu. Başlatır **rgProperties**, **cProperties**ve (isteğe bağlı) **guidPropertySet** alanlarının [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      CDBPropIDSet(  
   const GUID& guid   
);  
CDBPropIDSet(   
   const CDBPropIDSet& propidset    
);  
CDBPropIDSet( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guid`  
 [in] Başlatmak için kullanılan bir GUID **guidPropertySet** alan.  
  
 *propidset*  
 [in] Başka bir `CDBPropIDSet` kopya oluşturma için nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cdbpropıdset sınıfı](../../data/oledb/cdbpropidset-class.md)   
 [Cdbpropıdset::setguıd](../../data/oledb/cdbpropidset-setguid.md)