---
title: CDynamicAccessor::SetValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- SetValue method
ms.assetid: ecc18850-96e5-4845-abe5-ab34ad467238
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2227564d321ca3c5c590c11fca52b906ebc911ca
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessorsetvalue"></a>CDynamicAccessor::SetValue
Belirtilen sütun için veri depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <class ctype>
bool SetValue(   
   DBORDINAL nColumn,   
   constctype& data) throw( );  

template <class ctype>    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data) throw( );  

template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ctype`  
 [in] Herhangi bir veri türü dize türleri dışında işleme şablonlu bir parametre (**CHAR\***, **WCHAR\***), özel işleme gerektirir. `GetValue` ne burada belirttiğiniz üzerinde göre uygun veri türünü kullanır.  
  
 `pColumnName`  
 [in] Sütun adı içeren bir karakter dizesi için bir işaretçi.  
  
 `data`  
 [in] Verileri içeren bellek işaretçisi.  
  
 `nColumn`  
 [in] Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütuna başvuruyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dize verilerini ayarlamak istiyorsanız, nontemplated sürümlerini kullanan `GetValue`. Bu yöntem nontemplated sürümleri dönmek **void\***, belirtilen sütun veri içeren arabelleği parçası işaret eder. Döndürür **NULL** sütun bulunmazsa.  
  
 Tüm diğer veri türleri için şablonlu sürümlerini kullanan basit `GetValue`. Şablonlu sürümleri dönmek **true** başarı veya **false** hatasında.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)