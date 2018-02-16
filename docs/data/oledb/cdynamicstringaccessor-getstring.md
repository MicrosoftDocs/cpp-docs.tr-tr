---
title: CDynamicStringAccessor::GetString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
dev_langs:
- C++
helpviewer_keywords:
- GetString method
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c3ccef4046928be7ce62c845c99538f894bd1b3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicstringaccessorgetstring"></a>CDynamicStringAccessor::GetString
Belirtilen sütun verileri dize olarak alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      BaseType* GetString(DBORDINAL nColumn) const throw();  

BaseType* GetString(const CHAR* pColumnName) const throw();  

BaseType* GetString(const WCHAR* pColumnName) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nColumn`  
 [in] Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütuna başvuruyor.  
  
 `pColumnName`  
 [in] Sütun adı içeren bir karakter dizesi için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dize değeri için bir işaretçi belirtilen sütundan aldı. Değer ***BaseType***, hangi **CHAR** veya **WCHAR** _UNICODE veya tanımlanır bağlı olarak. Belirtilen sütun bulunmazsa NULL döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 İkinci sütun adı formu alır ANSI dize olarak geçersiz. Üçüncü sütun adı formu alır bir UNICODE dizesi geçersiz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicStringAccessor Sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)