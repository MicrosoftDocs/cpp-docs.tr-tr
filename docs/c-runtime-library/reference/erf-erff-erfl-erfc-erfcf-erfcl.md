---
title: erf, erff, erfl, erfc, erfcf, erfcl
ms.date: 4/2/2020
api_name:
- erff
- erfl
- erf
- erfc
- erfcf
- erfcl
- _o_erf
- _o_erfc
- _o_erfcf
- _o_erfcl
- _o_erff
- _o_erfl
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
- erfl
- erf
- erff
- erfc
- erfcf
- erfcl
helpviewer_keywords:
- erfl function
- erff function
- erf function
- erfcl function
- erfcf function
- erfc function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
ms.openlocfilehash: ad7ad279d3686e4f33a6f5f901c60348c131b89a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347917"
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl

Bir değerin hata işlevini veya tamamlayıcı hata işlevini hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**Erf** fonksiyonları *x*Gauss hata işlevini döndürmektedir. **Erfc** fonksiyonları *x*tamamlayıcı Gauss hata işlevini döndürmektedir.

## <a name="remarks"></a>Açıklamalar

**Erf** fonksiyonları *x'in*Gauss hata işlevini hesaplar:

![x'in hata fonksiyonu](media/crt_erf_formula.PNG "x'in hata fonksiyonu")

Tamamlayıcı Gauss hata fonksiyonu 1 - erf(x) olarak tanımlanır. **Erf** işlevleri -1,0 ile 1,0 aralığında bir değer döndürer. Hata iadesi yok. **Erfc** işlevleri 0 ile 2 aralığında bir değer döndürdü. *x* **erfc**için çok büyükse, **errno** değişkeni **ERANGE**olarak ayarlanır.

C++ aşırı yüklemeye izin verdiğinden, **float** ve **uzun** **çift** türleri alıp alan **aşırı erf** ve **erfc** yükleri arayabilirsiniz. Bir C programında, **erf** ve **erfc** her zaman almak ve bir **çift**dönmek .

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
