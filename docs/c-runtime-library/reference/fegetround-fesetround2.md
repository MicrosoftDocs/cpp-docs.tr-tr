---
description: 'Daha fazla bilgi edinin: fegetround, fesetround'
title: fegetround, fesetround
ms.date: 04/05/2018
api_name:
- fegetround
- fesetround
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
- fegetround
- fesetround
- fenv/fegetround
- fenv/fesetround
helpviewer_keywords:
- fegetround function
- fesetround function
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
ms.openlocfilehash: f3c112efc1c380ac4ce4495f4365e2a47a1d8fd2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322556"
---
# <a name="fegetround-fesetround"></a>fegetround, fesetround

Geçerli kayan nokta yuvarlama modunu alır veya ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int fegetround(void);

int fesetround(
   int round_mode
);
```

### <a name="parameters"></a>Parametreler

*round_mode*<br/>
Kayan nokta yuvarlama makrolarından biri olarak ayarlanacak yuvarlama modu. Değer, kayan nokta yuvarlama makrolarından birine eşit değilse, yuvarlama modu değiştirilmez.

## <a name="return-value"></a>Dönüş Değeri

Başarı durumunda **fegetround** , kayan nokta yuvarlama makro değerlerinden biri olarak yuvarlama modunu döndürür. Geçerli yuvarlama modu belirlenemiyorsa negatif bir değer döndürür.

Başarı durumunda **fesetround** 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürülür.

## <a name="remarks"></a>Açıklamalar

Kayan nokta işlemleri, birkaç yuvarlama modundan birini kullanabilir. Bu denetim, sonuçlar depolandığında kayan nokta işlemlerinin sonuçlarının yönünü gösteren bu denetimdir. Bunlar, içinde tanımlanan kayan nokta yuvarlama makrolarının adları ve davranışlardır \<fenv.h> :

|Makroya|Açıklama|
|-----------|-----------------|
|FE_DOWNWARD|Negatif sonsuza doğru yuvarla.|
|FE_TONEAREST|En yakın sayıya yaklaşın.|
|FE_TOWARDZERO|Sıfıra yuvarla.|
|FE_UPWARD|Pozitif sonsuza doğru yuvarla.|

FE_TONEAREST varsayılan davranışı, en yakın değere doğru (0) en az önemli bir bit ile gösterilebilir tablo değerleri arasındaki sonuç sayısını yuvarlayamak olur.

Geçerli yuvarlama modu bu işlemleri etkiler:

- Dize dönüştürmeleri.

- Kayan nokta aritmetik işleçlerinin, sabit ifadelerin dışındaki sonuçları.

- Kitaplık yuvarlama işlevleri, örneğin, **rint** ve yeniden bir **tamsayı**.

- Standart Kitaplık matematik işlevlerinden değerleri döndürün.

Geçerli yuvarlama modu bu işlemleri etkilemez:

- **TRUNC**, **CEIL**, **Floor** ve **lround** kitaplığı işlevleri.

- Her zaman sıfır ile yuvarlatılmış olan kayan nokta, tamsayı örtük ve Dönüştürmelere.

- Her zaman en yakın değere yuvarlak olan sabit ifadelerde kayan nokta aritmetik işleçlerinin sonuçları.

Bu işlevleri kullanmak için, çağrıdan önce yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir `#pragma fenv_access(on)` . Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**fegetround**, **fesetround**|\<fenv.h>|\<cfenv>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint, rintf, rintl](rint-rintf-rintl.md)<br/>
[lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
