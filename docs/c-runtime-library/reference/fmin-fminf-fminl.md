---
title: fmin, fminf, fminl
ms.date: 04/05/2018
apiname:
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
ms.openlocfilehash: f73853e18bd5d7f699cd2c3109fe5fb830859bf1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333384"
---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl

Belirtilen iki değerin daha küçük belirler.

## <a name="syntax"></a>Sözdizimi

```C
double fmin(
   double x,
   double y
);

float fmin(
   float x,
   float y
); //C++ only

long double fmin(
   long double x,
   long double y
); //C++ only

float fminf(
   float x,
   float y
);

long double fminl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Karşılaştırılacak ilk değer.

*Y*<br/>
Karşılaştırılacak ikinci değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa döndürür, daha küçük *x* veya *y*.

|Giriş|Sonuç|
|-----------|------------|
|*x* NaN olup|*Y*|
|*y* NaN olup|*x*|
|*x* ve *y* NaN olan|NaN|

İşlev neden olmaz [_matherr](matherr.md) çağrılacak, kayan nokta özel durumların neden değiştirin veya **errno**.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **fmin** alan ve getiren **float** ve **uzun** **çift** türleri. C programında **fmin** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**fmin**, **fminf**, **fminl**|C: \<math.h ><br />C++: \<math.h > veya \<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
