---
title: fegetround, fesetround
ms.date: 04/05/2018
apiname:
- fegetround
- fesetround
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetround
- fesetround
- fenv/fegetround
- fenv/fesetround
helpviewer_keywords:
- fegetround function
- fesetround function
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
ms.openlocfilehash: 061f0c9563d284396e85c6de70a2fe0911218eb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666810"
---
# <a name="fegetround-fesetround"></a>fegetround, fesetround

Alır veya ayarlar geçerli kayan nokta yuvarlama modu.

## <a name="syntax"></a>Sözdizimi

```C
int fegetround(void);

int fesetround(
   int round_mode
);
```

### <a name="parameters"></a>Parametreler

*round_mode*<br/>
, Kayan nokta yuvarlama makroları biri olarak ayarlamak için yuvarlama modu. Değeri kayan nokta yuvarlama makroları birine eşit değilse, yuvarlama modu değiştirilmez.

## <a name="return-value"></a>Dönüş Değeri

Başarı durumunda, **fegetround** yuvarlama modu makrosu değerleri yuvarlama kayan nokta döndürür. Geçerli yuvarlama modu belirlenemiyorsa negatif bir değer döndürür.

Başarı durumunda, **fesetround** 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürülür.

## <a name="remarks"></a>Açıklamalar

Kayan nokta işlemleri birkaç yuvarlama modu birini kullanabilirsiniz. Bu sonuçları depolandığında doğru kayan nokta işlemlerinin sonuçlarını yuvarlanır hangi yönde denetler. Bunlar adlarını ve kayan nokta yuvarlama makroları davranışlarını tanımlanan \<fenv.h >:

|Makrosu|Açıklama|
|-----------|-----------------|
|FE_DOWNWARD|Negatif sonsuz doğru yuvarlar.|
|FE_TONEAREST|Yuvarlak doğru en yakın.|
|FE_TOWARDZERO|Sıfıra doğru yuvarlar.|
|FE_UPWARD|Pozitif sonsuz doğru yuvarlar.|

Varsayılan FE_TONEAREST sonuçları midway doğru en yakın bir bile (0) en az önemli bit değeriyle temsil edilebilir değerler arasında yuvarlanacak davranışıdır.

Geçerli yuvarlama modu işlemlerini etkiler:

- Dönüştürmeleri dize.

- Sabit ifadeler dışında kayan nokta aritmetik işleçler sonuçları.

- İşlevler, aşağıdakiler gibi yuvarlama Kitaplığı **azdır** ve **nearbyint**.

- Standart kitaplık matematik işlevleri dönüş değerleri.

Geçerli yuvarlama modu bu işlemleri etkilemez:

- **Trunc**, **ceil**, **kat**, ve **lround** kitaplık işlevleri.

- Kayan nokta tamsayı örtük yayınları ve dönüştürme, her zaman sıfıra doğru yuvarlar.

- Her zaman en yakın değere yuvarlar sabit ifadeler, kayan nokta aritmetik işleçler sonuçları.

Bu işlevleri kullanmak için erişim kullanarak engelleyebilir kayan nokta iyileştirmelerinin kapatmanız gerekir `#pragma fenv_access(on)` çağrıdan önceki yönerge. Daha fazla bilgi için [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**fegetround**, **fesetround**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint, rintf, rintl](rint-rintf-rintl.md)<br/>
[lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
