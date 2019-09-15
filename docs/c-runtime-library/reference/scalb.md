---
title: _scalb, _scalbümf
ms.date: 04/05/2018
api_name:
- _scalb
- _scalbf
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
ms.openlocfilehash: 630a5e3db2c39cb40d31c71e6a6dfa214ed91e34
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948890"
---
# <a name="_scalb-_scalbf"></a>_scalb, _scalbümf

Bağımsız değişkeni 2 kuvvetle ölçeklendirir.

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

*x*<br/>
Çift duyarlıklı, kayan nokta değeri.

*exp*<br/>
Uzun tamsayı üs.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa üstel bir değer döndürür. Taşma durumunda ( *x*işaretine bağlı olarak), **_scalb** , +/- **HUGE_VAL**; döndürür **errno** değişkeni **ERANGE**olarak ayarlanır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Scalb** işlevi *x* \* 2<sup>*Exp*</sup>değerini hesaplar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_scalb**, **_scalbümf**|\<float. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
