---
title: getenv, _wgetenv
description: Microsoft C çalışma zamanı kitaplığı getenv ve _wgetenv işlevlerini açıklar.
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: ea7fba1dd47123919dc0a01fd84bad65481b9db9
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913660"
---
# <a name="getenv-_wgetenv"></a>getenv, _wgetenv

Geçerli ortamdan bir değer alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*varname*<br/>
Ortam değişkeni adı.

## <a name="return-value"></a>Döndürülen değer

*Varname*içeren ortam tablosu girişi için bir işaretçi döndürür. Döndürülen işaretçiyi kullanarak ortam değişkeninin değerini değiştirmek güvenli değildir. Bir ortam değişkeninin değerini değiştirmek için [_putenv](putenv-wputenv.md) işlevini kullanın. *Değişken adı* ortam tablosunda bulunmazsa dönüş değeri **null** olur.

## <a name="remarks"></a>Açıklamalar

**Getenv** işlevi, *varname*için ortam değişkenlerinin listesini arar. **getenv** , Windows işletim sisteminde büyük küçük harfe duyarlı değildir. **getenv** ve **_putenv** , ortama erişmek için **_environ** genel değişken tarafından işaret edilen ortamın kopyasını kullanır. **getenv** yalnızca çalışma zamanı kitaplığı için erişilebilir olan ve işletim sistemi tarafından işlem için oluşturulan "segment" ortamında olmayan veri yapılarında çalışır. Bu nedenle, [ana](../../cpp/main-function-command-line-args.md) veya [wmain](../../cpp/main-function-command-line-args.md) için *envp* bağımsız değişkenini kullanan programlar geçersiz bilgiler alabilir.

*Varname* **null**Ise, bu işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **null**değerini döndürür.

**_wgetenv** , **getenv**; öğesinin geniş karakterli bir sürümüdür **_wgetenv** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. **_Wenviron** genel değişkeni, **_environ**geniş karakterli bir sürümüdür.

Bir MBCS programında (örneğin, bir SBCS ASCII programında), ortam çok baytlı karakter dizelerinden oluştuğu için başlangıçta **NULL** **_wenviron** . Ardından, [_wputenv](putenv-wputenv.md)için ilk çağrıda **_wgetenv** veya bir (MBCS) ortamı zaten varsa, buna karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından **_wenviron**tarafından gösterilir.

Benzer şekilde, bir Unicode (**_wmain**) programında, ortam geniş karakter dizelerinden oluştuğu için **_environ** başlangıçta **null** olur. Ardından, **_putenv**ilk çağrıda veya **getenv** için Ilk çağrıda bir (Unicode) ortam zaten varsa, buna karşılık gelen bir MBCS ortamı oluşturulur ve sonra **_environ**tarafından gösterilir.

Ortamın iki kopyası (MBCS ve Unicode) bir programda aynı anda mevcut olduğunda, çalışma zamanı sisteminin her iki kopyayı da koruması gerekir, bu da daha yavaş yürütme süresine neden olur. Örneğin, **_putenv**her çağırdığınızda, iki ortam dizesinin karşılık gelmesi için **_wputenv** çağrısı de otomatik olarak yürütülür.

> [!CAUTION]
> Nadir örneklerde, çalışma zamanı sistemi hem Unicode sürümü hem de bir çok baytlı sürümü korunurken, bu iki ortam sürümü tam olarak karşılamayabilir. Bunun nedeni, benzersiz bir çok baytlı karakter dizesinin benzersiz bir Unicode dizesine eşlenmesine karşın, benzersiz bir Unicode dizesinden çok baytlı karakter dizesine eşlemenin benzersiz olması gerekir. Daha fazla bilgi için bkz. [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> İşlevlerin **_putenv** ve **_getenv** aileleri iş parçacığı açısından güvenli değildir. **_getenv** , **_putenv** dizeyi değiştirirken rastgele hatalara neden olan bir dize işaretçisi döndürebilir. Bu işlevlere yapılan çağrıların eşitlendiğinden emin olun.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

**TZ** ortam değişkeninin değerini denetlemek veya değiştirmek için, **getenv**, **_putenv** ve **_tzset** gereken şekilde kullanın. **TZ**hakkında daha fazla bilgi için bkz. [_tzset](tzset.md) ve [_daylight, saat dilimi ve _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getenv**|\<Stdlib. h>|
|**_wgetenv**|\<Stdlib. h> veya \<wchar. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[Ortam sabitleri](../../c-runtime-library/environmental-constants.md)<br/>
