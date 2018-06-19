---
title: CDynamicAccessor::GetColumnFlags | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetColumnFlags
- ATL::CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnFlags
- CDynamicAccessor::GetColumnFlags
- GetColumnFlags
dev_langs:
- C++
helpviewer_keywords:
- GetColumnFlags method
ms.assetid: b2ba2f3a-2c61-4a49-abfb-75823908ccf4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9cb4e439ab650793dcbafa79092d03b53271e45a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094702"
---
# <a name="cdynamicaccessorgetcolumnflags"></a>CDynamicAccessor::GetColumnFlags
Sütun özelliklerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
bool GetColumnFlags(DBORDINAL nColumn,   
  DBCOLUMNFLAGS* pFlags) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nColumn`  
 [in] Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütuna başvuruyor.  
  
 `pFlags`  
 [out] Sütun özelliklerini açıklayan bir bit maskesi için bir işaretçi. "DBCOLUMNFLAGS numaralandırılan türü" bölümüne bakın [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** sütun özelliklerini başarıyla alınırsa. Aksi takdirde, döndürür **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 Sütun numarası bir uzaklık. Sütun sıfır özel bir durum oluşturur; Bu yer işaretinin kullanılabilir olur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)