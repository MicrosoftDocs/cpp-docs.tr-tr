---
title: _spawnlpe, _wspawnlpe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _spawnlpe
- _wspawnlpe
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
- spawnlpe
- _wspawnlpe
- _spawnlpe
- wspawnlpe
dev_langs: C++
helpviewer_keywords:
- _wspawnlpe function
- wspawnlpe function
- processes, creating
- spawnlpe function
- _spawnlpe function
- processes, executing new
- process creation
ms.assetid: e171ebfa-70e7-4c44-8331-2a291fc17bd6
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46c3677ac1f00597d4ed435f919bde21b4904582
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="spawnlpe-wspawnlpe"></a>_spawnlpe, _wspawnlpe
Oluşturur ve yeni bir işlem yürütür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
intptr_t _spawnlpe(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wspawnlpe(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `mode`  
 Arama işlemi için yürütme modu.  
  
 `cmdname`  
 Yürütülecek dosyasının yolu.  
  
 `arg0, arg1, ... argn`  
 Bağımsız değişkenler işaretçiler listesi. `arg0` Bağımsız değişken genellikle bir işaretçi `cmdname`. Bağımsız değişkenler `arg1` aracılığıyla `argn` yeni bağımsız değişken listesi form karakter dizelerini işaretçileridir. Aşağıdaki `argn`, olmalıdır bir `NULL` bağımsız değişken listesinin sonuna işaretlemek için işaretçi.  
  
 `envp`  
 Ortam ayarları işaretçiler dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir zaman uyumlu yönteminden döndürülen değer `_spawnlpe` veya `_wspawnlpe` (`_P_WAIT` için belirtilen `mode`) yeni işlem çıkış durumudur. Dönüş değerini zaman uyumsuz bir `_spawnlpe` veya `_wspawnlpe` (`_P_NOWAIT` veya `_P_NOWAITO` için belirtilen `mode`) işlem tanıtıcısı. Çıkış durumu 0 ise işlemi normal şekilde sonlandırıldı. Oluşturulan işlemi çağırmak için sıfır olmayan bir bağımsız değişken özellikle kullanıyorsa, çıkış durumu sıfır olmayan bir değere ayarlayabilirsiniz `exit` yordamı. Yeni işlem pozitif Çıkış durumu açıkça ayarlamadıysanız pozitif Çıkış durumu bir durdurma veya bir kesme nedeniyle anormal bir çıkış gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, `errno` aşağıdaki değerlerden birine ayarlayın.  
  
 `E2BIG`  
 Bağımsız değişken listesi 1024 baytı aşıyor.  
  
 `EINVAL`  
 `mode`bağımsız değişkeni geçersiz.  
  
 `ENOENT`  
 Dosya veya yol bulunamadı.  
  
 `ENOEXEC`  
 Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.  
  
 `ENOMEM`  
 Yeni işlemi yürütmek yeterli bellek yok.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri oluşturur ve yeni bir işlem yürütür, her komut satırı bağımsız değişkeni ayrı bir parametre olarak geçirir ve ortam ayarlarını işaretçileri dizisi geçirir. Bu işlevleri kullanma `PATH` yürütmek için dosyayı bulmak için ortam değişkeni.  
  
 Bu işlevler kendi parametreleri doğrulayın. Her iki `cmdname` veya `arg0` boş bir dize ya da açıklandığı gibi geçersiz parametre işleyicisi null işaretçi çağrılan [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL`ve -1 döndürür. Yeni bir işlem oluşturdu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_spawnlpe`|\<Process.h >|  
|`_wspawnlpe`|\<stdio.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [Çıkış, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)