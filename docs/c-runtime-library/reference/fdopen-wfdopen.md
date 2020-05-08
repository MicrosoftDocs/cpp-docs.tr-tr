---
title: _fdopen, _wfdopen
ms.date: 4/2/2020
api_name:
- _fdopen
- _wfdopen
- _o__fdopen
- _o__wfdopen
api_location:
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
ms.openlocfilehash: 227f9e31c689b0259c429e2ffd9fce074903bd71
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920173"
---
# <a name="_fdopen-_wfdopen"></a>_fdopen, _wfdopen

Daha önce alt düzey g/ç için açılan bir dosyayla bir akışı ilişkilendirir.

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

*FD*<br/>
Açık dosyanın dosya tanımlayıcısı.

*modundaysa*<br/>
Dosya erişiminin türü.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri açık akışa bir işaretçi döndürür. Null işaretçi değeri bir hatayı gösterir. Bir hata oluştuğunda, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** , hatalı bir dosya tanımlayıcısı belirten **EBADF**, ya da *modun* null bir işaretçi olduğunu gösteren **EINVAL**olarak ayarlanmıştır.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Fdopen** işlevi, bir g/ç akışını *FD*tarafından tanımlanan dosyayla ilişkilendirir ve bu nedenle alt düzey g/ç için açılan bir dosyanın arabelleğe alınıp biçimlendirilmesi için izin verir. **_wfdopen** , **_fdopen**geniş karakterli bir sürümüdür; _wfdopen *mod* bağımsız değişkeni **_wfdopen** geniş karakterli bir dizedir. **_wfdopen** ve **_fdopen** aynı şekilde davranır.

**_Fdopen** geçirilen dosya tanımlayıcıları, döndürülen **Dosya &#42;** akışına aittir. **_Fdopen** başarılı olursa dosya tanımlayıcısında [ \_Close](close.md) 'u çağırmayın. Döndürülen dosyada [fclose](fclose-fcloseall.md) çağırma **&#42;** dosya tanımlayıcısını da kapatır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|\_UNICODE ve \_MBCS tanımlı değil|\_Tanımlanan MBCS|\_Tanımlanan UNICODE|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

*Mod* karakter dizesi, dosya için istenen dosya erişiminin türünü belirtir:

| *modundaysa* | Erişim |
|--------|--------|
| **sağ** | Okuma için açılır. Dosya yoksa veya bulunamazsa, **fopen** çağrısı başarısız olur. |
| **anlatımı** | Yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir. |
| **a** | Dosyanın sonuna yazmak için açılır (ekleme). Yoksa dosyayı oluşturur. |
| **"r +"** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **"w +"** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **"a +"** | Okuma ve ekleme için açılır. Yoksa dosyayı oluşturur. |

**"A"** veya **"a +"** erişim türüyle bir dosya açıldığında, dosyanın sonunda tüm yazma işlemleri gerçekleşir. Dosya işaretçisi, [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilir, ancak herhangi bir yazma işlemi yapılmadan önce her zaman dosyanın sonuna geri taşınır. Bu nedenle, mevcut verilerin üzerine yazılamaz. **"R +"**, **"w +"** ya da **"a +"** erişim türü belirtildiğinde, hem okuma hem de yazma için izin verilir (dosya "güncelleştirme" için açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, aradaki bir [fflush](fflush.md), [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md)veya [geri sarma](rewind.md) işlemi olmalıdır. İsterseniz [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) işlemi için geçerli konumu belirtebilirsiniz.

Yukarıdaki değerlere ek olarak, aşağıdaki karakterler de yeni satır karakterleri için çeviri modunu belirtmek üzere *moduna* dahil edilebilir:

| *mod* değiştiricisi | Davranış |
|-----------------|----------|
| **şı** | Metin (çevrilmiş) modunda aç. Bu modda, satır başı satır besleme (CR-LF) birleşimleri girişte tek satırlık akışlara (LF) çevrilir ve LF karakterleri çıkışta CR-LF birleşimlerine çevrilir. Ayrıca CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. |
| **kenarı** | İkili (çevrilmemiş) modda açın. **T** modundaki tüm çeviriler bastırılır. |
| **,** | Bir **fflush** veya **_flushall** çağrılırsa, dosya arabelleği içeriğinin doğrudan diske yazılması için ilişkili *dosya adı* için COMMIT bayrağını etkinleştirin. |
| **No** | İlişkili *dosya adı* için COMMIT bayrağını "No-COMMIT" olarak sıfırlayın. Bu varsayılandır. Ayrıca, programınızı Commode. obj ile bağlarsanız Genel tamamlama bayrağını da geçersiz kılar. Programınızı Commode. obj ile açıkça bağmadığınız takdirde Genel tamamlama bayrağı varsayılan olarak "No-COMMIT" olur. |

**T**, **c**ve **n** *modu* seçenekleri, **fopen** ve **_fdopen**için Microsoft uzantılarıdır. ANSI taşınabilirliği korumak istiyorsanız bunları kullanmayın.

**T** veya **b** *modunda*verilmezse, varsayılan çeviri modu [ \_fMode](../../c-runtime-library/fmode.md)genel değişkeni tarafından tanımlanır. **T** veya **b** bağımsız değişkene öneki varsa, Işlev başarısız olur ve null değerini döndürür. Metin ve ikili modların bir tartışması için bkz. [metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

**Fopen** ve **_fdopen** için kullanılan *mod* dizesi için geçerli karakterler, bu tabloda gösterildiği gibi [ \_Open](open-wopen.md) ve [ \_Sopen](sopen-wsopen.md)içinde kullanılan *oflag* bağımsız değişkenlerine karşılık gelir:

|*Mod* dizesindeki karakterler|**_Open** ve **_sopen** için eşdeğer *oflag* değeri|
|---------------------------------|---------------------------------------------------|
|**a**|**\_O\_yalnızca o &#124; \_o\_ekleme** (genellikle ** \_o\_ \_&#124; o\_&#124; \_\_** o)|
|**a +**|**\_O\_rdwr &#124; \_o\_Append** (genellikle ** \_o\_rdwr &#124; \_o\_Append &#124; \_o\_creat** )|
|**sağ**|**\_O\_yalnızca RD**|
|**r +**|**\_O\_rdwr**|
|**anlatımı**|**\_Yalnızca\_wronly** (genellikle ** \_o\_&#124; \_o\_creat &#124; \_o\_TRUNC**)|
|**w +**|**\_O\_rdwr** (genellikle ** \_o\_, rdwr \_&#124;\_o creat \_&#124;\_o TRUNC**)|
|**kenarı**|**\_O\_ikili**|
|**şı**|**\_O\_metni**|
|**,**|Yok|
|**No**|Yok|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fdopen**|\<stdio. h>|
|**_wfdopen**|\<stdio. h> veya \<wchar. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

### <a name="input-crt_fdopentxt"></a>Giriş: crt_fdopen. txt

```Input
Line one
Line two
```

### <a name="output"></a>Çıktı

```Output
Lines in file: 2
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[\_DUP, \_dUP2](dup-dup2.md)<br/>
[fclose, \_fcloseall](fclose-fcloseall.md)<br/>
[fopen, \_wfopen](fopen-wfopen.md)<br/>
[serbest açık, \_wfreopen](freopen-wfreopen.md)<br/>
[\_açık, \_wopen](open-wopen.md)<br/>
