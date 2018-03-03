---
title: "Özel durum makroları işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
dev_langs:
- C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 424a65c44d7bb22d1fef6e21e1892967ecd3e9b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling-macros"></a>Özel durum işleme makroları
Bu makroları özel durum işleme için destek sağlar.  
  
|||  
|-|-|  
|[_ATLCATCH](#_atlcatch)|Deyim ilişkili oluşan hataları işlemek için `_ATLTRY`.|  
|[_ATLCATCHALL](#_atlcatchall)|Deyim ilişkili oluşan hataları işlemek için `_ATLTRY`.|  
|[_ATLTRY](#_atltry)|Burada bir hata muhtemelen oluşabilir korumalı kod bölümünde işaretler.|  
  
## <a name="requirements"></a>Gereksinimleri:
**Başlık:** atldef.h

##  <a name="_atlcatch"></a>_ATLCATCH  
 Deyim ilişkili oluşan hataları işlemek için `_ATLTRY`.  
  
```
_ATLCATCH(e)
```  
  
### <a name="parameters"></a>Parametreler  
 *e*  
 Catch özel durum.  
  
### <a name="remarks"></a>Açıklamalar  
 İle birlikte kullanılan `_ATLTRY`. C++ için çözümler [(CAtlException e) catch](../../cpp/try-throw-and-catch-statements-cpp.md) C++ özel durumlarını belirli bir türde işlemek için.  
  
##  <a name="_atlcatchall"></a>_ATLCATCHALL  
 Deyim ilişkili oluşan hataları işlemek için `_ATLTRY`.  
  
```
_ATLCATCHALL
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle birlikte kullanılan `_ATLTRY`. C++ için çözümler [catch(...) ](../../cpp/try-throw-and-catch-statements-cpp.md) tüm türleri C++ özel durum işleme için.  
  
##  <a name="_atltry"></a>_ATLTRY  
 Burada bir hata muhtemelen oluşabilir korumalı kod bölümünde işaretler.  
  
```
_ATLTRY
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle birlikte kullanılan [_ATLCATCH](#_atlcatch) veya [_ATLCATCHALL](#_atlcatchall). C++ simgenin çözümler [deneyin](../../cpp/try-throw-and-catch-statements-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
