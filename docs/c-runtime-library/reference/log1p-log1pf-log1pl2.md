---
title: log1p, log1pf, log1pl2
ms.date: 04/05/2018
apiname:
- log1p
- log1pf
- log1pl
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
ms.openlocfilehash: 2ac864d7e28823c95b0202c0a8f2454d03c64aff
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519318"
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl

1 ek olarak belirtilen değere doğal logaritmasını hesaplar.

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
Kayan noktalı bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, doğal döndürür (temel -*e*) oturumu (*x* + 1).

Aksi halde aşağıdaki değerlerden birini döndürebilir:

|Giriş|Sonuç|SEH özel durumu|errno|
|-----------|------------|-------------------|-----------|
|+ INF|+ INF|||
|Denormals|Aynı giriş|YETERSİZ KALMASI||
|±0|Aynı giriş|||
|-1|-INF|DIVBYZERO|ERANGE|
|< -1|NaN|GEÇERSİZ|EDOM|
|-INF|NaN|GEÇERSİZ|EDOM|
|±SNaN|Aynı giriş|GEÇERSİZ||
|±QNaN belirsiz|Aynı giriş|||

**Errno** değer ayarlanmışsa için ERANGE *x* = -1. **Errno** değeri ayarı **EDOM** varsa *x* < -1.

## <a name="remarks"></a>Açıklamalar

**Log1p** işlevleri kullanmaktan daha doğru `log(x + 1)` olduğunda *x* 0'dır.

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **log1p** alan ve getiren **float** ve **uzun** **çift** türleri. C programında **log1p** her zaman alan ve döndüren bir **çift**.

Varsa *x* doğal sayı, bu işlev çarpımını logaritmasını döndürür (*x* - 1).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
