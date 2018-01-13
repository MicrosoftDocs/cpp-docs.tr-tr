---
title: _get_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_osfhandle
- _get_osfhandle
dev_langs: C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b810edac60b08ccc31d6767cb11b7176fb981b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="getosfhandle"></a>_get_osfhandle

Belirtilen dosya tanımlayıcısı ile ilişkili işletim sistemi dosya işleci alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
### <a name="parameters"></a>Parametreler

*FD*  
Varolan bir dosya tanımlayıcısı.  
  
## <a name="return-value"></a>Dönüş Değeri

Bir işletim sistemi dosya işleci döndürür *fd* geçerlidir. Aksi takdirde, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür `INVALID_HANDLE_VALUE` (-1) ve ayarlar `errno` için `EBADF`, geçersiz bir dosya tanıtıcısı belirten.  
  
## <a name="remarks"></a>Açıklamalar

İşletim sistemi (OS) dosya işleyici tarafından elde edilir bir dosyayı kapatmak için `_get_osfhandle`, çağrı [ \_kapatmak](../../c-runtime-library/reference/close.md) dosya tanımlayıcısı üzerinde *fd*. Çağırmayın `CloseHandle` bu işlevin dönüş değeri. Temel işletim sistemi dosya işleci tarafından sahip olunan *fd* tanımlayıcısı dosya ve ne zaman kapalı `_close` üzerinde adlı *fd*. Dosya tanımlayıcısı aitse bir `FILE *` stream, ardından çağırma [fclose](../../c-runtime-library/reference/fclose-fcloseall.md) üzerindeki `FILE *` akışı kapatır dosya tanımlayıcısı ve temel işletim sistemi dosya işleci. Bu durumda, çağırmayın `_close` üzerinde dosya tanımlayıcısı.
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_get_osfhandle`|\<io.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.

[Dosya işleme](../../c-runtime-library/file-handling.md)   
[_close](../../c-runtime-library/reference/close.md)   
[_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
[_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
[_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
