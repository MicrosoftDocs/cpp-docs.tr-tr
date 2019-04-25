---
title: lgamma, lgammaf, lgammal
ms.date: 04/05/2018
apiname:
- lgamma
- lgammaf
- lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: 43ce1599ab9161b9fadf5643ddd2ec739ab2d8b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157316"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

Belirtilen değerin gama fonksiyonu mutlak değerini doğal logaritmasını belirler.

## <a name="syntax"></a>Sözdizimi

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
İşlem için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, gama işlevi mutlak değerini doğal logaritmasını Döndür *x*.

|Sorun|döndürülecek|
|-----------|------------|
|*x* NaN =|NaN|
|*x* = ±0|+ INFİNİTY|
|*x*negatif tamsayı =|+ INFİNİTY|
|±INFINITY|+ INFİNİTY|
|kutup hata|+ HUGE_VAL + HUGE_VALF, veya + HUGE_VALL|
|Taşma aralık hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|

Hatalar rapor, belirtilen [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **lgamma** alan ve getiren **float** ve **uzun** **çift** türleri. C programında **lgamma** her zaman alan ve döndüren bir **çift**.

X bir rasyonel sayı ise, bu işlev faktöriyelini (x - 1) logaritmasını döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**lgamma**, **lgammaf**, **lgammal**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
