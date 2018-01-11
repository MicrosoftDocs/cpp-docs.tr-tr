---
title: _query_new_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _query_new_handler
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _query_new_handler
- query_new_handler
dev_langs: C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9fc9b3d85ffb2a268ab4e09b082d4678b4efedde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="querynewhandler"></a>_query_new_handler
Geçerli yeni işleyici yordamı adresini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_PNH _query_new_handler(  
   void   
);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirlenen geçerli yeni işleyici yordamının adresi döndürür `_set_new_handler`.  
  
## <a name="remarks"></a>Açıklamalar  
 C++ `_query_new_handler` işlevi döndürür kümesi tarafından C++ geçerli özel durum işleme işlevin adresini [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) işlevi. `_set_new_handler`denetim elde olan bir özel durum işleme işlevi belirtmek için kullanılan **yeni** işleci başarısız bellek ayıramadı. Açıklamalara daha fazla bilgi için bkz: [yeni ve delete işleçleri](../../cpp/new-and-delete-operators.md) C++ dil başvurusu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_query_new_handler`|\<New.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)