---
title: log1p, log1pf, log1pl2
ms.date: 04/05/2018
api_name:
- log1p
- log1pf
- log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
ms.openlocfilehash: aad6675a832e1715c505026fe11ffe77f1f6d275
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953213"
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl

1 ile belirtilen değerin doğal logaritmasını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double log1p(
   double x
);

float log1p(
   float x
); //C++ only

long double log1p(
   long double x
); //C++ only

float log1pf(
   float x
);

long double log1pl(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta bağımsız değişkeni.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, (*x* + 1) için doğal (Base-*e*) günlüğünü döndürür.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Giriş|Sonuç|SEH özel durumu|errno|
|-----------|------------|-------------------|-----------|
|\+ INF|\+ INF|||
|Denormals|Giriş ile aynı|ÖĞE||
|±0|Giriş ile aynı|||
|-1|-INF|DIVBYZERO|ERANGE|
|< -1|nBir|GEÇERSİZ|EDOM|
|-INF|nBir|GEÇERSİZ|EDOM|
|± SNaN|Giriş ile aynı|GEÇERSİZ||
|± QNaN, sonsuz|Giriş ile aynı|||

**Errno** değeri, *x* =-1 olduğunda ERANGE olarak ayarlanır. **Errno** değeri, *x* <-1 ise **Edom** olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

*X* 0 yakınında **log1p** işlevleri kullanmaktan `log(x + 1)` daha doğru olabilir.

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren **log1p** aşırı yüklerini çağırabilirsiniz. C programında, **log1p** her zaman bir **Double**alır ve döndürür.

*X* doğal bir sayı ise, bu işlev (*x* -1) çarpınımını logaritmasını döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
