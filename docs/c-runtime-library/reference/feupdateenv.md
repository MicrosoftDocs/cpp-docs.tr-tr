---
title: feupdateenv | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d88284717aec7a19c936d7ed8d87da96006d7ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397600"
---
# <a name="feupdateenv"></a>feupdateenv

Şu anda yükseltilmiş kayan nokta özel durumları kaydeder, belirtilen kayan nokta ortam durumunu geri yükler ve kaydedilmiş kayan nokta özel durumları oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
int feupdateenv(
   const fenv_t* penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
İşaretçi bir **fenv_t** içeren bir kayan nokta ortamı kümesi olarak yapılan bir çağrı tarafından nesne [fegetenv](fegetenv1.md) veya [feholdexcept](feholdexcept2.md). Varsayılan başlangıç kayan nokta ortamını FE_DFL_ENV makrosu kullanarak da belirtebilirsiniz.

## <a name="return-value"></a>Dönüş Değeri

Tüm eylemleri başarıyla tamamlarsa 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Feupdateenv** işlevi birden fazla eylemleri gerçekleştirir. İlk olarak, şu anki yükseltilmiş kayan nokta özel durumu bayrakları otomatik depolama alanında depolar. Ardından, depolanan değeri geçerli kayan nokta ortamından ayarlar **fenv_t** tarafından için nesne işaret *penv*. Varsa *penv* değil **FE_DFL_ENV** veya geçerli bir göstermiyor **fenv_t** nesnesi, sonraki davranış tanımlanmadı. Son olarak, **feupdateenv** yerel olarak depolanmış kayan nokta özel durumları oluşturur.

Bu işlevi kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**feupdateenv**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
