---
title: log1p, log1pf, log1pl2
description: Log1p, log1pf, log1pl2; için API başvurusu 1 ile belirtilen değerin doğal logaritmasını hesaplama.
ms.date: 9/1/2020
api_name:
- log1p
- log1pf
- log1pl
- _o_log1p
- _o_log1pf
- _o_log1pl
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
ms.openlocfilehash: 8858d761428d4dad6e3fe836b82041ae92f1827a
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556236"
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl

1 ile belirtilen değerin doğal logaritmasını hesaplar.

## <a name="syntax"></a>Söz dizimi

```C
double log1p(
   double x
);
float log1pf(
   float x
);
long double log1pl(
   long double x
);

#define log1p(X) // Requires C11 or higher

float log1p(
   float x
); //C++ only

long double log1p(
   long double x
); //C++ only
```

### <a name="parameters"></a>Parametreler

*sayı*\
Kayan nokta bağımsız değişkeni.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, (*x* + 1) için doğal (Base-*e*) günlüğünü döndürür.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Giriş|Sonuç|SEH özel durumu|errno|
|-----------|------------|-------------------|-----------|
|+ INF|+ INF|||
|Denormals|Giriş ile aynı|ÖĞE||
|± 0|Giriş ile aynı|||
|-1|-INF|DIVBYZERO|ERANGE|
|<-1|nBir|Geçersiz|EDOM|
|-INF|nBir|Geçersiz|EDOM|
|± SNaN|Giriş ile aynı|Geçersiz||
|± QNaN, sonsuz|Giriş ile aynı|||

**Errno** değeri, *x* =-1 olduğunda ERANGE olarak ayarlanır. **Errno** değeri, *x* <-1 ise **Edom** olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

X 0 yakınında **log1p** işlevleri kullanmaktan daha doğru olabilir `log(x + 1)` . *x*

C++ aşırı yüklemeye izin verdiğinden, ve türlerini alıp döndüren **log1p** aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **log1p** her zaman alır ve döndürür **`double`** .

\<tgmath.h> `log1p()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

*X* doğal bir sayı ise, bu işlev (*x* -1) çarpınımını logaritmasını döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<math.h>|\<cmath>|
|**log1p** makrosu | \<tgmath.h> ||

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik Işlev Başvurusu](crt-alphabetical-function-reference.md)\
[log2, log2f, log2l](log2-log2f-log2l.md)\
[log, logf, log10, log10f](log-logf-log10-log10f.md)
