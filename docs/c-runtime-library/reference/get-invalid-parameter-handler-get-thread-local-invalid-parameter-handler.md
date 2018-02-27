---
title: _get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
dev_langs:
- C++
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f52aecad7e33464c429dae982cb810d6be7bf9ad
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="getinvalidparameterhandler-getthreadlocalinvalidparameterhandler"></a>_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler
CRT geçersiz bağımsız değişken algıladığında çağrılan işlevi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_invalid_parameter_handler _get_invalid_parameter_handler(void);  
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi ayarlanmış geçersiz parametre işleyicisi işlevi ya da hiçbiri ayarlarsanız, null işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_get_invalid_parameter_handler` İşlevi alır ayarlanmış genel geçersiz parametre işleyicisi. Hiçbir genel geçersiz parametre işleyicisi ayarlarsanız null işaretçi döndürür. Benzer şekilde, `_get_thread_local_invalid_parameter_handler` hiçbir işleyici ayarlandıysa, geçerli iş parçacığı yerel geçersiz parametre işleyicisi adlı üzerinde iş parçacığı ya da boş bir imleç alır. Genel ve iş parçacığı yerel geçersiz parametre işleyicilerini ayarlama hakkında daha fazla bilgi için bkz: [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).  
  
 Döndürülen geçersiz parametre işleyicisi işlev işaretçisi aşağıdaki türü vardır:  
  
```C  
typedef void (__cdecl* _invalid_parameter_handler)(  
    wchar_t const*,  
    wchar_t const*,  
    wchar_t const*,   
    unsigned int,  
    uintptr_t  
    );  
```  
  
 Prototip geçersiz parametre işleyicisi hakkında daha fazla bilgi için bkz: [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_get_invalid_parameter_handler`, `_get_thread_local_invalid_parameter_handler`|C: \<stdlib.h ><br /><br /> C++: \<cstdlib > veya \<stdlib.h >|  
  
 `_get_invalid_parameter_handler` Ve `_get_thread_local_invalid_parameter_handler` Microsoft belirli işlevlerdir. Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)   
 [CRT İşlevlerinin Gelişmiş Güvenlik Sürümleri](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)