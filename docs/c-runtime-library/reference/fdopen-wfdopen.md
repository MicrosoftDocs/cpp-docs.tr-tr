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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 82a7e891e8bd6031ebbf761534b6df7cd8488d36
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347384"
---
# <a name="_fdopen-_wfdopen"></a>_fdopen, _wfdopen

Akışı daha önce düşük düzeyli G/Ç için açılmış bir dosyayla ilişkilendirin.

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

*Fd*<br/>
Açık dosyanın dosya tanımlayıcısı.

*Modu*<br/>
Dosya erişimi türü.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri açık akışiçin bir işaretçi döndürür. Null işaretçi değeri bir hata gösterir. Bir hata oluştuğunda, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, **errno** ya **EBADF**olarak ayarlanır , hangi kötü bir dosya tanımlayıcısı gösterir, ya da **EINVAL**, hangi *modu* null işaretçi olduğunu gösterir.

Bu ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_fdopen** işlevi, bir G/Ç akışını *fD*tarafından tanımlanan dosyayla ilişkilendirer ve böylece düşük düzeyli G/Ç için açılan bir dosyanın arabelleğe alınmasına ve biçimlendirilmesine olanak tanır. **_wfdopen** **_fdopen**geniş karakterli bir versiyonudur; **_wfdopen** mod bağımsız *değişkeni* geniş karakterli bir dizedir. **_wfdopen** ve **_fdopen** aynı şekilde çalışır.

**_fdopen** geçirilen dosya tanımlayıcıları, döndürülen **DOSYA &#42;** akışına aittir. **_fdopen** başarılı olursa, dosya tanımlayıcısını [ \_kapat'ı](close.md) aramayın. Döndürülen **DOSYA'da** [fclose](fclose-fcloseall.md) arama &#42;da dosya tanımlayıcısını kapatır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|\_UNICODE \_ve MBCS tanımlanmamış|\_MBCS tanımlı|\_UNICODE tanımlı|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

*Mod* karakteri dizesi, dosya için istenen dosya erişim türünü belirtir:

| *Modu* | Erişim |
|--------|--------|
| **"r"** | Okumak için açılır. Dosya yoksa veya bulunamıyorsa, **fopen** çağrısı başarısız olur. |
| **"w"** | Yazmak için boş bir dosya yı açar. Verilen dosya varsa, içeriği yok edilir. |
| **"a"** | Dosyanın sonunda (ek olarak) yazmak için açılır. Yoksa dosyayı oluşturur. |
| **"r+"** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **"w+"** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **"a+"** | Okuma ve ekolarak açılır. Yoksa dosyayı oluşturur. |

Bir dosya **"a" veya "a+"** erişim türüyle açıldığında, tüm yazma işlemleri dosyanın sonunda gerçekleşir. **"a+"** Dosya işaretçisi [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilir, ancak herhangi bir yazma işlemi gerçekleştirilmeden önce her zaman dosyanın sonuna geri taşınır. Bu nedenle, varolan veriler üzerine yazılamaz. **"r+"**, **"w+"** veya **"a+"** erişim türü belirtildiğinde, hem okumaya hem de yazmaya izin verilir (dosyanın "güncelleştirme" için açık olduğu söylenir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, araya giren bir [fflush,](fflush.md) [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md)veya [geri sarma](rewind.md) işlemi olmalıdır. İsterseniz [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) işlemi için geçerli konumu belirtebilirsiniz.

Yukarıdaki değerlere ek olarak, aşağıdaki karakterler de yeni satır karakterleri için çeviri modunu belirtmek için *moda* dahil edilebilir:

| *mod* değiştirici | Davranış |
|-----------------|----------|
| **T** | Metin (çevrilmiş) modunda açın. Bu modda, satır başı besleme (CR-LF) kombinasyonları girişte tek satırlık akışlara (LF) ve çıktıda LF karakterleri CR-LF kombinasyonlarına çevrilir. Ayrıca, Ctrl+Z girişte dosya sonu karakteri olarak yorumlanır. |
| **B** | İkili (çevrilmemiş) modda açın. **t** modundan tüm çeviriler bastırılır. |
| **C** | Fflush veya **_flushall** çağrıldığında, dosya arabellesinin içeriğinin doğrudan diske **fflush** yazılması için ilişkili *dosya adı* için işleme bayrağını etkinleştirin. |
| **n** | İlişkili *dosya adı* için işleme bayrağını "işlemeyok" olarak sıfırla. Bu varsayılandır. Ayrıca, programınızı Commode.obj ile bağlarsanız, genel işleme bayrağını geçersiz kılar. Programınızı Açıkça Commode.obj'e bağlamadığınız sürece genel işleme bayrağı varsayılanı "işleyiş yok"dur. |

**t**, **c**ve **n** *modu* seçenekleri **fopen** ve **_fdopen**için Microsoft uzantılarıdır. ANSI taşınabilirliğini korumak istiyorsanız bunları kullanmayın.

**T** veya **b** *modunda*verilmiyorsa, varsayılan çeviri modu global değişken [ \_fmode](../../c-runtime-library/fmode.md)ile tanımlanır. **T** veya **b** bağımsız değişkene önceden belirlenmişse, işlev başarısız olur ve NULL döndürür. Metin ve ikili modların tartışılması için [Metin ve İkili Mod Dosyası I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)bölümüne bakın.

**Fopen** ve **_fdopen** kullanılan *mod* dizesinin geçerli karakterleri, bu tabloda gösterildiği gibi [ \_açık](open-wopen.md) ve [ \_sopen'da](sopen-wsopen.md)kullanılan *oflag* bağımsız değişkenlerine karşılık gelir:

|*Mod* dizesindeki karakterler|**_open** ve **_sopen** için eşdeğer *oflag* değeri|
|---------------------------------|---------------------------------------------------|
|**A**|**\_O\_WRONLY \_\_&#124; O APPEND** (genellikle ** \_\_O WRONLY \_&#124; O\_CREAT \_&#124; O\_APPEND)**|
|**a+**|**\_O\_RDWR \_\_&#124; O APPEND** (genellikle ** \_\_O RDWR \_&#124; O\_APPEND \_&#124; O\_CREAT)**|
|**R**|**\_O\_RDONLY**|
|**r+**|**\_O\_RDWR**|
|**W**|**\_O\_WRONLY** (genellikle ** \_\_O \_\_WRONLY \_&#124;\_O CREAT &#124; O TRUNC)**|
|**w+**|**\_O\_RDWR** (genellikle ** \_\_O \_\_RDWR \_&#124;\_O CREAT &#124; O TRUNC)**|
|**B**|**\_O\_İkİlİ**|
|**T**|**\_O\_TEKSTİl**|
|**C**|None|
|**n**|None|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fdopen**|\<stdio.h>|
|**_wfdopen**|\<stdio.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

### <a name="input-crt_fdopentxt"></a>Giriş: crt_fdopen.txt

```Input
Line one
Line two
```

### <a name="output"></a>Çıktı

```Output
Lines in file: 2
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[\_dup, \_dup2](dup-dup2.md)<br/>
[fclose, \_fcloseall](fclose-fcloseall.md)<br/>
[fopen, \_wfopen](fopen-wfopen.md)<br/>
[freopen, \_wfreopen](freopen-wfreopen.md)<br/>
[\_açık, \_aç](open-wopen.md)<br/>
