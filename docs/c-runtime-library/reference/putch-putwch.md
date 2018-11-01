---
title: _putch, _putwch
ms.date: 11/04/2016
apiname:
- _putwch
- _putch
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _putch
- putwch
- _putwch
helpviewer_keywords:
- _putch function
- characters, writing
- putwch function
- _putwch function
- putch function
- console, writing characters to
ms.assetid: 3babc7cf-e333-405d-8449-c788d61d51aa
ms.openlocfilehash: 9abd27a926e641e72595360ed3951fad9e888676
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434768"
---
# <a name="putch-putwch"></a>_putch, _putwch

Konsola bir karakter yazar.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _putch(
int c
);
wint_t _putwch(
   wchar_t c
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Çıktı olacak karakter.

## <a name="return-value"></a>Dönüş Değeri

Döndürür *c* başarılı olursa. Varsa **_putch** döndürür, başarısız **EOF**if **_putwch** döndürür, başarısız **WEOF**.

## <a name="remarks"></a>Açıklamalar

Bu işlevler karakter yazma *c* , konsola arabelleğe alma olmadan doğrudan. Windows NT'de **_putwch** geçerli konsol yerel ayarını kullanarak Unicode karakterler yazar.

Sürümlerle **_nolock** soneki, bunlar başka iş parçacıklarının engellemelerinden korunmamaları hariç, aynıdır. Daha fazla bilgi için **_putch_nolock**, **_putwch_nolock**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_puttch**|**_putch**|**_putch**|**_putwch**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putch**|\<conio.h >|
|**_putwch**|\<conio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

Örneğin bakın [_getch](getch-getwch.md).

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
