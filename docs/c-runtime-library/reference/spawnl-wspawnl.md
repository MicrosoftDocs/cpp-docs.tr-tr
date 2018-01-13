---
title: _spawnl, _wspawnl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wspawnl
- _spawnl
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
- spawnl
- wspawnl
- _wspawnl
- _spawnl
dev_langs: C++
helpviewer_keywords:
- spawnl function
- processes, creating
- _spawnl function
- processes, executing new
- _wspawnl function
- wspawnl function
- process creation
ms.assetid: dd4584c9-7173-4fc5-b93a-6e7d3c2316d7
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50c1dc9f064b5920a136766ffa17628501d732be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="spawnl-wspawnl"></a>_spawnl, _wspawnl
Oluşturur ve yeni bir işlem yürütür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
intptr_t _spawnl(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wspawnl(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `mode`  
 Arama işlemi için yürütme modu.  
  
 `cmdname`  
 Yürütülecek dosyasının yolu.  
  
 `arg0, arg1, ... argn`  
 Bağımsız değişkenler işaretçiler listesi. `arg0` Bağımsız değişkeni genellikle bir işaretçidir `cmdname`. Bağımsız değişkenler `arg1` aracılığıyla `argn` yeni bağımsız değişken listesi oluşturuluyor karakter dizelerini işaretçileridir. Aşağıdaki `argn`, olmalıdır bir `NULL` bağımsız değişken listesinin sonuna işaretlemek için işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir zaman uyumlu yönteminden döndürülen değer `_spawnl` veya `_wspawnl` (`_P_WAIT` için belirtilen `mode`) yeni işlem çıkış durumudur. Dönüş değerini zaman uyumsuz bir `_spawnl` veya `_wspawnl` (`_P_NOWAIT` veya `_P_NOWAITO` için belirtilen `mode`) işlem tanıtıcısı. Çıkış durumu 0 ise işlemi normal şekilde sonlandırıldı. Oluşturulan işlemi özellikle çağırırsa, çıkış durumu sıfır olmayan bir değere ayarlayabilirsiniz `exit` sıfır olmayan bir bağımsız değişkeni ile rutin. Yeni işlem pozitif Çıkış durumu açıkça ayarlamadıysanız pozitif Çıkış durumu bir durdurma veya bir kesme normal olmayan bir çıkış gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, `errno` aşağıdaki değerlerden birine ayarlayın.  
  
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
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Bu işlevler kendi parametreleri doğrulayın. Her iki `cmdname` veya `arg0` boş bir dize ya da açıklandığı gibi geçersiz parametre işleyicisi null işaretçi çağrılan [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL`ve -1 döndürür. Yeni bir işlem oluşturdu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri oluşturur ve ayrı bir parametre olarak her komut satırı bağımsız değişken geçirme, yeni bir işlem yürütür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_spawnl`|\<Process.h >|  
|`_wspawnl`|\<stdio.h > veya \<wchar.h >|  
  
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