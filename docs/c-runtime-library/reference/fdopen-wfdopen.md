---
title: _fdopen, _wfdopen
ms.date: 12/12/2017
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 0cde110bf1dd12c23a6b0b658809502743d9edd3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334781"
---
# <a name="fdopen-wfdopen"></a>_fdopen, _wfdopen

Bir akış, düşük düzey g/ç için daha önce açıldı bir dosya ile ilişkilendirir.

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

*Modu*<br/>
Dosya erişimi türü.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri açık akışa bir işaretçi döndürür. Bir null işaretçi değeri bir hata olduğunu gösterir. Bir hata oluştuğunda, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ya da ayarlanmış **EBADF**, bir geçersiz dosya açıklayıcısı gösteren veya **EINVAL**, belirten *modu*  bir null işaretçi oluştu.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Fdopen** işlevi tarafından tanımlanan dosya g/ç akışına ilişkilendirir *fd*ve bu nedenle arabelleğe alınır ve biçimlendirilmiş düşük düzey g/ç için açtığınız bir dosya sağlar. **_wfdopen** geniş karakterli sürümüdür **_fdopen**; *modu* bağımsız değişkeni **_wfdopen** geniş karakterli bir dizedir. **_wfdopen** ve **_fdopen** Aksi halde aynı şekilde davranır.

Dosya tanımlayıcıları yöntemlere geçirilen **_fdopen** ait olan tarafından döndürülen **dosya &#42;**  akış. Varsa **_fdopen** başarılı olursa, çağırmayın [ \_kapatmak](close.md) üzerinde dosya tanımlayıcısı. Çağırma [fclose](fclose-fcloseall.md) döndürülen üzerinde **dosya &#42;**  ayrıca dosya tanımlayıcısı kapatır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|\_UNICODE ve \_MBCS tanımlı değil|\_MBCS tanımlanan|\_Tanımlanan UNICODE|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

*Modu* karakter dizesi, dosya için istenen dosya erişim türünü belirtir:

| *Modu* | Access |
|--------|--------|
| **"r"** | Okuma için açar. Dosya mevcut değil ya da bulunamıyorsa **fopen** çağrısı başarısız olur. |
| **"w"** | Yazma için boş bir dosya açar. Verilen dosya varsa içeriği yok edilir. |
| **"a"** | (Ekleme) dosyanın sonunda yazma için açar. Henüz yoksa dosyayı oluşturur. |
| **"r +"** | Hem okuma ve yazma için açar. Dosyanın mevcut olması gerekir. |
| **"w +"** | Hem okuma ve yazma için boş bir dosya açar. Dosya varsa içeriği yok edilir. |
| **"a+"** | Okuma ve ekleme için açar. Henüz yoksa dosyayı oluşturur. |

Ne zaman bir dosya açıldığında ile **"a"** veya **"a +"** erişim türü, tüm yazma işlemleri dosyanın sonunda gerçekleşir. Dosya işaretçisini kullanarak konumlandırılabilir [fseek](fseek-fseeki64.md) veya [rewind](rewind.md), ancak herhangi bir işlemi yazma önce her zaman geri dosyanın sonuna kadar taşınır. Bu nedenle, var olan verilerin üzerine yazılamaz. Zaman **"r +"**, **"w +"**, veya **"a +"** erişim türü belirtildiğinde, hem okumaya hem yazmaya izin verilir (dosyanın "güncelleştirme" açık olarak kabul edilir). Ancak, yazma ve okuma arasında geçiş yaptığınızda, olmalıdır bir araya giren [fflush](fflush.md), [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), veya [rewind](rewind.md) işlem. Geçerli konumu için belirttiğiniz [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) isterseniz işlemi.

Yukarıdaki değerlerden ek olarak, şu karakterleri de eklenebilir *modu* yeni satır karakterlerinin çeviri modu belirtmek için:

| *modu* değiştiricisi | Davranış |
|-----------------|----------|
| **T** | Açık metin (çevrilmiş) modunda. Bu modda, satır başı satır besleme (CR-LF) kombinasyonları girişte satır akışlarını (LF) çevrilir ve LF karakterleri için çıkış CR-LF kombinasyonlarına çevrilir. Ayrıca, Ctrl + Z girişteki bir dosya sonu karakteri olarak yorumlanır. |
| **b** | İkili (çevrilmemiş) modda açın. Tüm çevirilerden **t** modu gizlenir. |
| **c** | İlişkili için bayrak kaydetmeyi etkinleştir *filename* dosya tamponunun içeriği doğrudan diske yazılır, böylece **fflush** veya **_flushall** çağrılır. |
| **n** | İlişkili tamamlama bayrağı sıfırlar *filename* için "no-commit." Bu varsayılandır. Ayrıca programınızı Commode.obj ile bağlarsanız genel tamamlama bayrağını geçersiz kılar. Programınızı Commode.obj ile açıkça bağlantı sürece, küresel kaydetme bayrağı varsayılan "no-commit". |

**t**, **c**, ve **n** *modu* seçenekleri için Microsoft genişletmeleridir **fopen** ve **_fdopen**. ANSI taşınabilirliğinin korumak istiyorsanız, bunları kullanmayın.

Varsa **t** veya **b** verilmez *modu*, varsayılan çeviri modu genel değişkeni tarafından tanımlanan [ \_fmode](../../c-runtime-library/fmode.md). Varsa **t** veya **b** öneki bağımsız değişken işlev başarısız olur ve NULL döndürür. Metin ve ikili modlarının bir tartışma için bkz [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Geçerli karakterler için *modu* kullanılan dize **fopen** ve **_fdopen** karşılık *oflag* kullanılan bağımsız değişkenleri [ \_açın](open-wopen.md) ve [ \_sopen](sopen-wsopen.md), bu tabloda gösterildiği gibi:

|Öğesindeki karakterler *modu* dize|Eşdeğer *oflag* değerini **_aç** ve **_sopen**|
|---------------------------------|---------------------------------------------------|
|**a**|**\_O\_WRONLY &#124; \_O\_ekleme** (genellikle  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O \_Ekleme**)|
|**a+**|**\_O\_RDWR &#124; \_O\_ekleme** (genellikle  **\_O\_RDWR &#124; \_O\_ekleme &#124; \_O\_ CREAT** )|
|**r**|**\_O\_RDONLY**|
|**r +**|**\_O\_RDWR**|
|**w**|**\_O\_WRONLY** (genellikle  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**w +**|**\_O\_RDWR** (usually **\_O\_RDWR &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**b**|**\_O\_İKİLİ**|
|**T**|**\_O\_METİN**|
|**c**|Yok.|
|**n**|None|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fdopen**|\<stdio.h >|
|**_wfdopen**|\<stdio.h > veya \<wchar.h >|

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[\_Dup, \_dup2](dup-dup2.md)<br/>
[fclose, \_fcloseall](fclose-fcloseall.md)<br/>
[fopen, \_wfopen](fopen-wfopen.md)<br/>
[freopen, \_wfreopen](freopen-wfreopen.md)<br/>
[\_açık, \_wopen](open-wopen.md)<br/>
