---
title: CDynamicStringAccessor::SetString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d425159b1234a152fc5e914db4a664abd91e599
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicstringaccessorsetstring"></a>CDynamicStringAccessor::SetString
Belirtilen sütun veri dize olarak ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
HRESULT SetString(DBORDINAL nColumn,  
  BaseType* data) throw();  


HRESULT SetString(const CHAR* pColumnName,  
   BaseType* data) throw();  


HRESULT SetString(const WCHAR* pColumnName,  
   BaseType* data) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nColumn`  
 [in] Sütun numarası. Sütun numaraları 1 ile başlar. Özel değeri 0, varsa yer işareti sütuna başvuruyor.  
  
 `pColumnName`  
 [in] Sütun adı içeren bir karakter dizesi için bir işaretçi.  
  
 `data`  
 [in] Belirtilen sütuna yazılacak dize verilerini gösteren bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen sütun kümesi dize değeri için bir işaretçi. Değer `BaseType`, hangi `CHAR` veya `WCHAR` mı bağlı olarak `_UNICODE` veya tanımlanır.  
  
## <a name="remarks"></a>Açıklamalar  
 İkinci sütun adı bir ANSI dize olarak form alır geçersiz kılabilir ve üçüncü sütun adı bir UNICODE dizesi olarak form alır geçersiz kıl.  
  
 Varsa `_SECURE_ATL` tanımlanan sıfır olmayan bir değere sahip olması için bir çalışma zamanı onaylama hatası olduğunda oluşturulması giriş `data` dizesi izin verilen uzunluk üst başvurulan veri sütununun sınırından daha uzun. Aksi takdirde, izin verilen uzunluk üst sınırından daha uzun olması durumunda giriş dizesi kesilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicStringAccessor Sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)