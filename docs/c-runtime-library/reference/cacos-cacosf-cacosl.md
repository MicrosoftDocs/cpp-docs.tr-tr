---
title: cacos, cacosf, cacosl
ms.date: 11/04/2016
apiname:
- cacos
- cacosf
- cacosl
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
ms.openlocfilehash: 18757ecd30f399ca3d1fdb77e8bff8213a265e74
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348581"
---
# <a name="cacos-cacosf-cacosl"></a>cacos, cacosf, cacosl

Dal keser gerçek ekseni aralığı [-1, + 1] dışında ile karmaşık bir sayının arkkosinüsünü alır.

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
Radyan cinsinden açı temsil eden bir karmaşık sayı.

## <a name="return-value"></a>Dönüş Değeri

Arkkosinüsünü *z*, radyan cinsinden açı. Sonuç ve sanal ekseni sınırsız gerçek ekseni aralığı [0, π]. Bir etki alanı hatası meydana gelir *z* [-1, + 1] aralığının dışında.

## <a name="remarks"></a>Açıklamalar

Çünkü C++ aşırı yüklemesi, sağlayan yüklerini çağırabilirsiniz **cacos** alan ve getiren **_Fcomplex** ve **_Lcomplex** değerleri. C programında **cacos** her zaman alan ve döndüren bir **_Dcomplex** değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üst bilgisi|
|-------------|--------------|------------------|
|**cacos**,               **cacosf**, **cacosl**|\<Complex.h >|\<ccomplex >|

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
