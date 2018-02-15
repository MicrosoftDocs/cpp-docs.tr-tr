---
title: _set_new_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _set_new_mode
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
- set_new_mode
- _set_new_mode
dev_langs:
- C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0c49e60201374f2c9cc916d65077c2800ed48ab
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="setnewmode"></a>_set_new_mode
Yeni bir işleyici modu için ayarlar `malloc`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `newhandlermode`  
 Yeni işleyici modu için `malloc`; geçerli değer 0 veya 1'dir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Mod kümesi için önceki işleyicisini döndürür `malloc`. 1 değeri, gösterir, bellek ayırma hatası dönüş `malloc` daha önce yeni işleyici yordamı; adlı dönüş değerinin 0, belirtmiyor olduğunu gösterir. Varsa `newhandlermode` bağımsız değişkeni 0 veya 1 eşit değil, -1 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 C++ `_set_new_mode` işlevi ayarlar için yeni işleyici modu [malloc](../../c-runtime-library/reference/malloc.md). Yeni işleyici modunu gösterir, hatasında kullanılıp `malloc` belirlediği yeni işleyici yordamı çağırmaktır [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Varsayılan olarak, `malloc` yeni işleyici yordamı bellek ayırma hatası çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, `malloc` bellek ayırmak başarısız `malloc` yeni işleyici yordamını aynı çağırıyor biçimi `new` işleci mu aynı nedenden dolayı başarısız olduğunda. Daha fazla bilgi için bkz: [yeni](../../cpp/new-operator-cpp.md) ve [silmek](../../cpp/delete-operator-cpp.md) işleçleri *C++ dil başvurusu*. Varsayılan değer geçersiz kılmak için arayın:  
  
```  
_set_new_mode(1)  
```  
  
 program veya Newmode.obj bağlantısıyla erkenden (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).  
  
 Bu işlev, parametre doğrular. Varsa `newhandlermode` 0 veya 1, işlev dışındaki çağırır geçersiz parametre işleyicisi olarak herhangi bir şey açıklanan [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **_** `set_new_mode` -1 döndürür ve ayarlar `errno` için `EINVAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_set_new_mode`|\<New.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [Boş](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [_query_new_mode](../../c-runtime-library/reference/query-new-mode.md)