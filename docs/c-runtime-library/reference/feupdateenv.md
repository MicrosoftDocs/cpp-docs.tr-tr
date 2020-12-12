---
description: 'Daha fazla bilgi edinin: feupdateenv'
title: feupdateenv
ms.date: 04/05/2018
api_name:
- feupdateenv
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
api_type:
- HeaderDef
f1_keywords:
- feupdateenv
- fenv/feupdateenv
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
ms.openlocfilehash: 4e3fe47c6a03138f2bc82679eb5fc8e938678a17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289341"
---
# <a name="feupdateenv"></a>feupdateenv

Şu anda oluşturulan kayan nokta özel durumlarını kaydeder, belirtilen kayan nokta ortamı durumunu geri yükler ve ardından kaydedilen kayan nokta özel durumlarını yükseltir.

## <a name="syntax"></a>Sözdizimi

```C
int feupdateenv(
   const fenv_t* penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
[Fegetenv](fegetenv1.md) veya [feholdexcept](feholdexcept2.md)çağrısıyla ayarlanmış bir kayan nokta ortamı içeren **fenv_t** nesnesine yönelik işaretçi. Ayrıca, FE_DFL_ENV makrosunu kullanarak varsayılan başlangıç kayan nokta ortamını de belirtebilirsiniz.

## <a name="return-value"></a>Dönüş Değeri

Tüm eylemler başarıyla tamamlanırsa 0 döndürür. Aksi takdirde, sıfır dışında bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Feupdateenv** işlevi birden çok eylem gerçekleştirir. İlk olarak, geçerli yükseltilen kayan nokta özel durum bayraklarını otomatik depolamada depolar. Ardından, geçerli kayan nokta ortamını, *penv* tarafından işaret edilen **fenv_t** nesnesinde depolanan değerden ayarlar. *Penv* **FE_DFL_ENV** yoksa veya geçerli bir **fenv_t** nesnesine işaret etmez, sonraki davranış tanımsızdır. Son olarak, **feupdateenv** yerel olarak depolanan kayan nokta özel durumlarını yükseltir.

Bu işlevi kullanmak için, çağrıdan önce yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir `#pragma fenv_access(on)` . Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**feupdateenv**|\<fenv.h>|\<cfenv>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
