---
title: _execl, _wexecl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _execl
- _wexecl
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
- _execl
- _wexecl
- wexecl
dev_langs:
- C++
helpviewer_keywords:
- _execl function
- wexecl function
- _wexecl function
- execl function
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 893de6ced476c36ff704a9e9ae01b2d38c8b81af
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="execl-wexecl"></a>_execl, _wexecl
Yükler ve yeni alt işlemleri yürütür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
intptr_t _execl(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wexecl(  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cmdname`  
 Yürütülecek dosyasının yolu.  
  
 `arg0, ... argn`  
 Parametreleri işaretçiler listesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, bu işlevler için arama işlemi döndürmeyin. Dönüş değeri-1, bu durumda bir hata gösterir `errno` genel değişkeni ayarlanır.  
  
|errno değeri|Açıklama|  
|-----------------|-----------------|  
|`E2BIG`|Ortam ayarları ve bağımsız değişkenler için gereken alanı 32 KB'yi aşıyor.|  
|`EACCES`|Belirtilen dosya kilitleme veya paylaşım ihlali var.|  
|`EINVAL`|Geçersiz parametre (bir veya daha fazla parametre olduğu bir null işaretçinin veya boş dize).|  
|`EMFILE`|Çok fazla dosya açık (belirtilen dosya yürütülebilir olup olmadığını belirlemek için açık olması gerekir).|  
|`ENOENT`|Dosya veya yol bulunamadı.|  
|`ENOEXEC`|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.|  
|`ENOMEM`|Yeni işlemi yürütmek yeterli kullanılabilir bellek yok; kullanılabilir bellek bozulmuş; veya arama işlemi düzgün ayrılmamış olduğunu belirten bir geçersiz blok yok.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri yükler ve ayrı bir parametre olarak her komut satırı bağımsız değişken geçirme, yeni bir işlem yürütür. İlk bağımsız değişken, komut veya yürütülebilir dosya adı ve ikinci bağımsız değişkeni, ilk olarak aynı olmalıdır. Bu duruma `argv[0]` yürütülen işleminde. Üçüncü bağımsız değişkeni ilk bağımsız değişkeni olan `argv[1]`, yürütülmekte olan işlemin.  
  
 `_execl` İşlevleri parametrelerini doğrulayın. Her iki `cmdname` veya `arg0` bir null işaretçinin ya da boş dize açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) devam etmek için yürütülmesine izin veriliyorsa, bu işlevler ayarlayın.`errno` için `EINVAL` ve -1 döndürür. Yeni bir işlem yürütülür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|  
|--------------|---------------------|---------------------|  
|`_execl`|\<Process.h >|\<errno.h >|  
|`_wexecl`|\<Process.h > veya \<wchar.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [Durdurma](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [Çıkış, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)