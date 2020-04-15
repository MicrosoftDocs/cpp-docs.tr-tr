---
title: getenv, _wgetenv
description: Microsoft C çalışma zamanı getenv _wgetenv kitaplığını ve işlevlerini açıklar.
ms.date: 4/2/2020
api_name:
- getenv
- _wgetenv
- _o__wgetenv
- _o_getenv
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wgetenv
- getenv
- _tgetenv
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
no-loc:
- getenv
- _wgetenv
- getenv_s
- _wgetenv_s
- _putenv_s
- main
- wmain
- errno
- EINVAL
- ERANGE
- _environ
- _wenviron
- _putenv
- _wputenv
- _tgetenv_s
- _tzset
- _dupenv_s
- _wdupenv_s
ms.openlocfilehash: c9d7f7e1a2c5d6b15aee2f7f972a30cc0c90115c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344249"
---
# <a name="getenv-_wgetenv"></a>getenv, _wgetenv

Geçerli ortamdan bir değer alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)bakın.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
char *getenv(
   const char *varname
);
wchar_t *_wgetenv(
   const wchar_t *varname
);
```

### <a name="parameters"></a>Parametreler

*Varname*<br/>
Çevre değişken adı.

## <a name="return-value"></a>Döndürülen değer

*Varname*içeren ortam tablosu girişine bir işaretçi döndürür. Döndürülen işaretçiyi kullanarak ortam değişkeninin değerini değiştirmek güvenli değildir. Bir ortam değişkeninin değerini değiştirmek için [_putenv](putenv-wputenv.md) işlevini kullanın. *Varname* ortam tablosunda bulunmazsa iade değeri **NULL'dur.**

## <a name="remarks"></a>Açıklamalar

**Getenv** işlevi *varname*için ortam değişkenleri listesini arar. **getenv** Windows işletim sisteminde büyük/küçük harf duyarlı değildir. **getenv** ve **_putenv,** çevreye erişmek için küresel değişken **_environ** işaret ettiği ortamın kopyasını kullanırlar. **getenv,** işletim sistemi tarafından işlem için oluşturulan ortam "segmenti" üzerinde değil, yalnızca çalışma zamanı kitaplığı için erişilebilen veri yapılarında çalışır. Bu nedenle, [ana](../../cpp/main-function-command-line-args.md) veya [wmain](../../cpp/main-function-command-line-args.md) *için envp* bağımsız değişkeni kullanan programlar geçersiz bilgi alabilir.

*Varname* **NULL**ise, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisi çağırır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL** **için errno** ayarlar ve **NULL**döndürür.

**_wgetenv** **getenv**geniş karakterli bir sürümüdür; _wgetenv bağımsız değişkeni **_wgetenv** ve geri dönüş değeri geniş karakterli dizeleridir. **_wenviron** global **değişken, _environ**geniş karakterli bir sürümüdür.

Bir MBCS programında (örneğin, bir SBCS ASCII programında), ortam çok bayt karakterli dizelerden oluştuğuiçin **_wenviron** başlangıçta **NULL'dur.** Daha sonra, [_wputenv](putenv-wputenv.md)için ilk çağrıda, ya da **_wgetenv** için ilk çağrıda bir (MBCS) ortamı zaten varsa, karşılık gelen geniş karakterli dize ortamı oluşturulur ve daha sonra **_wenviron**tarafından işaret edilir.

Benzer şekilde, unicode **(_wmain**) programında da ortam geniş karakterli dizeleri **oluşturduğundan, _environ** başlangıçta **NULL'dur.** Daha sonra, **_putenv**için ilk çağrıda, ya da **getenv** için ilk çağrıda eğer bir (Unicode) ortam zaten var, ilgili bir MBCS ortamı oluşturulur ve daha sonra **_environ**tarafından işaret edilir.

Bir programda ortamın iki kopyası (MBCS ve Unicode) aynı anda varsa, çalışma zamanı sisteminin her iki kopyayı da tutması gerekir ve bu da yürütme süresinin daha yavaş olması gerekir. Örneğin, **_putenv'** ı arayarak, **_wputenv'a** yapılan çağrı da otomatik olarak yürütülür, böylece iki ortam dizeleri karşılık gelir.

> [!CAUTION]
> Çalışma zamanı sistemi hem Unicode sürümünü hem de ortamın çok bayt sürümünü korurken, bu iki ortam sürümü tam olarak karşılık sızmayabilir. Bunun nedeni, benzersiz bir çok bayt karakterli dize yle eşlemesine rağmen, benzersiz bir Unicode dizesinden çok bayt karakterli bir dize eşlemenin mutlaka benzersiz olmamasıdır. Daha fazla bilgi için [_environ _wenviron.](../../c-runtime-library/environ-wenviron.md)

> [!NOTE]
> Fonksiyonların **_putenv** ve **_getenv** aileleri iş parçacığı açısından güvenli değildir. **_getenv,** **_putenv** dizeyi değiştirerek rasgele hatalara neden olurken bir dize işaretçisi döndürebilir. Bu işlevlere yapılan çağrıların eşitlendirildiğinden emin olun.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**Getenv**|**Getenv**|**_wgetenv**|

**TZ** ortam değişkeninin değerini kontrol etmek veya değiştirmek için **getenv,** **_putenv** ve **_tzset** gerektiği gibi kullanın. **TZ**hakkında daha fazla bilgi için [_tzset](tzset.md) [ve _daylight, saat dilimi ve _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getenv**|\<stdlib.h>|
|**_wgetenv**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_getenv.c
// compile with: /W3
// This program uses getenv to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *libvar;

   // Get the value of the LIB environment variable.
   libvar = getenv( "LIB" ); // C4996
   // Note: getenv is deprecated; consider using getenv_s instead

   if( libvar != NULL )
      printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects the environment
   // variable of the current process. The command processor's
   // environment is not changed.
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996
   // Note: _putenv is deprecated; consider using putenv_s instead

   // Get new value.
   libvar = getenv( "LIB" ); // C4996

   if( libvar != NULL )
      printf( "New LIB variable is: %s\n", libvar );
}
```

```Output
Original LIB variable is: C:\progra~1\devstu~1\vc\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve çevre kontrolü](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[Ortam sabitleri](../../c-runtime-library/environmental-constants.md)<br/>
