---
title: fputs, fputws | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fputs
- fputws
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
- fputs
- fputws
- _fputts
dev_langs:
- C++
helpviewer_keywords:
- streams, writing strings to
- fputws function
- _fputts function
- fputs function
- fputts function
ms.assetid: d48c82b8-aa17-4830-8c7d-30442ddbb326
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 31c559e49712fa74d5cd457b528266c4eaeaa17a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fputs-fputws"></a>fputs, fputws
Bir dizeyi bir akışa yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fputs(   
   const char *str,  
   FILE *stream   
);  
int fputws(   
   const wchar_t *str,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `str`  
 Çıkış dizesi.  
  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa bu işlevlerin her biri negatif olmayan bir değer döndürür. Bir hata `fputs` ve `fputws` iade `EOF`. Varsa `str` veya `stream` null işaretçi açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve ardından `fputs` döndürür `EOF`, ve `fputws` döndürür `WEOF`.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 Bunların her biri kopyaları işlevleri `str` çıktısına `stream` geçerli konumundaki. `fputws` joker karakter bağımsız değişkeni kopyalar `str` için `stream` çok baytlı karakter dizesi veya mi göre bir joker karakter dizesi olarak `stream` metin modunda veya ikili modunda sırasıyla açılır. Hiçbiri işlevi sonlandırma null karakter kopyalar.  
  
 Akış ANSI modunda açılırsa iki işlevleri aynı şekilde davranır. `fputs` şu anda çıktı bir UNICODE akışa desteklemiyor.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fputts`|`fputs`|`fputs`|`fputws`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fputs`|\<stdio.h >|  
|`fputws`|\<stdio.h > veya \<wchar.h >|  
  
 Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_fputs.c  
// This program uses fputs to write  
// a single line to the stdout stream.  
  
#include <stdio.h>  
  
int main( void )  
{  
   fputs( "Hello world from fputs.\n", stdout );  
}  
```  
  
```Output  
Hello world from fputs.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [_getws alır](../../c-runtime-library/gets-getws.md)   
 [puts, _putws](../../c-runtime-library/reference/puts-putws.md)