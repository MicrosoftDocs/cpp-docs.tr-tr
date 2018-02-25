---
title: CDynamicAccessor::GetValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- GetValue method
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3b572faceb1ea27f05bb1a422a86de4b42f9175c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorgetvalue"></a>CDynamicAccessor::GetValue
Belirtilen sütun için veri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
void* GetValue(DBORDINAL nColumn) const throw();  

void* GetValue(const CHAR* pColumnName) const throw();  

void* GetValue(const WCHAR* pColumnName) const throw();  

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ctype`  
 [in] Herhangi bir veri türü dize türleri dışında işleme şablonlu bir parametre (**CHAR\***, **WCHAR\***), özel işleme gerektirir. `GetValue` ne burada belirttiğiniz üzerinde göre uygun veri türünü kullanır.  
  
 `nColumn`  
 [in] Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütuna başvuruyor.  
  
 `pColumnName`  
 [in] Sütun adı.  
  
 `pData`  
 [out] Belirtilen sütunun içeriğine yönelik işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dize verilerini geçirmek istiyorsanız, nontemplated sürümlerini kullanan `GetValue`. Bu yöntem nontemplated sürümleri dönmek **void\***, belirtilen sütun veri içeren arabelleği parçası işaret eder. Döndürür **NULL** sütun bulunmazsa.  
  
 Tüm diğer veri türleri için şablonlu sürümlerini kullanan basit `GetValue`. Şablonlu sürümleri dönmek **true** başarı veya **false** hatasında.  
  
## <a name="remarks"></a>Açıklamalar  
 Dizeler ve diğer veri türleri içeren sütunlar için şablonlu sürümleri içeren sütunlar döndürmek için nontemplated sürümlerini kullanın.  
  
 Hata ayıklama modunda, bir onaylama alırsa boyutunu `pData` işaret ettiği sütununun boyutuna eşit değil.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)