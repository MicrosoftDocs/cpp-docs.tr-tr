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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b4e077f5b806dbe38ed4a4f4e8eef0259170cb7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341804"
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl

1'in doğal logaritma ve belirtilen değeri hesaplar.

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

*X*<br/>
Kayan nokta bağımsız değişkeni.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa,*(x* + 1) doğal (base-*e*) log'u döndürür.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Girdi|Sonuç|SEH özel durumu|Errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|Denormals|Girişle aynı|ALT Akış||
|±0|Girişle aynı|||
|-1|-inf|DIVBYZERO|Erange|
|< -1|Nan|Geçersiz|Edom|
|-inf|Nan|Geçersiz|Edom|
|±SNaN|Girişle aynı|Geçersiz||
|±QNaN, belirsiz|Girişle aynı|||

x *=* -1 ise **errno** değeri ERANGE olarak ayarlanır. *X* -1'e < **errno** değeri **EDOM** olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**Log1p** işlevleri *x* 0'a `log(x + 1)` yakın olduğunda kullanmaktan daha doğru olabilir.

C++ aşırı yüklemeye izin verdiğinden, **float** ve **uzun** **çift** türleri alan ve döndüren **log1p** aşırı yüklerini arayabilirsiniz. C **programında, log1p** her zaman alır ve bir **çift**döndürür.

*X* doğal bir sayı ise, bu fonksiyon faktöriyel *(x* - 1) logaritma döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgi|C++ üstbilgi|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<math.h>|\<cmath>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
