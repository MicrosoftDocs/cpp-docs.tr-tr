---
title: feupdateenv
ms.date: 04/05/2018
apiname:
- feupdateenv
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
apitype: HeaderDef
f1_keywords:
- feupdateenv
- fenv/feupdateenv
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
ms.openlocfilehash: 6d553d6899f55f5bdfb3ff313e88abfcb56ab4ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605123"
---
# <a name="feupdateenv"></a>feupdateenv

Şu anda yükseltilmiş kayan nokta özel durumlarını kaydeder, kayan nokta belirtilen ortam durumunu geri yükler ve ardından kaydedilen kayan nokta özel durumlarını oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
int feupdateenv(
   const fenv_t* penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
İşaretçi bir **fenv_t** yapılan bir çağrıyla kümesi olarak bir kayan nokta ortamı içeren nesne [fegetenv](fegetenv1.md) veya [feholdexcept](feholdexcept2.md). Varsayılan başlangıç kayan nokta ortam FE_DFL_ENV makrosu kullanarak da belirtebilirsiniz.

## <a name="return-value"></a>Dönüş Değeri

Tüm Eylemler başarıyla tamamlandı, 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Feupdateenv** işlevi, birden fazla eylem gerçekleştirir. İlk olarak, şu anki kayan nokta özel durumu durumu bayrakları otomatik depolama alanında depolar. Ardından, kayan nokta geçerli ortamdan depolanan değere ayarlar **fenv_t** nesne tarafından işaret edilen *penv*. Varsa *penv* değil **FE_DFL_ENV** veya geçerli bir işaret etmiyor **fenv_t** nesnesi, sonraki davranışı tanımsızdır. Son olarak, **feupdateenv** yerel olarak saklanan bir kayan nokta özel durumlarını oluşturur.

Bu işlevi kullanmak için erişim kullanarak engelleyebilir kayan nokta iyileştirmelerinin kapatmanız gerekir `#pragma fenv_access(on)` çağrıdan önceki yönerge. Daha fazla bilgi için [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**feupdateenv**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
