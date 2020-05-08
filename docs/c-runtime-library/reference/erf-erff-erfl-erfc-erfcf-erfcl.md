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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 633a766684ed7485ab579157ae4c94fe209f7e73
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915020"
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl

Hata işlevini veya bir değerin tamamlayıcı hata işlevini hesaplar.

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

*sayı*<br/>
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**HATAİŞLEV** Işlevleri *x*Gauss hata işlevini döndürür. **Erfc** işlevleri, *x*öğesinin tamamlayıcı Gauss hata işlevini döndürür.

## <a name="remarks"></a>Açıklamalar

**HATAİŞLEV** işlevleri, şöyle tanımlanan *x*Gauss hata işlevini hesaplar:

![X öğesinin hata işlevi](media/crt_erf_formula.PNG "X öğesinin hata işlevi")

Tamamlayıcı Gauss Error işlevi, 1-HATAİŞLEV (x) olarak tanımlanır. **HATAİŞLEV** işlevleri-1,0 ile 1,0 arasında bir değer döndürür. Hata döndürme yok. **Erfc** işlevleri 0 ile 2 aralığında bir değer döndürür. *X* , **erfc**için çok büyükse, **errno** değişkeni **ERANGE**olarak ayarlanır.

C++ aşırı yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren **HATAİŞLEV** ve **erfc** aşırı yüklerini çağırabilirsiniz. C programında, **HATAİŞLEV** ve **erfc** her zaman bir **Double**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**HATAİŞLEV**, **erff**, **ERFL**, **erfc**, **erfcf**, **erfcl**|\<Math. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
