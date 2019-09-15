---
title: cacos, cacosf, cacosl
ms.date: 11/04/2016
api_name:
- cacos
- cacosf
- cacosl
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
- cacos
- cacosf
- cacosl
- complex/cacos
- complex/cacosf
- complex/cacosl
helpviewer_keywords:
- cacos function
- cacosf function
- cacosl function
ms.assetid: 78118c00-0a07-49c1-8a13-4bf19ce3aea8
ms.openlocfilehash: 5b0751703b9b9cdcdb50e265a6b5d3c929d89ae1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939397"
---
# <a name="cacos-cacosf-cacosl"></a>cacos, cacosf, cacosl

Bir karmaşık sayının arkkosinüsünü alır, dal, gerçek eksen üzerinde [-1, + 1] aralığının dışına keser.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex cacos( _Dcomplex z );
_Fcomplex cacosf( _Fcomplex z );
_Lcomplex cacosl( _Lcomplex z );
```

```cpp
_Fcomplex cacos( _Fcomplex z );  // C++ only
_Lcomplex cacos( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parametreler

*z*<br/>
Radyan cinsinden bir açıyı temsil eden karmaşık bir sayı.

## <a name="return-value"></a>Dönüş Değeri

*Z*'nin radyan cinsinden arkkosinüsü. Sonuç, sanal eksen ve içinde [0, π] aralığında gerçek eksen üzerinde sınırsız olarak yapılır. *Z* , [-1, + 1] aralığının dışındaysa bir etki alanı hatası meydana gelir.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **_Fcomplex** ve **_lcomplex** değerlerini alıp döndüren **cacos** 'ın aşırı yüklerini çağırabilirsiniz. C programında **cacos** her zaman **_dcomplex** değeri alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++üst bilgi|
|-------------|--------------|------------------|
|**cacos**, **cacosf**, **cacosl**|\<karmaşık. h >|\<ccomplex >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh, ctanhf, ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
