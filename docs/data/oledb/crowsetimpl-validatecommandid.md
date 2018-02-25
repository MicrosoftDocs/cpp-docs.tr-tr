---
title: CRowsetImpl::ValidateCommandID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
dev_langs:
- C++
helpviewer_keywords:
- ValidateCommandID method
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f92e8f51f5056cc4caf82d9baebe2acf37972284
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplvalidatecommandid"></a>CRowsetImpl::ValidateCommandID
Her iki bakın veya her ikisini de denetler **DBID**s dize değerleri içeren ve varsa, bunları kendi veri üyelerine kopyalar [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pTableID`  
 [in] Bir işaretçi **DBID** tablo kimliğine temsil eden  
  
 `pIndexID`  
 [in] Bir işaretçi **DBID** dizin kimliğini temsil eden  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından bir statik yukarı çevrim aracılığıyla çağrılır `CRowsetImpl` veri üyelerine doldurmak için [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). Varsayılan olarak, bu yöntem, her iki bakın veya her ikisini de denetler. **DBID**s dize değerleri içeren ve varsa, bunları kendi veri üyelerine kopyalar. Bu imza yöntemiyle yerleştirerek, `CRowsetImpl`-türetilmiş sınıf, temel uygulamayı yerine yönteminiz olarak adlandırılır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowsetImpl sınıfı](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)