---
title: _popen, _wpopen
description: Microsoft C çalışma zamanı (CRT) kitaplığı işlevleri _popen ve _wpopeniçin bir başvuru.
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 37e5bb491234e46a0e3330bc2fd42c16e54793fc
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915284"
---
# <a name="_popen-_wpopen"></a>_popen, _wpopen

Bir kanal oluşturur ve bir komut yürütür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*komutundaki*\
Yürütülecek komut.

*modundaysa*\
Döndürülen akışın modu.

## <a name="return-value"></a>Döndürülen değer

Oluşturulan kanalın bir sonuyla ilişkili bir akış döndürür. Kanalın diğer ucu, oluşturulan komutun standart girişi veya standart çıkışıyla ilişkilendirilir. İşlevler bir hata üzerinde **null değeri** döndürür. Hata geçersiz bir parametre nedeniyle kaynaklanıyorsa, **errno** , **EINVAL**olarak ayarlanır. Geçerli modlar için açıklamalar bölümüne bakın.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Popen** işlevi bir kanal oluşturur. Ardından komut işlemcisinin üretilmiş bir kopyasını zaman uyumsuz olarak yürütür ve komut satırı olarak *komutunu* kullanır. Karakter dizesi *modu* , istenen erişim türünü aşağıdaki gibi belirtir.

|Erişim modu|Açıklama|
|-|-|
|**sağ**|Çağıran işlem, döndürülen akışı kullanarak, oluşturulan komutun standart çıkışını okuyabilir.|
|**anlatımı**|Çağıran işlem, döndürülen akışı kullanarak, oluşturulan komutun standart girişine yazabilir.|
|**kenarı**|İkili modda açın.|
|**şı**|Metin modunda açın.|

> [!NOTE]
> Bir Windows programında kullanılırsa, **_popen** işlevi programın süresiz olarak yanıt vermemesine neden olan geçersiz bir dosya işaretçisi döndürür. **_popen** bir konsol uygulamasında düzgün şekilde çalışmaktadır. Girişi ve çıktıyı yeniden yönlendiren bir Windows uygulaması oluşturmak için, bkz. Windows SDK [yeniden yönlendirilen giriş ve çıkışlarla bir alt Işlem oluşturma](/windows/win32/ProcThread/creating-a-child-process-with-redirected-input-and-output) .

**_wpopen** , **_popen**geniş karakterli bir sürümüdür; _wpopen *yol* bağımsız değişkeni **_wpopen** , geniş karakterli bir dizedir. **_wpopen** ve **_popen** aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tpopen**|**_popen**|**_popen**|**_wpopen**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_popen**|\<stdio. h>|
|**_wpopen**|\<stdio. h> veya \<wchar. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

Bu çıktı, geçerli dizinde `.c` dosya adı uzantısına sahip yalnızca bir dosya olduğunu varsayar.

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

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)\
[_pclose](pclose.md)\
[_pipe](pipe.md)
