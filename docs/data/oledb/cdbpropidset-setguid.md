---
title: "Cdbpropıdset::setguıd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs: C++
helpviewer_keywords: SetGUID method
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d91cc0374474a38bd2caba66ab98003852195f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdbpropidsetsetguid"></a>CDBPropIDSet::SetGUID
GUID alanı ayarlar **DBPROPIDSET** yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guid`  
 [in] Ayarlamak için kullanılan bir GUID **guidPropertySet** alanını [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu alan ayarlanabilir [Oluşturucusu](../../data/oledb/cdbpropidset-cdbpropidset.md) de. Bu sınıf için varsayılan oluşturucu kullanıyorsanız bu işlevini çağırın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cdbpropıdset sınıfı](../../data/oledb/cdbpropidset-class.md)