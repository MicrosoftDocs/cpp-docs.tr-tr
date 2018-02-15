---
title: fgetpos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fgetpos
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
- fgetpos
dev_langs:
- C++
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3740fdc7924e12fc9eeb2de4ab108ad376c764da
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fgetpos"></a>fgetpos
Bir akışın dosya konumu göstergesi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fgetpos(   
   FILE *stream,  
   fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 Hedef akış.  
  
 `pos`  
 Konum göstergesi depolama.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, `fgetpos` 0 döndürür. İsteğe bağlı olarak, arıza sıfır olmayan bir değer döndürür ve ayarlar `errno` aşağıdakilerden birini bildirim Sabitleri (STDIO içinde tanımlanmıştır. H): `EBADF`, belirtilen stream başka bir deyişle, geçerli dosya işaretçisi değil veya erişilebilir değil veya `EINVAL`, anlamına `stream` değeri veya değeri `pos` olduğu ya da null işaretçi gelmesi gibi geçersiz. Varsa `stream` veya `pos` olan bir `NULL` işaretçisi işlevi çağırır geçersiz parametre işleyicisi açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `fgetpos` İşlevi alır geçerli değeri `stream` bağımsız değişkeninin dosya konumu göstergesi ve nesne içinde işaret için tarafından depoları `pos`. `fsetpos` İşlevi daha sonra depolanan bilgileri kullanmak `pos` sıfırlamak için `stream` bağımsız değişkeninin işaretçi zaman konumuna `fgetpos` çağrıldı. `pos` Değeri iç bir biçimde depolanır ve yalnızca tarafından kullanılmaya yöneliktir `fgetpos` ve `fsetpos`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fgetpos`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_fgetpos.c  
// This program uses fgetpos and fsetpos to  
// return to a location in a file.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE   *stream;  
   fpos_t pos;  
   char   buffer[20];  
  
   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {  
      perror( "Trouble opening file" );  
      return -1;  
   }  
  
   // Read some data and then save the position.   
   fread( buffer, sizeof( char ), 8, stream );  
   if( fgetpos( stream, &pos ) != 0 ) {  
      perror( "fgetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fgetpos: %.13s\n", buffer );  
  
   // Restore to old position and read data   
   if( fsetpos( stream, &pos ) != 0 ) {  
      perror( "fsetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fsetpos: %.13s\n", buffer );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfgetpostxt"></a>Input: crt_fgetpos.txt  
  
```  
fgetpos gets a stream's file-position indicator.  
```  
  
### <a name="output-crtfgetpostxt"></a>Output crt_fgetpos.txt  
  
```  
after fgetpos: gets a stream  
after fsetpos: gets a stream  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fsetpos](../../c-runtime-library/reference/fsetpos.md)