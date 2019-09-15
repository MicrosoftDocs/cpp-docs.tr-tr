---
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
ms.openlocfilehash: 8f40cab42e4a89b1fc5a100587b11b0e2aeeb55c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940984"
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
[Fegetenv](fegetenv1.md) veya [feholdexcept](feholdexcept2.md)çağrısıyla ayarlanmış bir kayan nokta ortamı içeren bir **fenv_t** nesnesine yönelik işaretçi. FE_DFL_ENV makrosunu kullanarak varsayılan başlangıç kayan nokta ortamını de belirtebilirsiniz.

## <a name="return-value"></a>Dönüş Değeri

Tüm eylemler başarıyla tamamlanırsa 0 döndürür. Aksi takdirde, sıfır dışında bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Feupdateenv** işlevi birden çok eylem gerçekleştirir. İlk olarak, geçerli yükseltilen kayan nokta özel durum bayraklarını otomatik depolamada depolar. Ardından, geçerli kayan nokta ortamını, *penv*tarafından işaret edilen **fenv_t** nesnesinde depolanan değerden ayarlar. *Penv* **FE_DFL_ENV** değilse veya geçerli bir **fenv_t** nesnesine işaret içermiyorsa, sonraki davranış tanımsızdır. Son olarak, **feupdateenv** yerel olarak depolanan kayan nokta özel durumlarını yükseltir.

Bu işlevi kullanmak için, çağrıdan önce `#pragma fenv_access(on)` yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir. Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**feupdateenv**|\<fenv. h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
