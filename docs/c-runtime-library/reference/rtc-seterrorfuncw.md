---
title: _RTC_SetErrorFuncW | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1eb3b8e5f6fb602675538c6588372b87df8781ac
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW

Çalışma zamanı hata denetimleri (RTCs) raporlaması için işleyici olarak bir işlev belirler.

## <a name="syntax"></a>Sözdizimi

```C
_RTC_error_fnW _RTC_SetErrorFuncW(
   _RTC_error_fnW function
);
```

### <a name="parameters"></a>Parametreler

*İşlevi*<br/>
Çalışma zamanı hata denetimleri işleyecek işlevi adresi.

## <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış hata işlevi; veya **NULL** önceden tanımlanmış bir işlev ise.

## <a name="remarks"></a>Açıklamalar

Yalnızca yeni kod içinde kullanma **_RTC_SetErrorFuncW**. **_RTC_SetErrorFunc** yalnızca geriye dönük uyumluluk için kitaplığında yer.

**_RTC_SetErrorFuncW** , bağlı bileşen geri çağırma uygulanır, ancak genel olarak değil.

Emin olmak için geçirdiğiniz adresi **_RTC_SetErrorFuncW** geçerli hata işlevi işleme olan.

Hata -1 türünü kullanarak atanmış olan varsa [_RTC_SetErrorType](rtc-seterrortype.md), hata işlevi işleme çağrılmaz.

Bu işlev aramadan önce ilk çalışma zamanı hata denetimi başlatma işlevlerinden birini çağırmanız gerekir. Daha fazla bilgi için bkz: [kullanarak çalışma zamanı denetler olmadan C çalışma zamanı kitaplığı](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

**_RTC_error_fnW** şu şekilde tanımlanır:

> **TypeDef int (__cdecl \*_RTC_error_fnW) (int** *errorType* **, const wchar_t \***  *filename* **, int***linenumber* **, const wchar_t \***  *moduleName* **, const wchar_t \***  *biçimi* **,...);** 

burada:

*errorType* tarafından belirtilen hata türü [_RTC_SetErrorType](rtc-seterrortype.md).

*filename* hatanın oluştuğu kaynak dosyası ya da hiç hata ayıklama bilgileri kullanılabiliyorsa, null.

*LineNumber* satırda *filename* hatanın oluştuğu ya da 0 hata ayıklama bilgisi yok.

*moduleName* DLL veya hatanın oluştuğu yürütülebilir dosya adı.

*Biçim* kalan parametrelerini kullanarak bir hata iletisi görüntülenecek printf stili dize. VA_ARGLIST ilk bağımsız değişkeni oluşan RTC hata sayısıdır.

Nasıl kullanılacağını gösteren bir örnek için **_RTC_error_fnW**, bkz: [yerel çalışma zamanı denetler özelleştirme](/visualstudio/debugger/native-run-time-checks-customization).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
