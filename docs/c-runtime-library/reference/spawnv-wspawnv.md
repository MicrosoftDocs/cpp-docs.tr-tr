---
title: _spawnv, _wspawnv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wspawnv
- _spawnv
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wspawnv
- _spawnv
- _wspawnv
dev_langs:
- C++
helpviewer_keywords:
- wspawnv function
- processes, creating
- _spawnv function
- processes, executing new
- process creation
- _wspawnv function
- spawnv function
ms.assetid: 72360ef4-dfa9-44c1-88c1-b3ecb660aa7d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fd29395d5dc2fb913c7d7abb443ab00e646d78f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="spawnv-wspawnv"></a>_spawnv, _wspawnv
Oluşturur ve yeni bir işlem yürütür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
intptr_t _spawnv(  
   int mode,  
   const char *cmdname,  
   const char *const *argv   
);  
intptr_t _wspawnv(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *const *argv   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `mode`  
 Arama işlemi için yürütme modu.  
  
 `cmdname`  
 Yürütülecek dosyasının yolu.  
  
 `argv`  
 Bağımsız değişkenler işaretçiler dizisi. Bağımsız değişken `argv`[0] genellikle bir yol için bir işaretçi gerçek modda program adı için korumalı modda mı ve `argv`[1] aracılığıyla `argv`[`n`] için ilgili yeni bağımsız değişken listesi oluşturuluyor karakter dizeleri. Bağımsız değişken `argv`[`n` + 1] olmalıdır bir `NULL` bağımsız değişken listesinin sonuna işaretlemek için işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir zaman uyumlu yönteminden döndürülen değer `_spawnv` veya `_wspawnv` (`_P_WAIT` için belirtilen `mode`) yeni işlem çıkış durumudur. Dönüş değerini zaman uyumsuz bir `_spawnv` veya `_wspawnv` (`_P_NOWAIT` veya `_P_NOWAITO` için belirtilen `mode`) işlem tanıtıcısı. Çıkış durumu 0 ise işlemi normal şekilde sonlandırıldı. Oluşturulan işlemi özellikle çağırırsa, çıkış durumu sıfır olmayan bir değere ayarlayabilirsiniz `exit` sıfır olmayan bir bağımsız değişkeni ile rutin. Yeni işlem pozitif Çıkış durumu açıkça ayarlamadıysanız pozitif Çıkış durumu bir durdurma veya bir kesme normal olmayan bir çıkış gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, `errno` aşağıdaki değerlerden birine ayarlayın.  
  
 `E2BIG`  
 Bağımsız değişken listesi 1024 baytı aşıyor.  
  
 `EINVAL`  
 `mode` bağımsız değişkeni geçersiz.  
  
 `ENOENT`  
 Dosya veya yol bulunamadı.  
  
 `ENOEXEC`  
 Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.  
  
 `ENOMEM`  
 Yeni işlemi yürütmek yeterli bellek yok.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri oluşturur ve bir dizi işaretçileri için komut satırı bağımsız değişkenleri geçirme, yeni bir işlem yürütür.  
  
 Bu işlevler kendi parametreleri doğrulayın. Her iki `cmdname` veya `argv` null işaretçinin veya `argv` işaret null işaretçi veya `argv[0]` boş bir dize açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL`ve -1 döndürür. Yeni bir işlem oluşturdu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_spawnv`|\<stdio.h > veya \<process.h >|  
|`_wspawnv`|\<stdio.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)   
 [Durdurma](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [Çıkış, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)