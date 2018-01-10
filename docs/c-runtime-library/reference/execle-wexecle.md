---
title: _execle, _wexecle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execle
- _wexecle
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
- wexecle
- _execle
- _wexecle
dev_langs: C++
helpviewer_keywords:
- wexecle function
- execle function
- _wexecle function
- _execle function
ms.assetid: 75efa9c5-96b7-4e23-acab-06258901f63a
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce05085a0580cff8f1e3d06260fa9c969b4bc6b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="execle-wexecle"></a>_execle, _wexecle
Yükler ve yeni alt işlemleri yürütür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
intptr_t _execle(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wexecle(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL,  
   const char *const *envp   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cmdname`  
 Yürütülecek dosyasının yolu.  
  
 `arg0, ... argn`  
 Parametreleri işaretçiler listesi.  
  
 `envp`  
 Ortam ayarları işaretçiler dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, bu işlevler için arama işlemi döndürmeyin. Dönüş değeri-1, bu durumda bir hata gösterir `errno` genel değişkeni ayarlanır.  
  
|`errno`değer|Açıklama|  
|-------------------|-----------------|  
|`E2BIG`|Bağımsız değişkenler ve ortam ayarları için gerekli alanı 32 KB'yi aşıyor.|  
|`EACCES`|Belirtilen dosya kilitleme veya paylaşım ihlali var.|  
|`EINVAL`|Geçersiz parametre.|  
|`EMFILE`|Çok fazla dosya açık durumda. (Belirtilen dosya yürütülebilir olup olmadığını belirlemek için açık olması gerekir.)|  
|`ENOENT`|Dosya veya yol bulunamadı.|  
|`ENOEXEC`|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.|  
|`ENOMEM`|Yeni işlemi yürütmek yeterli kullanılabilir bellek yok; kullanılabilir bellek bozulmuş; veya geçersiz bir blok var, arama işlemi düzgün ayrılmamış olduğunu gösterir.|  
  
 Bu dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri yükler ve yeni bir işlem yürütür ve her komut satırı bağımsız değişkeni ayrı bir parametre olarak geçirir ve işaretçiler bir dizi ortam ayarlarını geçirir.  
  
 `_execle` İşlevleri parametrelerini doğrulayın. Varsa `cmdname` veya `arg0` null işaretçi ya da boş bir dize açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve -1 döndürür. Yeni bir işlem başlatılır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|  
|--------------|---------------------|---------------------|  
|`_execle`|\<Process.h >|\<errno.h >|  
|`_wexecle`|\<Process.h > veya \<wchar.h >|\<errno.h >|  
  
 Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [Çıkış, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)