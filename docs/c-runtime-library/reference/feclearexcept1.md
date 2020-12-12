---
description: 'Hakkında daha fazla bilgi edinin: bahselearexcept'
title: feclearexcept1
ms.date: 04/05/2018
api_name:
- feclearexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- feclearexcept
- fenv/feclearexcept
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
ms.openlocfilehash: 09eb34ddb781a40418152ec8cc6893074c58a617
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322595"
---
# <a name="feclearexcept"></a>feclearexcept

Bağımsız değişken tarafından belirtilen kayan nokta özel durum bayraklarını temizlemeye çalışır.

## <a name="syntax"></a>Sözdizimi

```C
int feclearexcept(
   int excepts
);
```

### <a name="parameters"></a>Parametreler

*hariç tutulan*<br/>
Temizlenecek özel durum bayrakları.

## <a name="return-value"></a>Dönüş Değeri

, *Hariç tutulan* bir sıfır ise veya belirtilen tüm özel durumlar başarıyla silinirse sıfır döndürür. Aksi takdirde, sıfır dışında bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

Söz konusu işlev, **hariç** *tutulan* tarafından belirtilen kayan nokta özel durum bayraklarını temizlemeye çalışır. İşlevi, fenv. h içinde tanımlanan bu özel durum makrolarını destekler:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|Daha önceki bir kayan nokta işleminde singularor veya direk hatası oluştu; sonsuz değer oluşturuldu.|
|FE_INEXACT|İşlev, önceki bir kayan nokta işleminin saklı sonucunu yuvarlamak üzere zorlandı.|
|FE_INVALID|Önceki kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Bir Aralık hatası oluştu; daha önceki bir kayan nokta işlem sonucu gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Daha önceki bir kayan nokta işlem sonucu tam duyarlıkta gösterilemeyecek kadar küçük; bir denormal değeri oluşturuldu.|
|FE_ALL_EXCEPT|Desteklenen tüm kayan nokta özel durumlarının bit düzeyinde veya dışında.|

*Hariç tutulan* bağımsız değişken sıfır ya da desteklenen bir veya daha fazla özel durum makrosunu veya BIT düzeyinde ya da daha fazlasını içerebilir. Diğer bağımsız değişken değerinin sonucu tanımlı değil.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**feclearexcept**|\<fenv.h>|\<cfenv>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
