---
title: ftell, _ftelli64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
dev_langs: C++
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4b37db89ca7d9e3facb7de2fbce2dc819cfa03e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64
Dosya işaretçisini geçerli konumunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 Hedef `FILE` yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `ftell`ve `_ftelli64` geçerli dosya konumu döndürür. Tarafından döndürülen değer `ftell` ve `_ftelli64` satır başı satır besleme çeviri metin modu neden olduğundan metin modunda açılmış akışlar için fiziksel bayt uzaklığı yansıtmayabilir. Kullanım `ftell` ile `fseek` veya `_ftelli64` ile `_fseeki64` dosya konumları doğru dönün. Hata, `ftell` ve `_ftelli64` açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlevler dönüş-1 M ve kümesi yürütülmesine izin veriliyorsa `errno` ERRNO içinde tanımlanan iki sabitleri birine. H. `EBADF` Sabiti anlamına gelir `stream` bağımsız değişkeni geçerli bir dosya işaretçi değeri değil veya açık olan bir dosyaya başvurmuyor. `EINVAL`Geçersiz bir anlamına gelir `stream` işleve bağımsız değişken geçirildi. (Terminal ve yazıcılar gibi), aramayı kuramadığı cihazlarda veya ne zaman `stream` referansta açık bir dosyanın dönüş değeri tanımlanmadı.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.  
  
## <a name="remarks"></a>Açıklamalar  
 `ftell` Ve `_ftelli64` işlevleri ile ilişkili dosya işaretçisi (varsa) geçerli konumunu almak `stream`. Konumu uzaklığı akış başlangıcından göreli olarak ifade edilir.  
  
 Veri ekleme için bir dosya açıldığında, geçerli dosya konumu son g/ç işlemi tarafından değil, sonraki yazma oluşacak tarafından belirlendiğini unutmayın. Örneğin, bir dosya için bir ekleme açılmış ve son işlemi okuma başarısız olursa dosya konumu burada İleri okuma işlemi, sonraki yazma burada başlatılamayan başlarsınız noktasıdır. (Ekleme için bir dosya açıldığında, dosya konumunu dosyanın sonunu herhangi bir yazma işlemi önce taşınır.) G/ç işlemi henüz ekleme için açılan bir dosyada oluştuysa, dosya dosyasının başında konumdur.  
  
 Metin modunda CTRL + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılmış dosyalarında `fopen` ve tüm ilgili yordamlar için CTRL + Z dosyanın sonunda denetleyin ve mümkünse kaldırın. Bu birleşimini kullanarak yapılır, çünkü `ftell` ve `fseek` veya `_ftelli64` ve `_fseeki64`, CTRL + Z ile biter neden olabilecek bir dosyanın içinde taşımak için `ftell` veya `_ftelli64` dosyanın sonuna yakın yanlış bir şekilde davranır.  
  
 Bu işlev yürütülürken çağıran iş parçacığı kilitler ve bu nedenle iş parçacığı. Kilitleme olmayan bir sürümü için bkz: `_ftell_nolock`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|  
|--------------|---------------------|----------------------|  
|`ftell`|\<stdio.h >|\<errno.h >|  
|`_ftelli64`|\<stdio.h >|\<errno.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
```Output  
Position after trying to read 100 bytes: 100  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)