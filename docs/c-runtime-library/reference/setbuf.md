---
title: setbuf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: setbuf
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
f1_keywords: setbuf
dev_langs: C++
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a57e815376414724b2c92977c52a309f86c63b50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setbuf"></a>setbuf
Denetim akışı arabelleğe alma. Bu işlev kullanım dışıdır; kullanmak [setvbuf](../../c-runtime-library/reference/setvbuf.md) yerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void setbuf(  
   FILE *stream,  
   char *buffer   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
 `buffer`  
 Kullanıcı tarafından ayrılan arabellek.  
  
## <a name="remarks"></a>Açıklamalar  
 `setbuf` İşlev için arabelleğe alma denetimleri `stream`. `stream` Bağımsız değişkeni bir açık dosyasına okuma yazılmış veya kaldırılmış başvurması gerekir. Varsa `buffer` bağımsız değişkeni `NULL`, beklemediğiniz arabelleğe alınan bir akışıdır. Arabellek uzunluğu için bir karakter dizisi işaret etmelidir değil, varsa `BUFSIZ`, burada `BUFSIZ` STDIO içinde tanımlanan arabellek boyutu olan. H. Kullanıcı tarafından belirtilen arabellek, belirtilen akışa için varsayılan sistem tarafından ayrılmış arabellek yerine g/ç için kullanılan arabelleğe alma. `stderr` Akış varsayılan olarak kaldırmayı arabelleğe alınan ancak kullanabilirsiniz `setbuf` arabelleklere atamak için `stderr`.  
  
 `setbuf`ile değiştirilmiştir [setvbuf](../../c-runtime-library/reference/setvbuf.md), yeni kodu için tercih edilen yordamı olduğu. `setbuf`var olan kodu ile uyumluluk için tutulmaktadır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`setbuf`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_setbuf.c  
// compile with: /W3  
// This program first opens files named DATA1 and  
// DATA2. Then it uses setbuf to give DATA1 a user-assigned  
// buffer and to change DATA2 so that it has no buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[BUFSIZ];  
   FILE *stream1, *stream2;  
  
   fopen_s( &stream1, "data1", "a" );  
   fopen_s( &stream2, "data2", "w" );  
  
   if( (stream1 != NULL) && (stream2 != NULL) )  
   {  
      // "stream1" uses user-assigned buffer:  
      setbuf( stream1, buf ); // C4996  
      // Note: setbuf is deprecated; consider using setvbuf instead  
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );  
  
      // "stream2" is unbuffered  
      setbuf( stream2, NULL ); // C4996  
      printf( "stream2 buffering disabled\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
stream1 set to user-defined buffer at: 0012FCDC  
stream2 buffering disabled  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)