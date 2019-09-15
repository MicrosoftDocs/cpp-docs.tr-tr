---
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
ms.openlocfilehash: 0d45e5c857e917ca23b62482c64a06314565226e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948960"
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

Yeni kodda yalnızca **_RTC_SetErrorFuncW**kullanın. **_RTC_SetErrorFunc** , yalnızca geri uyumluluk için kitaplığa dahil edilmiştir.

**_RTC_SetErrorFuncW** geri çağırması yalnızca bağlı olduğu, genel olarak değil bileşen için geçerlidir.

**_RTC_SetErrorFuncW** 'e geçirdiğiniz adresin geçerli bir hata işleme işlevinin olduğundan emin olun.

Bir hata [_RTC_SetErrorType](rtc-seterrortype.md)kullanarak-1 türü atanmışsa, hata işleme işlevi çağrılmaz.

Bu işlevi çağırabilmeniz için önce çalışma zamanı hata denetimi başlatma işlevlerinden birini çağırmanız gerekir. Daha fazla bilgi için bkz. [C çalışma zamanı kitaplığı olmadan çalışma zamanı denetimlerini kullanma](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

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

*kısaltın*<br/>
Hatanın gerçekleştiği kaynak dosya veya hata ayıklama bilgisi yoksa null.

*onayın*<br/>
Hatanın gerçekleştiği *dosya adında* satır veya hata ayıklama bilgisi yoksa 0.

*Ladı*<br/>
Hatanın oluştuğu DLL veya yürütülebilir dosya adı.

*format*<br/>
kalan parametreleri kullanarak bir hata iletisi görüntüleyen printf stili dize. VA_ARGLIST ilk bağımsız değişkeni oluşan RTC hata numarasıdır.

**_RTC_error_fnW**'in nasıl kullanılacağını gösteren bir örnek için bkz. [yerel çalışma zamanı denetimleri özelleştirmesi](/visualstudio/debugger/native-run-time-checks-customization).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapı. h >|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
