---
title: CDBPropIDSet::SetGUID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 32f697e07c850ab71249614a0479aecca4f7caa2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdbpropidsetsetguid"></a>CDBPropIDSet::SetGUID
GUID alanı ayarlar **DBPROPIDSET** yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guid`  
 [in] Ayarlamak için kullanılan bir GUID **guidPropertySet** alanını [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu alan ayarlanabilir [Oluşturucusu](../../data/oledb/cdbpropidset-cdbpropidset.md) de. Bu sınıf için varsayılan oluşturucu kullanıyorsanız bu işlevini çağırın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDBPropIDSet Sınıfı](../../data/oledb/cdbpropidset-class.md)