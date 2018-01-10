---
title: _umask | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _umask
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
f1_keywords: _umask
dev_langs: C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 48adac5a394e782e60d03cc5aadfa094627331b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="umask"></a>_umask
Varsayılan dosya izni maskesi ayarlar. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [_umask_s](../../c-runtime-library/reference/umask-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pmode`  
 Varsayılan izni ayarı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_umask`önceki değerini döndürür `pmode`. Döndürülen hata yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 `_umask` İşlevi tarafından belirtilen modu için geçerli işlem dosya izni maskesi ayarlar `pmode`. Dosya izni maskesi tarafından oluşturulan yeni dosya izni ayarı değiştirir `_creat`, `_open`, veya `_sopen`. Bir bit maskesi 1 ise, dosyanın istenen izin değeri karşılık gelen bit (izin verilmeyen) 0 olarak ayarlanır. Bir bit maskesi 0 ise, karşılık gelen bit sol değişmez. Dosyanın ilk kez kapatılana kadar yeni bir dosya izni ayarı ayarlanmadı.  
  
 Tamsayı ifade `pmode` birini veya her ikisini SYS\STAT tanımlanan aşağıdaki bildirim sabitleri içerir. Y:  
  
 `_S_IWRITE`  
 Yazma izin verilir.  
  
 `_S_IREAD`  
 Okuma izin verilir.  
  
 `_S_IREAD | _S_IWRITE`  
 Okuma ve yazma izin verilir.  
  
 Her iki sabitleri verildiğinde olan bit düzeyinde OR işleci katılan ( `|` ). Varsa `pmode` bağımsız değişkeni `_S_IREAD`, okuma izin verilmiyor (dosya salt yazılır). Varsa `pmode` bağımsız değişkeni `_S_IWRITE`, yazma izin verilmiyor (dosya salt okunur durumdadır). Örneğin, yazma bit maskesi ayarlarsanız, yeni dosyalar salt okunur olacaktır. MS-DOS ve Windows işletim sistemleri ile tüm dosyaları okunabilir olduğunu unutmayın; salt yazılır izin vermek mümkün değildir. Bu nedenle, ile bit okunur ayarını `_umask` dosyanın modları üzerinde hiçbir etkisi olmaz.  
  
 Varsa `pmode` bildirim sabitleri bir birleşimini değil veya başka bir kümesi içerir, sabitleri işlevi yalnızca bu göz ardı eder.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_umask`|\<io.h >, \<sys/stat.h >, \<sys/types.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
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
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)