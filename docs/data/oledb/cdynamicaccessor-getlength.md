---
title: CDynamicAccessor::GetLength | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
dev_langs:
- C++
helpviewer_keywords:
- GetLength method
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dd97a324b0e57cc679e7b467fe387325c0aabcf9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessorgetlength"></a>CDynamicAccessor::GetLength
Belirtilen sütun uzunluğunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
bool GetLength(DBORDINAL nColumn,   
  DBLENGTH* pLength) const throw();  

bool GetLength(const CHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  

bool GetLength(const WCHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nColumn`  
 [in] Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütuna başvuruyor.  
  
 `pColumnName`  
 [in] Sütun adı içeren bir karakter dizesi için bir işaretçi.  
  
 `pLength`  
 [out] Sütun bayt cinsinden uzunluğu içeren tamsayı gösteren bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** belirtilen sütun bulunursa. Aksi takdirde, bu işlevi döndürür **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk geçersiz kılma sütun sayısını alır ve ANSI veya Unicode biçiminde sütun adı ikinci ve üçüncü geçersiz kılmaları sırasıyla gerçekleştirin.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)