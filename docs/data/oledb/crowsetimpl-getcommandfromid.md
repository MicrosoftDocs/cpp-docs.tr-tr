---
title: CRowsetImpl::getcommandfromıd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
dev_langs:
- C++
helpviewer_keywords:
- GetCommandFromID method
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f79e9287bf8d546ba5007257899a6b6ddc27ad40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091300"
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