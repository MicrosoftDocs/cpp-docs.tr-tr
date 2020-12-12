---
description: 'Hakkında daha fazla bilgi edinin: _RTC_SetErrorFuncW'
title: _RTC_SetErrorFuncW
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorFuncW
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: e1f92b791f986c7881f0c65a22c24432c03160e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341431"
---
# <a name="_rtc_seterrorfuncw"></a>_RTC_SetErrorFuncW

Çalışma zamanı hata denetimleri (RTCs) raporlaması için bir işlevi işleyici olarak belirler.

## <a name="syntax"></a>Sözdizimi

```C
_RTC_error_fnW _RTC_SetErrorFuncW(
   _RTC_error_fnW function
);
```

### <a name="parameters"></a>Parametreler

*çalışmayacaktır*<br/>
Çalışma zamanı hata denetimlerini işleyecek işlevin adresi.

## <a name="return-value"></a>Dönüş Değeri

Daha önce tanımlanan hata işlevi; veya daha önce tanımlanmış bir işlev yoksa **null** .

## <a name="remarks"></a>Açıklamalar

Yeni kodda yalnızca **_RTC_SetErrorFuncW** kullanın. **_RTC_SetErrorFunc** , yalnızca geri uyumluluk için kitaplığa dahil edilmiştir.

**_RTC_SetErrorFuncW** geri çağırması yalnızca bağlı olduğu, genel olarak değil, bileşen için geçerlidir.

**_RTC_SetErrorFuncW** için geçirdiğiniz adresin geçerli bir hata işleme işlevinin olduğundan emin olun.

Bir hataya [_RTC_SetErrorType](rtc-seterrortype.md)kullanılarak-1 türü atanmışsa, hata işleme işlevi çağrılmaz.

Bu işlevi çağırabilmeniz için önce çalışma zamanı hata denetimi başlatma işlevlerinden birini çağırmanız gerekir. Daha fazla bilgi için bkz. [C Run-Time kitaplığı olmadan Run-Time denetimleri kullanma](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

**_RTC_error_fnW** aşağıdaki gibi tanımlanır:

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

*errorType*<br/>
[_RTC_SetErrorType](rtc-seterrortype.md)tarafından belirtilen hata türü.

*filename*<br/>
Hatanın gerçekleştiği kaynak dosya veya hata ayıklama bilgisi yoksa null.

*onayın*<br/>
Hatanın gerçekleştiği *dosya adında* satır veya hata ayıklama bilgisi yoksa 0.

*Ladı*<br/>
Hatanın oluştuğu DLL veya yürütülebilir dosya adı.

*formatını*<br/>
kalan parametreleri kullanarak bir hata iletisi görüntüleyen printf stili dize. VA_ARGLIST ilk bağımsız değişkeni oluşan RTC hata numarasıdır.

**_RTC_error_fnW** nasıl kullanacağınızı gösteren bir örnek için bkz. [Yerel Run-Time denetimleri özelleştirmesi](/visualstudio/debugger/native-run-time-checks-customization).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h>|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Çalışma zamanı hata denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
