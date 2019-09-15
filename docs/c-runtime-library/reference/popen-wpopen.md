---
title: _popen, _wpopen
ms.date: 11/04/2016
api_name:
- _popen
- _wpopen
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
ms.openlocfilehash: 0e58ffd523c6919d70c68454f3547736afdef565
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70950992"
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

*komutundaki*<br/>
Yürütülecek komut.

*modundaysa*<br/>
Döndürülen akışın modu.

## <a name="return-value"></a>Dönüş Değeri

Oluşturulan kanalın bir sonuyla ilişkili bir akış döndürür. Kanalın diğer ucu, oluşturulan komutun standart girişi veya standart çıkışıyla ilişkilendirilir. İşlevler bir hata üzerinde **null değeri** döndürür. Hata geçersiz bir parametredir (örneğin, *komut* veya *mod* null işaretçisiyse veya *mod* geçerli bir mod değilse, **errno** , **EINVAL**olarak ayarlanır. Geçerli modlar için açıklamalar bölümüne bakın.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Popen** işlevi bir kanal oluşturur ve belirtilen dize *komutuyla*komut işlemcisinin oluşturulan bir kopyasını zaman uyumsuz olarak yürütür. Karakter dizesi *modu* , istenen erişim türünü aşağıdaki gibi belirtir.

|Erişim modu|Açıklama|
|-|-|
|**"r"**|Çağıran işlem, döndürülen akışı kullanarak, oluşturulan komutun standart çıkışını okuyabilir.|
|**"w"**|Çağıran işlem, döndürülen akışı kullanarak, oluşturulan komutun standart girişine yazabilir.|
|**"b"**|İkili modda açın.|
|**şı**|Metin modunda açın.|

> [!NOTE]
> Bir Windows programında kullanılırsa, **_popen** işlevi, programın süresiz olarak yanıt vermemesine neden olan geçersiz bir dosya işaretçisi döndürür. **_popen** , konsol uygulamasında düzgün şekilde çalışmaktadır. Girişi ve çıktıyı yeniden yönlendiren bir Windows uygulaması oluşturmak için, bkz. Windows SDK [yeniden yönlendirilen giriş ve çıkışlarla bir alt Işlem oluşturma](/windows/win32/ProcThread/creating-a-child-process-with-redirected-input-and-output) .

**_wpopen** , **_popen**; öğesinin geniş karakterli bir sürümüdür. **_wpopen** için *yol* bağımsız değişkeni geniş karakterli bir dizedir. **_wpopen** ve **_popen** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tpopen**|**_popen**|**_popen**|**_wpopen**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_popen**|\<stdio. h >|
|**_wpopen**|\<stdio. h > veya \<wchar. h >|

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
      printf(psBuffer);
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

### <a name="sample-output"></a>Örnek Çıktı

Bu çıktı, geçerli dizinde. c dosya adı uzantısına sahip yalnızca bir dosya olduğunu varsayar.

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

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_pclose](pclose.md)<br/>
[_pipe](pipe.md)<br/>
