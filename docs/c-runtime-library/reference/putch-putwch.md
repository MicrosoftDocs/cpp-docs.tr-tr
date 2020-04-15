---
title: _putch, _putwch
ms.date: 4/2/2020
api_name:
- _putwch
- _putch
- _o__putch
- _o__putwch
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
- api-ms-win-crt-conio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 123d4a9b1ee5024ed85b7034462b469740012b85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338416"
---
# <a name="_putch-_putwch"></a>_putch, _putwch

Konsola bir karakter yazar.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*C*<br/>
Karakter çıktı olmak.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa *c* verir. **_putch** başarısız olursa, **EOF**döndürür; **_putwch** başarısız olursa, **WEOF**döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler *c* karakterini doğrudan, arabelleğe almadan konsola yazar. Windows NT'de **_putwch,** geçerli konsol yerel ayarını kullanarak Unicode karakterleri yazar.

**_nolock** sonekli sürümler, diğer iş parçacıkları tarafından parazite karşı korunmayan sürümler dışında aynıdır. Daha fazla bilgi için **_putch_nolock**, **_putwch_nolock.**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_puttch**|**_putch**|**_putch**|**_putwch**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putch**|\<conio.h>|
|**_putwch**|\<conio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

[_getch](getch-getwch.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve Bağlantı Noktası G/Ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
