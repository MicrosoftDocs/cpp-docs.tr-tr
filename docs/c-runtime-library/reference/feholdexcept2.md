---
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
ms.openlocfilehash: bd55a4ed627d731f7246d589d4b74b4173e31d4e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941197"
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
Kayan nokta ortamının bir kopyasını içeren bir **fenv_t** nesnesi işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Yalnızca işlev, durdurma olmayan kayan nokta özel durum işlemesini başarıyla açabiliyor ise sıfır değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**Feholdexcept** işlevi, geçerli kayan nokta ortamının durumunu *penv*tarafından işaret edilen **fenv_t** nesnesi içinde depolamak ve ortamı kayan nokta özel durumları üzerinde kesintiye uğramayan yürütme olarak ayarlamak için kullanılır. Bu, durdurma olmayan mod olarak bilinir.  Bu mod, ortam [fesetenv](fesetenv1.md) veya [feupdateenv](feupdateenv.md)kullanılarak geri yüklenene kadar devam eder.

Bu işlevi, çağıranın bir veya daha fazla kayan nokta özel durumunu gizlemek için gereken bir altyordam başlangıcında kullanabilirsiniz. Bir özel durumu raporlamak için, istenmeyen özel durumları yalnızca [öğreneöğreni](feclearexcept1.md) kullanarak temizleyebilir ve sonra da durmayan modunu **feupdateenv**çağrısıyla sonlandırmanız yeterlidir.

Bu işlevi kullanmak için, çağrıdan önce `#pragma fenv_access(on)` yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir. Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**feholdexcept**|\<fenv. h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[fesetenv](fesetenv1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
