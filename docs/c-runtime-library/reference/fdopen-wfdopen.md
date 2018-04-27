---
title: _fdopen, _wfdopen | Microsoft Docs
ms.custom: ''
ms.date: 12/12/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _fdopen
- _wfdopen
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
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
dev_langs:
- C++
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03dd7c56c8b8249ddee09ed2ac5446f99484e671
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="fdopen-wfdopen"></a>_fdopen, _wfdopen

Düşük düzey g/ç için daha önce açıldı bir dosya akışı ilişkilendirir.

## <a name="syntax"></a>Sözdizimi

```C
FILE *_fdopen(
   int fd,
   const char *mode
);
FILE *_wfdopen(
   int fd,
   const wchar_t *mode
);
```

### <a name="parameters"></a>Parametreler

*FD* açık dosyanın dosya tanımlayıcısı.

*mod* dosya erişimi türü.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri bir işaretçi açık akışına döndürür. Null işaretçinin değeri bir hata gösterir. Hata oluştuğunda geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ya da ayarlamak **EBADF**, bozuk dosya tanımlayıcısı gösterir veya **EINVAL**, hangi gösterir *modu*  null işaretçi oluştu.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Fdopen** işlevi tarafından tanımlanan dosyası içeren bir g/ç akışı ilişkilendirir *fd*ve bu nedenle arabelleğe ve biçimlendirilmiş düşük düzey g/ç için açılan bir dosya sağlar. **_wfdopen** bir joker karakter sürümü **_fdopen**; *modu* bağımsız değişkeni **_wfdopen** bir joker karakter dizesidir. **_wfdopen** ve **_fdopen** Aksi takdirde aynı şekilde davranır.

Dosya tanımlayıcıları içine geçirilen **_fdopen** olunan tarafından döndürülen **dosya &#42;**  akış. Varsa **_fdopen** başarılı çağırmayın [ \_kapatmak](close.md) üzerinde dosya tanımlayıcısı. Çağırma [fclose](fclose-fcloseall.md) döndürülen üzerinde **dosya &#42;**  ayrıca dosya tanımlayıcısı kapatır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|\_UNICODE ve \_MBCS tanımlı değil|\_Tanımlanan MBCS|\_Tanımlanan UNICODE|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

*Modu* karakter dizesi dosya erişimi için dosyayı istenen türünü belirtir:

|*Modu*|Access|
|-|-|
**"r"**|Okuma için açılır. Dosya yok veya bulunamadı, **fopen** çağrısı başarısız olur.
**"w"**|Boş bir dosya yazma için açılır. Verilen dosya varsa, içeriği yok.
**"a"**|Yazma (ekleme) dosya sonunda açar. Henüz yoksa dosyası oluşturur.
**"r +"**|Hem okuma ve yazma için açılır. Dosyanın mevcut olması gerekir.
**"w +"**|Hem okumak ve yazmak için boş bir dosya açar. Dosya varsa, içeriği yok.
**"bir +"**|Okuma ve sonuna ekleme için açılır. Henüz yoksa dosyası oluşturur.

Ne zaman bir dosya açıldığında ile **"a"** veya **"bir +"** erişim türüne, tüm işlemleri ortaya dosyanın sonunda yazma. Dosya işaretçisini kullanarak konumlandırılmasına [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md), ancak herhangi bir işlemi gerçekleştirilir yazmadan önce her zaman geri dosyanın sonuna taşınır. Bu nedenle, varolan verilerin üzerine yazılamıyor. Zaman **"r +"**, **"w +"**, veya **"bir +"** erişim türü belirtildi, hem okuma ve yazma izin verilir (dosya "güncelleştirmesi" açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, olmalıdır bir araya giren [fflush](fflush.md), [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), veya [geri sarma](rewind.md) işlem. Geçerli konumu için belirttiğiniz [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) istiyorsanız işlemi.

Yukarıdaki değerleri ek olarak, aşağıdaki karakterleri da eklenebilir *modu* satırbaşı karakterlerini çeviri modu belirtmek için:

|*mod* değiştiricisi|Davranış|
|-|-|
**T**|Açık metin (modu çevrilmiş). Bu modda, satır başı satır besleme (CR-LF) birleşimleri tek satır akışlarına (LF) giriş uygulamasına dönüştürülür ve çıktıyı CR LF birleşimleri için LF karakterleri çevrilir. Ayrıca, Ctrl + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır.
**b**|İkili (untranslated) modunda açın. Gelen tüm çevirileri **t** modu gizlenir.
**c**|İle ilişkili yürütme bayrağı etkinleştirmek *filename* böylece dosya arabellek içeriğini doğrudan ya da diske yazılan **fflush** veya **_flushall** olarak adlandırılır.
**n**|İle ilişkili yürütme bayrağını sıfırlama *filename* "no-uygulanmak." Bu varsayılandır. Ayrıca Commode.obj programınızla bağlarsanız genel tamamlama bayrağı geçersiz kılar. Açıkça Commode.obj programınızla bağlantı sürece genel tamamlama bayrağı "no-commit" varsayılandır.

**t**, **c**, ve **n** *modu* seçenekleri için Microsoft uzantıları olan **fopen** ve **_fdopen**. ANSI taşınabilirlik korumak istiyorsanız, bunları kullanmayın.

Varsa **t** veya **b** verilmemiştir *modu*, varsayılan çeviri modu genel değişkeni tarafından tanımlanan [ \_fmode](../../c-runtime-library/fmode.md). Varsa **t** veya **b** bağımsız değişkenin işlevi başarısız öneki ve NULL döndürür. Metin ve ikili modlarda tartışma için bkz [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Geçerli karakterleri *modu* kullanılan dize **fopen** ve **_fdopen** karşılık *oflag* kullanılan bağımsız değişkenler [ \_açmak](open-wopen.md) ve [ \_sopen](sopen-wsopen.md)bu tabloda gösterildiği gibi:

|İçindeki karakterleri *modu* dize|Eşdeğer *oflag* değerini **_kurulum Aç** ve **_sopen**|
|---------------------------------|---------------------------------------------------|
|**a**|**\_O\_WRONLY &#124; \_O\_APPEND** (genellikle  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O \_APPEND**)|
|**bir +**|**\_O\_RDWR &#124; \_O\_APPEND** (genellikle  **\_O\_RDWR &#124; \_O\_APPEND &#124; \_O\_ CREAT** )|
|**r**|**\_O\_RDONLY**|
|**r +**|**\_O\_RDWR**|
|**W**|**\_O\_WRONLY** (genellikle  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**w +**|**\_O\_RDWR** (genellikle  **\_O\_RDWR &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**b**|**\_O\_İKİLİ**|
|**T**|**\_O\_METİN**|
|**c**|Yok.|
|**n**|Yok.|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fdopen**|\<stdio.h >|
|**_wfdopen**|\<stdio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```c
// crt_fdopen.c
// This program opens a file by using low-level
// I/O, then uses _fdopen to switch to stream
// access. It counts the lines in the file.

#include <stdlib.h>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>
#include <share.h>

int main( void )
{
   FILE *stream;
   int  fd, count = 0;
   char inbuf[128];

   // Open a file.
   if( _sopen_s( &fd, "crt_fdopen.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
      exit( 1 );

   // Get stream from file descriptor.
   if( (stream = _fdopen( fd, "r" )) == NULL )
      exit( 1 );

   while( fgets( inbuf, 128, stream ) != NULL )
      count++;

   // After _fdopen, close by using fclose, not _close.
   fclose( stream );
   printf( "Lines in file: %d\n", count );
}
```

### <a name="input-crtfdopentxt"></a>Giriş: crt_fdopen.txt

```Input
Line one
Line two
```

### <a name="output"></a>Çıkış

```Output
Lines in file: 2
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[\_Dup, \_dup2](dup-dup2.md)<br/>
[fclose, \_fcloseall](fclose-fcloseall.md)<br/>
[fopen, \_wfopen](fopen-wfopen.md)<br/>
[freopen, \_wfreopen](freopen-wfreopen.md)<br/>
[\_açık, \_wopen](open-wopen.md)<br/>
