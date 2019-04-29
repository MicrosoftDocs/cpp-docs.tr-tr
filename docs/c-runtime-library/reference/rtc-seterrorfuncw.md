---
title: _RTC_SetErrorFuncW
ms.date: 11/04/2016
apiname:
- _RTC_SetErrorFuncW
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
apitype: DLLExport
f1_keywords:
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
ms.openlocfilehash: 03e9f540a215550a698700f28e5722b33b119149
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357232"
---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW

Çalışma zamanı hata denetimleri (RTCs) raporlaması için işleyici olarak bir işlevi belirtir.

## <a name="syntax"></a>Sözdizimi

```C
_RTC_error_fnW _RTC_SetErrorFuncW(
   _RTC_error_fnW function
);
```

### <a name="parameters"></a>Parametreler

*İşlevi*<br/>
Çalışma zamanı hata denetimlerini işleyecek işlevin adresi.

## <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış hata işlevini; veya **NULL** önceden tanımlanmış bir işlev ise.

## <a name="remarks"></a>Açıklamalar

Yeni kod içinde yalnızca kullanma **_RTC_SetErrorFuncW**. **_RTC_SetErrorFunc** yalnızca geriye dönük uyumluluk Kitaplığı'nda dahildir.

**_RTC_SetErrorFuncW** , bağlı bileşen geri çağırma uygular, ancak genel olarak değil.

Emin olun geçirdiğiniz adresi **_RTC_SetErrorFuncW** bu işleme işlevinin geçerli bir hata oluştu.

Hata -1 türünü kullanarak atanıp atanmadığını [_RTC_SetErrorType](rtc-seterrortype.md), hata işleme işlevi çağrılmaz.

Bu işlev çağrı yapmadan önce ilk çalışma zamanı hata denetimini başlatma işlevlerden birini çağırmanız gerekir. Daha fazla bilgi için [kullanarak çalışma zamanı denetimleri olmadan C çalışma zamanı kitaplığı](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

**_RTC_error_fnW** şu şekilde tanımlanır:

```cpp
typedef int (__cdecl * _RTC_error_fnW)(
    int errorType,
    const wchar_t * filename,
    int linenumber,
    const wchar_t * moduleName,
    const wchar_t * format,
    ... );
```

burada:

*ErrorType*<br/>
Tarafından belirtilen hata türünü [_RTC_SetErrorType](rtc-seterrortype.md).

*Dosya adı*<br/>
Hatanın oluştuğu kaynak dosyası veya hata ayıklama bilgisi yok yoksa null.

*LineNumber*<br/>
Satırda *filename* hatanın oluştuğu ya da 0 hata ayıklama bilgisi yok.

*Modül adı*<br/>
DLL veya yürütülebilir dosya adına hatanın oluştuğu.

*Biçim*<br/>
printf türü dize kalan parametrelerle bir hata iletisi görüntüler. İlk bağımsız değişkenin VA_ARGLIST oluşan RTC hata sayısıdır.

Nasıl kullanılacağını gösteren bir örnek için **_RTC_error_fnW**, bkz: [yerel çalışma zamanı denetimleri özelleştirme](/visualstudio/debugger/native-run-time-checks-customization).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
