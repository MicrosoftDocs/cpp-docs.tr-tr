---
title: fflush | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: fflush
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
f1_keywords: fflush
dev_langs: C++
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2692e06416da3b62e5f9e87b4c0827d3003253e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fflush"></a>fflush
Bir akışa aktarır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fflush(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `fflush`Arabellek başarıyla temizlendi 0 döndürür. 0 değeri, belirtilen stream hiçbir arabellek olan veya yalnızca okumak için açık durumda da döndürülür. Dönüş değeri `EOF` bir hata olduğunu gösterir.  
  
> [!NOTE]
>  Varsa `fflush` döndürür `EOF`, veriler kaybolmuş olabilir bir yazma hatası nedeniyle. Bir kritik hata işleyicisini ayarlarken, arabelleğe alma ile devre dışı bırakmak güvenli `setvbuf` işlevi veya düşük düzey g/ç yordamları gibi kullanmak için `_open`, `_close`, ve `_write` akış g/ç işlevleri yerine.  
  
## <a name="remarks"></a>Açıklamalar  
 `fflush` İşlevi temizler akış `stream`. Akış açtıysanız yazma modu veya güncelleştirme modunda açılmış ve son işlemi bir yazma olduğu, Akış Arabellek içeriğini temel alınan dosya veya aygıt için yazılmıştır ve arabellek atılır. Akış Okuma modunda açılan veya akış hiçbir arabellek çağrısı varsa `fflush` hiçbir etkisi yoktur ve tüm arabellek korunur. Çağrı `fflush` üzerindeki herhangi bir önceki çağrısına etkisini geçersiz kılar `ungetc` akış için. Akış çağrısından sonra açık kalır.  
  
 Varsa `stream` olan `NULL`, davranışı çağrısı ile aynıdır `fflush` açık her akış hakkındaki. Tüm akışlar yazma modunda açılmış ve son işlemi yazma bulunduğu tüm akışlar güncelleştirme modunda açılmış temizlenir. Çağrı diğer akışlar üzerinde etkisi yoktur.  
  
 Arabellekler verileri otomatik olarak diske yazmak için en iyi zamanı belirler işletim sistemi tarafından normalde korunur: bir arabellek dolduğunda, bir akış kapalıyken veya ne zaman bir program akış kapatmadan sona erer. Çalışma Zamanı Kitaplığı commit-to-disk özellik kritik verileri doğrudan diske yerine işletim sistemi arabellekleri için yazılmış emin olun olanak sağlar. Varolan bir programı'nı yeniden yazma işlemi olmadan, programın nesne dosyaları COMMODE.OBJ ile bağlayarak bu özelliği etkinleştirebilirsiniz. Sonuçta elde edilen yürütülebilir dosyada çağrılar `_flushall` tüm arabelleklerinin içeriğini diske yazma. Yalnızca `_flushall` ve `fflush` COMMODE.OBJ tarafından etkilenir.  
  
 Commit-to-disk özelliği denetleme hakkında daha fazla bilgi için bkz: [akış g/ç](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md), ve [_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
 Bu işlev çağıran iş parçacığı kilitler ve bu nedenle iş parçacığı. Kilitleme olmayan bir sürümü için bkz: `_fflush_nolock`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fflush`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_fflush.c  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int integer;  
   char string[81];  
  
   // Read each word as a string.  
   printf( "Enter a sentence of four words with scanf: " );  
   for( integer = 0; integer < 4; integer++ )  
   {  
      scanf_s( "%s", string, sizeof(string) );        
      printf( "%s\n", string );  
   }  
  
   // You must flush the input buffer before using gets.   
   // fflush on input stream is an extension to the C standard   
   fflush( stdin );     
   printf( "Enter the same sentence with gets: " );  
   gets_s( string, sizeof(string) );  
   printf( "%s\n", string );  
}  
```  
  
```Output  
  
      This is a test  
This is a test  
  
```  
  
```Output  
  
      This is a test  
This is a testEnter a sentence of four words with scanf: This is a test  
This  
is  
a  
test  
Enter the same sentence with gets: This is a test  
This is a test  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)