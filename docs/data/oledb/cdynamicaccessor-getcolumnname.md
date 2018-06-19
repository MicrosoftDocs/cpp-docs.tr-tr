---
title: CDynamicAccessor::GetColumnName | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicAccessor::GetColumnName
- GetColumnName
- ATL.CDynamicAccessor.GetColumnName
- CDynamicAccessor::GetColumnName
- CDynamicAccessor.GetColumnName
dev_langs:
- C++
helpviewer_keywords:
- GetColumnName method
ms.assetid: 96a7452a-1f5b-41e9-ab37-88dac026f961
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3ad9a1830be94a2c0d3649bf72a6d25af1fb4e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090363"
---
# <a name="cdynamicaccessorgetcolumnname"></a>CDynamicAccessor::GetColumnName
Belirtilen sütunun adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      LPOLESTR GetColumnName(DBORDINAL nColumn) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nColumn`  
 [in] Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütuna başvuruyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen sütunun adı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)