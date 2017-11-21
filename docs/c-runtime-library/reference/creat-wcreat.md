---
title: _creat, _wcreat | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _creat
- _wcreat
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
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
dev_langs: C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5e8f61cda7d26f75677093e2377adb29a913dd35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creat-wcreat"></a>_creat, _wcreat
Yeni bir dosya oluşturur. `_creat`ve `_wcreat` kullanım dışı bırakıldı; kullanın [_sopen_s, _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md) yerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _creat(   
   const char *filename,  
   int pmode   
);  
int _wcreat(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Yeni dosya adı.  
  
 `pmode`  
 İzni ayarı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevler başarılı olursa, oluşturulan dosya için dosya tanımlayıcısı döndürür. Aksi takdirde işlevleri -1 döndürür ve `errno` aşağıdaki tabloda gösterildiği gibi.  
  
|`errno`ayarı|Açıklama|  
|---------------------|-----------------|  
|`EACCES`|`filename`Varolan salt okunur dosyanın veya bir dosya yerine bir dizin belirtir.|  
|`EMFILE`|Daha fazla hiçbir dosya tanımlayıcıları kullanılabilir.|  
|`ENOENT`|Belirtilen dosya bulunamadı.|  
  
 Varsa `filename` null, bu işlevler açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve -1 döndürür.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_creat` İşlevi yeni bir dosya oluşturur veya açar ve mevcut bir tamsayıya dönüştürür. `_wcreat`bir joker karakter sürümü `_creat`; `filename` bağımsız değişkeni `_wcreat` bir joker karakter dizesidir. `_wcreat`ve `_creat` Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 Dosyanın belirtilen `filename` mevcut olmadığından yeni bir dosya ile verilen izni ayarı oluşturulur ve yazma için açılmış. Dosya zaten varsa ve yazma izni ayarı sağlar `_creat` önceki içeriği yok etme uzunluğu 0, dosyaya tamsayıya dönüştürür ve yazma için açar. İzni ayarı `pmode`, yalnızca yeni oluşturulan dosyalar için geçerlidir. İlk kez kapatıldıktan sonra yeni dosya belirtilen izin ayarını alır. Tamsayı ifade `pmode` birini veya her ikisini bildirim sabitleri içerir `_S_IWRITE` ve `_S_IREAD`, SYS\Stat.h içinde tanımlı. Her iki sabitleri verildiğinde, bunlar Bitsel ile katılan `OR` işleci ( **&#124;** ). `pmode` Parametresi şu değerlerden biri olarak ayarlanır.  
  
|Değer|Tanım|  
|-----------|----------------|  
|`_S_IWRITE`|Yazma izin verilir.|  
|`_S_IREAD`|Okuma izin verilir.|  
|`_S_IREAD &#124; _S_IWRITE`|Okuma ve yazma izin verilir.|  
  
 Yazma izni verilmedi, dosya salt okunurdur. Tüm dosyaları her zaman okunabilir; salt yazılır izin vermek mümkün değildir. Modları `_S_IWRITE` ve `_S_IREAD | _S_IWRITE` sonra eşdeğerdir. Kullanarak açılan dosyaları `_creat` her zaman uyumluluk modunda açılmış (bkz [_sopen](../../c-runtime-library/reference/sopen-wsopen.md)) ile `_SH_DENYNO`.  
  
 `_creat`Geçerli dosya izni maskesi uygular `pmode` izinleri ayarlamadan önce (bkz [_umask](../../c-runtime-library/reference/umask.md)). `_creat`öncelikle önceki kitaplıkları ile uyumluluk için sağlanır. Çağrı `_open` ile `_O_CREAT` ve `_O_TRUNC` içinde `oflag` parametredir eşdeğer `_creat` ve için yeni kod tercih edilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_creat`|\<io.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|  
|`_wcreat`|\<io.h > veya \<wchar.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_creat.c  
// compile with: /W3  
// This program uses _creat to create  
// the file (or truncate the existing file)  
// named data and open it for writing.  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int fh;  
  
   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996  
   // Note: _creat is deprecated; use _sopen_s instead  
   if( fh == -1 )  
      perror( "Couldn't create data file" );  
   else  
   {  
      printf( "Created data file.\n" );  
      _close( fh );  
   }  
}  
```  
  
```Output  
Created data file.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)