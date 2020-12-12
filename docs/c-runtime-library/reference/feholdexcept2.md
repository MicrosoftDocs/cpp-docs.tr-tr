---
description: 'Hakkında daha fazla bilgi edinin: feholdexcept'
title: feholdexcept
ms.date: 04/05/2018
api_name:
- feholdexcept
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
- feholdexcept
- fenv/feholdexcept
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
ms.openlocfilehash: 89ccf9bedb05752202152f6bd862b11b2f765322
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322530"
---
# <a name="feholdexcept"></a>feholdexcept

Geçerli kayan nokta ortamını belirtilen nesneye kaydeder, kayan nokta durum bayraklarını temizler ve mümkünse kayan nokta ortamını durdurma olmayan moda koyar.

## <a name="syntax"></a>Sözdizimi

```C
int feholdexcept(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
Kayan nokta ortamının bir kopyasını içeren **fenv_t** nesnesine yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Yalnızca işlev, durdurma olmayan kayan nokta özel durum işlemesini başarıyla açabiliyor ise sıfır değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**Feholdexcept** işlevi, geçerli kayan nokta ortamının durumunu *penv* tarafından işaret edilen **fenv_t** nesnesi içinde depolamak ve ortamı kayan nokta özel durumları üzerinde kesintiye uğramayan yürütme olarak ayarlamak için kullanılır. Bu, durdurma olmayan mod olarak bilinir.  Bu mod, ortam [fesetenv](fesetenv1.md) veya [feupdateenv](feupdateenv.md)kullanılarak geri yüklenene kadar devam eder.

Bu işlevi, çağıranın bir veya daha fazla kayan nokta özel durumunu gizlemek için gereken bir altyordam başlangıcında kullanabilirsiniz. Bir özel durumu raporlamak için, istenmeyen özel durumları yalnızca [öğreneöğreni](feclearexcept1.md) kullanarak temizleyebilir ve sonra da durmayan modunu **feupdateenv** çağrısıyla sonlandırmanız yeterlidir.

Bu işlevi kullanmak için, çağrıdan önce yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir `#pragma fenv_access(on)` . Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**feholdexcept**|\<fenv.h>|\<cfenv>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[fesetenv](fesetenv1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
