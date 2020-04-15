---
title: _popen, _wpopen
description: Microsoft C çalışma zamanı (CRT) kitaplığı işlevleri _popen için bir başvuru ve. _wpopen
ms.date: 4/2/2020
api_name:
- _popen
- _wpopen
- _o__popen
- _o__wpopen
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tpopen
- popen
- wpopen
- _popen
- _wpopen
- _tpopen
helpviewer_keywords:
- tpopen function
- pipes, creating
- _popen function
- _tpopen function
- popen function
- wpopen function
- _wpopen function
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
no-loc:
- _popen
- _wpopen
- _tpopen
- _doserrno
- errno
- _sys_errlist
- _sys_nerr
- EINVAL
ms.openlocfilehash: 5b478893ef8f201f39cb63ecfc7ab174d16b86de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338510"
---
# <a name="_popen-_wpopen"></a>_popen, _wpopen

Bir boru oluşturur ve bir komut yürütür.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
FILE *_popen(
    const char *command,
    const char *mode
);
FILE *_wpopen(
    const wchar_t *command,
    const wchar_t *mode
);
```

### <a name="parameters"></a>Parametreler

*Komut*\
İdam edilecek komut.

*Modu*\
Döndürülen akışın modu.

## <a name="return-value"></a>Döndürülen değer

Oluşturulan borunun bir ucuyla ilişkili bir akışı döndürür. Borunun diğer ucu, oluşturulan komutun standart girişi veya standart çıktısıyla ilişkilidir. İşlevler bir hata da **NULL** döndürdü. Hata geçersiz bir parametreden kaynaklanıyorsa, **errno** **EINVAL**olarak ayarlanır. Geçerli modlar için Açıklamalar bölümüne bakın.

Bu ve diğer hata kodları hakkında bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_popen** işlevi bir boru oluşturur. Daha sonra eş senkronize komut işlemcisinin yumurtlanmış bir kopyasını yürütür ve komut satırı olarak *komutu* kullanır. Karakter dize *modu* aşağıdaki gibi istenen erişim türünü belirtir.

|Erişim modu|Açıklama|
|-|-|
|**"r"**|Arama işlemi, döndürülen akışı kullanarak oluşturulan komutun standart çıktısını okuyabilir.|
|**"w"**|Arama işlemi, döndürülen akışı kullanarak oluşturulan komutun standart girişine yazılabilir.|
|**"b"**|İkili modda açın.|
|**"t"**|Metin modunda açın.|

> [!NOTE]
> Bir Windows programında kullanılırsa, **_popen** işlevi, programın süresiz yanıt vermeyi durdurmasına neden olan geçersiz bir dosya işaretçisi döndürür. **_popen** konsol uygulamasında düzgün çalışır. Giriş ve çıktıyı yeniden yönlendiren bir Windows uygulaması oluşturmak için [bkz.](/windows/win32/ProcThread/creating-a-child-process-with-redirected-input-and-output)

**_wpopen** **_popen**geniş karakterli bir versiyonudur; **_wpopen** *yol* bağımsız değişkeni geniş karakterli bir dizedir. **_wpopen** ve **_popen** aynı şekilde davranan.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tpopen**|**_popen**|**_popen**|**_wpopen**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_popen**|\<stdio.h>|
|**_wpopen**|\<stdio.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_popen.c
/* This program uses _popen and _pclose to receive a
* stream of text from a system process.
*/

#include <stdio.h>
#include <stdlib.h>

int main( void )
{

   char   psBuffer[128];
   FILE   *pPipe;

        /* Run DIR so that it writes its output to a pipe. Open this
         * pipe with read text attribute so that we can read it
         * like a text file.
         */

   if( (pPipe = _popen( "dir *.c /on /p", "rt" )) == NULL )
      exit( 1 );

   /* Read pipe until end of file, or an error occurs. */

   while(fgets(psBuffer, 128, pPipe))
   {
      puts(psBuffer);
   }

   /* Close pipe and print return value of pPipe. */
   if (feof( pPipe))
   {
     printf( "\nProcess returned %d\n", _pclose( pPipe ) );
   }
   else
   {
     printf( "Error: Failed to read the pipe to the end.\n");
   }
}
```

Bu çıktı, geçerli dizinde dosya adı uzantısı olan `.c` yalnızca bir dosya olduğunu varsayar.

```Output
Volume in drive C is CDRIVE
Volume Serial Number is 0E17-1702

Directory of D:\proj\console\test1

07/17/98  07:26p                   780 popen.c
               1 File(s)            780 bytes
                             86,597,632 bytes free

Process returned 0
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve çevre kontrolü](../../c-runtime-library/process-and-environment-control.md)\
[_pclose](pclose.md)\
[_pipe](pipe.md)
