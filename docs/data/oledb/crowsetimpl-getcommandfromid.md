---
title: "CRowsetImpl::getcommandfromıd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
dev_langs:
- C++
helpviewer_keywords:
- GetCommandFromID method
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 64db10bec645b357107134dc1838e8840f8be6fa
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetimplgetcommandfromid"></a>CRowsetImpl::GetCommandFromID
Biri veya her ikisi parametreleri dize değerlerini içeriyorsa ve bu durumda, bakar kopyalar dize değerleri veri üyelerine [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pTableID`  
 [in] Bir işaretçi **DBID** tablo kimliği temsil eden  
  
 `pIndexID`  
 [in] Bir işaretçi **DBID** dizin kimliği temsil eden  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından bir statik yukarı çevrim aracılığıyla çağrılır `CRowsetImpl` veri üyeleri doldurmak için [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). Varsayılan olarak, bu yöntem birini veya her ikisini parametreleri dize değerleri içerip içermediğini görmek için denetler. Dize değerlerini içerir, bu yöntem veri üyelerine dize değerleri kopyalar. Bu imza yöntemiyle yerleştirerek, `CRowsetImpl`-türetilmiş sınıf, temel uygulamayı yerine yönteminiz olarak adlandırılır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowsetImpl sınıfı](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)