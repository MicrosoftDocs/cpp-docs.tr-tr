---
title: getenv, _wgetenv
ms.date: 11/04/2016
apiname:
- getenv
- _wgetenv
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 79c685fef8d6a4b966c53bb7d94b423d16971976
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157675"
---
# <a name="getenv-wgetenv"></a>getenv, _wgetenv

Geçerli ortamdan bir değer alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*varName*<br/>
Ortam değişkeni adı.

## <a name="return-value"></a>Dönüş Değeri

Ortam tablosunu içeren giriş işaretçi döndüren *varname*. Döndürülen işaretçisi kullanılarak ortam değişkeninin değerini değiştirmek güvenli değildir. Kullanım [_putenv](putenv-wputenv.md) bir ortam değişkeninin değerini değiştirmek için işlevi. Dönüş değeri **NULL** varsa *varname* ortam tablosunda bulunamadı.

## <a name="remarks"></a>Açıklamalar

**Getenv** işlevi için ortam değişkenleri listesi arar *varname*. **GETENV** Windows işletim sistemi büyük/küçük harfe duyarlı değildir. **GETENV** ve **_putenv** için genel değişkeni tarafından işaret edilen ortamın kopyasını kullanın **_environ** ortama erişmek için. **GETENV** yalnızca çalışma zamanı kitaplığının erişilebildiği veri yapıları ve ortam işlem için işletim sistemi tarafından oluşturulan "segment" üzerinde çalışır. Bu nedenle, kullanan programlar *envp* bağımsız değişkeni [ana](../../cpp/main-program-startup.md) veya [wmain](../../cpp/main-program-startup.md) geçersiz bilgi alabilir.

Varsa *varname* olduğu **NULL**, bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **NULL**.

**_wgetenv** geniş karakterli sürümüdür **getenv**; bağımsız değişkeni ve dönüş değeri **_wgetenv** geniş karakterli dizelerdir. **_Wenviron** genel değişkeni, bir geniş karakter sürümünü **_environ**.

Bir MBCS programında (örneğin, programda bir ASCII SBCS) **_wenviron** başlangıçta **NULL** çünkü ortam çok baytlı karakter dizeleri kümesinden oluşur. Daha sonra yapılan ilk çağrıda [_wputenv](putenv-wputenv.md), veya yapılan ilk çağrıda **_wgetenv** (MBCS) ortamı zaten varsa, karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından için tarafındanişaretedilen **_wenviron**.

Benzer şekilde, bir Unicode (**_wmain**) programı **_environ** başlangıçta **NULL** çünkü ortam geniş karakter dizeleri kümesinden oluşur. Daha sonra yapılan ilk çağrıda **_putenv**, veya yapılan ilk çağrıda **getenv** (Unicode) ortamı zaten varsa, karşılık gelen bir MBCS ortamı oluşturulur ve ardından tarafından işaret edilen **_ environ**.

Ortam (MBCS ve Unicode) iki kopyasını aynı anda bir programda varsa, çalışma zamanı sistemi daha yavaş yürütme süresi bunun sonucunda, her iki kopyasında sürdürmeniz gerekir. Örneğin, her çağırmanız **_putenv**, çağrı **_wputenv** böylece iki ortam dizeleri karşılık da otomatik olarak yürütülür.

> [!CAUTION]
> Çalışma zamanı sistemi, hem Unicode sürümü hem de çok baytlı bir sürüm ortamının muhafaza ederken nadir durumlarda, bu iki ortam sürümleri tam olarak karşılık gelmeyebilir. Benzersiz bir çok baytlı karakterli dize benzersiz bir Unicode dizesini eşleştirir ancak bir çok baytlı karakter dizesi benzersiz bir Unicode dize eşleme mutlaka benzersiz olmadığından budur. Daha fazla bilgi için [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv** ve **_getenv** işlev aileleri iş parçacığı açısından güvenli değildir. **_getenv** dize işaretçisini döndürebilir **_putenv** rastgele hatalara neden dize değiştirme. Bu işlevlere aramaların eşitlendiğinden emin olun.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

Denetleyin ya da değerini değiştirmek için **TZ** ortam değişkenini kullanmak **getenv**, **_putenv** ve **_tzset** gerektiği şekilde. Hakkında daha fazla bilgi için **TZ**, bkz: [_tzset](tzset.md) ve [_daylight, saat diliminizi ve _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**getenv**|\<stdlib.h >|
|**_wgetenv**|\<stdlib.h > veya \<wchar.h >|

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

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[Ortam Sabitleri](../../c-runtime-library/environmental-constants.md)<br/>
