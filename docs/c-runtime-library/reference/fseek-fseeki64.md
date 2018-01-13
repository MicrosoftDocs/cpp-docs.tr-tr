---
title: fseek, _fseeki64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fseeki64
- fseek
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
apitype: DLLExport
f1_keywords:
- fseek
- _fseeki64
dev_langs: C++
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 90af1581910ceaadf814050be39bc537cfc3881c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64
Dosya işaretçisini belirtilen bir konuma taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
 `offset`  
 Bayt sayısı `origin`.  
  
 `origin`  
 Başlangıç konumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, `fseek` ve `_fseeki64` 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür. Cihazlarda aramayı kuramadığı dönüş değeri tanımlanmamıştır. Varsa `stream` null işaretçinin veya `origin` aşağıda açıklanan izin verilen değerlerden biri değil `fseek` ve `_fseeki64` açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve -1 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `fseek` Ve `_fseeki64` taşır (varsa) dosya işaretçisini ilişkili işlevleri `stream` yeni bir konuma `offset` baytlar `origin`. Sonraki işlem akışını yeni konumda gerçekleşir. Güncelleştirme için açık bir akış üzerinde okuma veya yazma sonraki işlemi olabilir. Bağımsız değişken kaynak STDIO içinde tanımlanan sabitlerden biri olması gerekir. Y:  
  
 `SEEK_CUR`  
 Dosya işaretçisini geçerli konumu.  
  
 `SEEK_END`  
 Dosya sonu.  
  
 `SEEK_SET`  
 Dosya başlangıcı.  
  
 Kullanabileceğiniz `fseek` ve `_fseeki64` işaretçi bir dosyada herhangi bir yere yeniden konumlandırmak için. İşaretçinin dosyanın sonunu aşan konumlandırılmış olabilir. `fseek`ve `_fseeki64` dosya sonu göstergesi temizler ve tüm önceki etkisini geçersiz hale getirir `ungetc` karşı çağırır `stream`.  
  
 Veri ekleme için bir dosya açıldığında, geçerli dosya konumu değil burada sonraki yazma oluşacak tarafından son g/ç işlemi tarafından belirlenir. G/ç işlemi henüz ekleme için açılan bir dosyada oluştuysa, dosya konumu dosya sayısıdır.  
  
 Metin modunda açılmış akışlar için `fseek` ve `_fseeki64` kullanımı, satır başı satır besleme çevirileri neden olabileceği için sınırlı `fseek` ve `_fseeki64` beklenmeyen sonuçlar üretmek için. Yalnızca `fseek` ve `_fseeki64` metin modunda açılmış akışları üzerinde çalışmak için garanti işlemleri:  
  
-   Uzaklığı 0 kaynak değerlerden herhangi birine göre ile aramayı.  
  
-   Bir uzaklık değeri dosyasıyla başından itibaren aramayı döndürülen çağrısından `ftell` kullanırken `fseek` veya `_ftelli64` kullanırken `_fseeki64`.  
  
 Ayrıca metin modunda, CTRL + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılmış dosyalarında `fopen` ve tüm ilgili yordamlar için CTRL + Z dosyanın sonunda denetleyin ve mümkünse kaldırın. Bu birleşimini kullanarak yapılır, çünkü `fseek` ve `ftell` veya `_fseeki64` ve `_ftelli64`, CTRL + Z ile biter neden olabilecek bir dosyanın içinde taşımak için `fseek` veya `_fseeki64` dosyanın sonuna yakın yanlış bir şekilde davranır.  
  
 CRT bir bayt sırası işareti (BOM) ile başlayan bir dosyayı açtığında dosya işaretçisini sonra AĞACI konumlandırılır (diğer bir deyişle, dosyanın gerçek içeriği başlangıcında). Gerekirse `fseek` dosyasının başlangıcına kullanmak `ftell` ilk konumunu almak için ve `fseek` ona yerine 0 konumuna.  
  
 Bu işlev yürütülürken başka bir iş parçacığı kilitler ve bu nedenle iş parçacığı. Kilitleme olmayan bir sürümü için bkz: [_fseek_nolock, _fseeki64_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fseek`|\<stdio.h >|  
|`_fseeki64`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
```Output  
File pointer is set to middle of first line.  
This is the file 'fseek.out'.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, _ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)