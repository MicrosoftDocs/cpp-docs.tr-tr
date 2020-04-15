---
title: _scalb, _scalbf
ms.date: 4/2/2020
api_name:
- _scalb
- _scalbf
- _o__scalb
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- scalb
- _scalb
- _scalbf
helpviewer_keywords:
- exponential calculations
- _scalb function
- _scalbf function
- scalb function
ms.assetid: 148cf5a8-b405-44bf-a1f0-7487adba2421
ms.openlocfilehash: 6501fe53e67d0f277fa64c08e0edbff1d7eeb61a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332683"
---
# <a name="_scalb-_scalbf"></a>_scalb, _scalbf

Bağımsız değişkeni 2'lik bir güçle ölçeklendirin.

## <a name="syntax"></a>Sözdizimi

```C
double _scalb(
   double x,
   long exp
);
float _scalbf(
   float x,
   long exp
); /* x64 only */
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Çift duyarlıklı, kayan nokta değeri.

*Exp*<br/>
Uzun bir sayı, üs.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa üstel bir değer verir. Taşmada *(x*işaretine bağlı olarak), **_scalb** +/- **HUGE_VAL**döndürür; **errno** değişkeni **ERANGE**olarak ayarlanır.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_scalb** fonksiyonu *x* \* 2<sup>*exp*</sup>değerini hesaplar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_scalb**, **_scalbf**|\<float.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
