---
title: _scalb, _scalbf | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _scalb
- _scalbf
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- scalb
- _scalb
- _scalbf
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- _scalb function
- _scalbf function
- scalb function
ms.assetid: 148cf5a8-b405-44bf-a1f0-7487adba2421
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47b6e20c6395337113088aa51d8ba75744421922
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207526"
---
# <a name="scalb-scalbf"></a>_scalb, _scalbf

2'in kuvveti olarak ölçek bağımsız değişkeni.

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

Başarılı olursa üstel bir değer döndürür. Taşma (işaretini bağlı olarak *x*), **_scalb** döndürür **HUGE_VAL**; **errno** değişkeni ayarlanır  **ERANGE**.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Scalb** işlevi değerini hesaplar *x* \* 2<sup>*exp*</sup>.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_scalb**, **_scalbf**|\<float.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
