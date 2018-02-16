---
title: _getdcwd_nolock, _wgetdcwd_nolock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wgetdcwd_nolock
- _getdcwd_nolock
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
apitype: DLLExport
f1_keywords:
- _wgetdcwd_nolock
- tgetdcwd_nolock
- wgetdcwd_nolock
- _getdcwd_nolock
- _tgetdcwd_nolock
- getdcwd_nolock
dev_langs:
- C++
helpviewer_keywords:
- getdcwd_nolock function
- _tgetdcwd_nolock function
- working directory
- tgetdcwd_nolock function
- _getdcwd_nolock function
- current working directory
- wgetdcwd_nolock function
- _wgetdcwd_nolock function
- directories [C++], current working
ms.assetid: d9bdf712-43f8-4173-8f9a-844e82beaa97
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c1d9f4c57ef942f11f5e5dee79356a3e2d7f47a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="getdcwdnolock-wgetdcwdnolock"></a>_getdcwd_nolock, _wgetdcwd_nolock
Geçerli çalışma dizininin tam yolu belirtilen sürücü üzerindeki alır.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_getdcwd_nolock(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd_nolock(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `drive`  
 Disk sürücüsü.  
  
 `buffer`  
 Yol için depolama konumu.  
  
 `maxlen`  
 Yol karakter cinsinden en büyük uzunluğu: `char` için `_getdcwd` ve `wchar_t` için `_wgetdcwd`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 See [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_getdcwd_nolock` ve `_wgetdcwd_nolock` özdeş `_getdcwd` ve `_wgetdcwd`, sırasıyla dışında diğer iş parçacıkları tarafından girişime korunmaz. Bunlar başka bir iş parçacığı kilitleme zahmetine değil olduğundan daha hızlı olabilir. Bu işlevler yalnızca iş parçacığı bağlamları tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işleme olduğu gibi kullanın.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd_nolock`|`_getdcwd_nolock`|`_getdcwd_nolock`|`_wgetdcwd_nolock`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_getdcwd_nolock`|\<Direct.h >|  
|`_wgetdcwd_nolock`|\<Direct.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)