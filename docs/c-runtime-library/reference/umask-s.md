---
title: _umask_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _umask_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- unmask_s
- _umask_s
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 315473748d64e572c73746ce6f6fc97ccc912bb0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="umasks"></a>_umask_s
Varsayılan dosya izni maskesi ayarlar. Bir sürümünü [_umask](../../c-runtime-library/reference/umask.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _umask_s(  
   int mode,  
   int * pOldMode  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `mode`  
 Varsayılan izni ayarı.  
  
 [out] `oldMode`  
 İzni ayarı önceki değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir hata kodunu döndürür `Mode` geçerli bir moda belirtmiyor veya `pOldMode` işaretçi `NULL`.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`mode`|`pOldMode`|**Dönüş değeri**|**İçeriği**  `oldMode`|  
|------------|----------------|----------------------|--------------------------------|  
|tüm|`NULL`|`EINVAL`|değiştirilmedi|  
|Geçersiz mod|tüm|`EINVAL`|değiştirilmedi|  
  
 Yukarıdaki koşullardan biri meydana gelirse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `_umask_s` döndürür `EINVAL` ve ayarlar `errno` için `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_umask_s` İşlevi tarafından belirtilen modu için geçerli işlem dosya izni maskesi ayarlar `mode`. Dosya izni maskesi tarafından oluşturulan yeni dosya izni ayarı değiştirir `_creat`, `_open`, veya `_sopen`. Bir bit maskesi 1 ise, dosyanın istenen izin değeri karşılık gelen bit (izin verilmeyen) 0 olarak ayarlanır. Bir bit maskesi 0 ise, karşılık gelen bit sol değişmez. Dosyanın ilk kez kapatılana kadar yeni bir dosya izni ayarı ayarlanmadı.  
  
 Tamsayı ifade `pmode` birini veya her ikisini SYS\STAT tanımlanan aşağıdaki bildirim sabitleri içerir. Y:  
  
 `_S_IWRITE`  
 Yazma izin verilir.  
  
 `_S_IREAD`  
 Okuma izin verilir.  
  
 `_S_IREAD | _S_IWRITE`  
 Okuma ve yazma izin verilir.  
  
 Her iki sabitleri verildiğinde olan bit düzeyinde OR işleci katılan ( `|` ). Varsa `mode` bağımsız değişkeni `_S_IREAD`, okuma izin verilmiyor (dosya salt yazılır). Varsa `mode` bağımsız değişkeni `_S_IWRITE`, yazma izin verilmiyor (dosya salt okunur durumdadır). Örneğin, yazma bit maskesi ayarlarsanız, yeni dosyalar salt okunur olacaktır. MS-DOS ve Windows işletim sistemleri ile tüm dosyaları okunabilir olduğunu unutmayın; salt yazılır izin vermek mümkün değildir. Bu nedenle, ile bit okunur ayarını `_umask_s` dosyanın modları üzerinde hiçbir etkisi olmaz.  
  
 Varsa `pmode` bildirim sabitleri bir birleşimini değil veya başka bir kümesi içerir, sabitleri işlevi yalnızca bu göz ardı eder.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_umask_s`|\<io.h > ve \<sys/stat.h > ve \<sys/types.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_umask_s.c  
/* This program uses _umask_s to set  
 * the file-permission mask so that all future  
 * files will be created as read-only files.  
 * It also displays the old mask.  
 */  
  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask, err;  
  
   /* Create read-only files: */  
   err = _umask_s( _S_IWRITE, &oldmask );  
   if (err)  
   {  
      printf("Error setting the umask.\n");  
      exit(1);  
   }  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
```Output  
Oldmask = 0x0000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)