---
title: _execvp, _wexecvp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execvp
- _wexecvp
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
- _execvp
- wexecvp
- _wexecvp
dev_langs: C++
helpviewer_keywords:
- _execvp function
- _wexecvp function
- wexecvp function
- execvp function
ms.assetid: a4db15df-b204-4987-be7c-de84c3414380
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 431a79be49b723c874409c030a166a7ef78b9730
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="execvp-wexecvp"></a>_execvp, _wexecvp
Yükler ve yeni alt işlemleri yürütür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
intptr_t _execvp(   
   const char *cmdname,  
   const char *const *argv   
);  
intptr_t _wexecvp(   
   const wchar_t *cmdname,  
   const wchar_t *const *argv   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cmdname`  
 Yürütülecek dosyasının yolu.  
  
 `argv`  
 Parametreleri işaretçiler dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, bu işlevler için arama işlemi döndürmeyin. Dönüş değeri-1, bu durumda bir hata gösterir `errno` genel değişkeni ayarlanır.  
  
|`errno`değer|Açıklama|  
|-------------------|-----------------|  
|`E2BIG`|Ortam ayarları ve bağımsız değişkenler için gereken alanı 32 KB'yi aşıyor.|  
|`EACCES`|Belirtilen dosya kilitleme veya paylaşım ihlali var.|  
|`EINVAL`|Geçersiz parametre.|  
|`EMFILE`|Çok fazla dosya açık (belirtilen dosya yürütülebilir olup olmadığını belirlemek için açık olması gerekir).|  
|`ENOENT`|Dosya veya yol bulunamadı.|  
|`ENOEXEC`|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.|  
|`ENOMEM`|Yeni işlemi yürütmek yeterli kullanılabilir bellek yok; kullanılabilir bellek bozulmuş; veya arama işlemi düzgün ayrılmamış olduğunu belirten bir geçersiz blok yok.|  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri yükler ve işaretçiler bir dizi komut satırı bağımsız değişkenleri geçirme ile kullanarak yeni bir işlem yürütür `PATH` yürütmek için dosyayı bulmak için ortam değişkeni.  
  
 `_execvp` İşlevleri parametrelerini doğrulayın. Varsa `cmdname` null işaretçinin veya `argv` null işaretçi, boş bir dizi işaretçi veya dizinin ilk bağımsız değişken olarak boş bir dize içeriyorsa, bu işlevler geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve -1 döndürür. Hiçbir işlem başlatılır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|  
|--------------|---------------------|---------------------|  
|`_execvp`|\<Process.h >|\<errno.h >|  
|`_wexecvp`|\<Process.h > veya \<wchar.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
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
 [Sistem, _wsystem](../../c-runtime-library/reference/system-wsystem.md)