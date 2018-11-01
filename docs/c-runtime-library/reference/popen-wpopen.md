---
title: _popen, _wpopen
ms.date: 11/04/2016
apiname:
- _popen
- _wpopen
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
ms.openlocfilehash: 5284685f56a73c4c7e48fce981745220651399a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498910"
---
# <a name="popen-wpopen"></a>_popen, _wpopen

Bir kanal oluşturur ve bir komutu yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Komutu*<br/>
Yürütülecek komut.

*Modu*<br/>
Döndürülen akışa modu.

## <a name="return-value"></a>Dönüş Değeri

Oluşturulan kanal bir uç ile ilişkili bir akış döndürür. Bir kanal sonuna üretilmiş komut standart giriş veya standart çıkış ile ilişkilidir. İşlevler dönüş **NULL** üzerinde hata. IF gibi geçersiz bir parametre hataysa *komut* veya *modu* null bir işaretçiyse veya *modu* geçerli bir moda değil **errno** ayarlanır **EINVAL**. Geçerli mod için Açıklamalar bölümüne bakın.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Popen** işlevi bir kanal oluşturur ve belirtilen dizeyi içeren komut işleyicisi üretilmiş bir kopyasını zaman uyumsuz olarak yürütür *komut*. Karakter dizesi *modu* gibi istenen erişim türünü belirtir.

|Erişim modu|Açıklama|
|-|-|
|**"r"**|Çağırma işlemi üretilmiş komut standart çıkışında döndürülen akışa kullanarak okuyabilir.|
|**"w"**|Çağırma işlemi, döndürülen akışa kullanarak üretilmiş komut standart girişi yazabilirsiniz.|
|**"b"**|İkili modda açık.|
|**"t"**|Metin modunda açın.|

> [!NOTE]
> Bir Windows programı kullandıysanız **_popen** işlevi, programın süresiz olarak yanıt vermemesine neden olan bir geçersiz dosya işaretçisini döndürür. **_popen** bir konsol uygulamasında düzgün çalışır. Giriş ve çıkış yönlendiren bir Windows uygulaması oluşturmak için bkz: [yeniden yönlendirilen giriş ve çıkış bir alt işlemi oluşturma](/windows/desktop/ProcThread/creating-a-child-process-with-redirected-input-and-output) Windows SDK.

**_wpopen** geniş karakterli sürümüdür **_popen**; *yolu* bağımsız değişkeni **_wpopen** geniş karakterli bir dizedir. **_wpopen** ve **_popen** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tpopen**|**_popen**|**_popen**|**_wpopen**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_popen**|\<stdio.h >|
|**_wpopen**|\<stdio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

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

Bu çıkış, yalnızca bir dosya var. geçerli dizindeki .c dosya adı uzantısına sahip varsayar.

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
