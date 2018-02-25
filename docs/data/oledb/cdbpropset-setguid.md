---
title: "CDBPropSet::setguıd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
- AddProperty method
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: edf9720e0f116060a06ffa56bf5c3e6c4c8691e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cdbpropsetsetguid"></a>CDBPropSet::SetGUID
Ayarlar **guidPropertySet** alanındaki **DBPROPSET** yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guid`  
 [in] Ayarlamak için kullanılan bir GUID **guidPropertySet** alanını [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu alan ayarlanabilir [Oluşturucusu](../../data/oledb/cdbpropset-cdbpropset.md) de.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDBPropSet Sınıfı](../../data/oledb/cdbpropset-class.md)