---
title: log1p, log1pf, log1pl2
ms.date: 4/2/2020
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
ms.openlocfilehash: 21bba72b204f975b806e43cdc6d36d8efa173b9b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911424"
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

*sayı*<br/>
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

*X* 0 yakınında **log1p** işlevleri kullanmaktan `log(x + 1)` daha doğru olabilir.

C++ aşırı yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren **log1p** aşırı yüklerini çağırabilirsiniz. C programında, **log1p** her zaman bir **Double**alır ve döndürür.

*X* doğal bir sayı ise, bu işlev (*x* -1) çarpınımını logaritmasını döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<Math. h>|\<cmath>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
