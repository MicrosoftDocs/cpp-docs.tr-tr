---
title: GETENV, _wgetenv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f83ac7c044f019699556d69ddbf199cbfc02dc0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="getenv-wgetenv"></a>getenv, _wgetenv

Geçerli ortamından bir değer alır. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

İşaretçi ortamı tabloyu içeren girişi döndüren *varname*. Döndürülen işaretçisi kullanılarak ortam değişkeninin değerini değiştirmek güvenli değildir. Kullanım [_putenv](putenv-wputenv.md) bir ortam değişkeninin değerini değiştirmek için işlevi. Dönüş değeri **NULL** varsa *varname* ortamı tablosunda bulunamadı.

## <a name="remarks"></a>Açıklamalar

**Getenv** işlevi için ortam değişkenleri listesi arar *varname*. **GETENV** Windows işletim sisteminde büyük küçük harfe duyarlı değildir. **GETENV** ve **_putenv** genel değişkeni tarafından işaret ortam kopyasını kullanmak **_environ** ortama erişmek için. **GETENV** yalnızca çalışma zamanı kitaplığı'na erişilebilir veri yapıları ve "işlem için işletim sistemi tarafından oluşturulan segment" ortam üzerinde çalışır. Bu nedenle, kullanan programlar *envp* bağımsız değişkeni [ana](../../cpp/main-program-startup.md) veya [wmain](../../cpp/main-program-startup.md) geçersiz bilgiler alabilir.

Varsa *varname* olan **NULL**, bu işlev açıklandığı gibi bir geçersiz parametre işleyicisi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür **NULL**.

**_wgetenv** bir joker karakter sürümü **getenv**; bağımsız değişkeni ve dönüş değeri **_wgetenv** joker karakter dizelerdir. **_Wenviron** genel değişkeni sürümüdür bir joker karakter **_environ**.

MBCS programında (örneğin, bir programında SBCS ASCII), **_wenviron** başlangıçta **NULL** çok baytlı karakter dizeleri oluşturulan ortam olduğundan. Ardından, ilk çağrıda [_wputenv](putenv-wputenv.md), ya da ilk çağrıda **_wgetenv** (MBCS) ortam zaten varsa, karşılık gelen bir joker karakter dizesi ortamı oluşturulur ve ardından olarak tarafındanverilir **_wenviron**.

Benzer şekilde, bir Unicode (**_wmain**) programı **_environ** başlangıçta **NULL** joker karakter dizelerini oluşturulan ortam olduğundan. Ardından, ilk çağrıda **_putenv**, ya da ilk çağrıda **getenv** (Unicode) ortam zaten varsa, karşılık gelen bir MBCS ortamı oluşturulur ve ardından işaret ediyor **_ environ**.

Ortam (MBCS ve Unicode) iki kopyasını aynı anda bir program varsa, çalışma zamanı sistem kaynaklanan yavaş yürütme süresi içinde her iki kopya bulundurmanız gerekir. Örneğin, her çağırmanız **_putenv**, çağrı **_wputenv** böylece iki ortam dizeleri karşılık da otomatik olarak yürütülür.

> [!CAUTION]
> Çalışma zamanı sistem Unicode sürümü ve ortam, birden çok baytlı sürümü korurken nadir durumlarda, bu iki ortam sürümleri tam olarak karşılık gelmeyebilir. Benzersiz bir UNICODE dizesi herhangi bir benzersiz çok baytlı karakter dizesini eşleştirir ancak çok baytlı karakter dizesi için benzersiz bir UNICODE dizesi eşlemesinden mutlaka benzersiz olmadığından budur. Daha fazla bilgi için bkz: [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv** ve **_getenv** işlevlerin aileleri iş parçacığı açısından güvenli değildir. **_getenv** sırasında dize işaretçisi döndürebilirsiniz **_putenv** rastgele hatalarına neden dize değiştiriyor. Bu işlevler çağrıları eşitlendiğinden emin olun.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**GETENV**|**GETENV**|**_wgetenv**|

Denetlemek veya değerini değiştirmek için **TZ** ortam değişkeni, kullanım **getenv**, **_putenv** ve **_tzset** gerektiği. Hakkında daha fazla bilgi için **TZ**, bkz: [_tzset](tzset.md) ve [_daylight, saat dilimi ve _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**GETENV**|\<stdlib.h >|
|**_wgetenv**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
