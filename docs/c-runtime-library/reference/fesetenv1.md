---
title: fesetenv | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fesetenv
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
- fesetenv
- fenv/fesetenv
dev_langs:
- C++
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd761f505c602aad44c5e00df223d4a6c983e851
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397252"
---
# <a name="fesetenv"></a>fesetenv

Geçerli kayan nokta ortamını ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int fesetenv(
   const fenv_t *penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
İşaretçi bir **fenv_t** içeren bir kayan nokta ortamı kümesi olarak yapılan bir çağrı tarafından nesne [fegetenv](fegetenv1.md) veya [feholdexcept](feholdexcept2.md). Kullanarak varsayılan başlangıç kayan nokta ortamını belirtebilirsiniz **FE_DFL_ENV** makrosu.

## <a name="return-value"></a>Dönüş Değeri

Ortam başarılı bir şekilde ayarlarsanız 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fesetenv** işlevi ayarlar depolanan değeriyle geçerli kayan nokta ortamından **fenv_t** tarafından için nesne işaret *penv*. Kayan nokta ortamıdır durumu bayrakları ve kayan nokta hesaplamaları etkileyecek denetim modları kümesi. Bu yuvarlama modu ve kayan nokta özel durumlar için durumu bayrakları içerir.  Varsa *penv* değil **FE_DFL_ENV** veya geçerli bir göstermiyor **fenv_t** nesnesi, sonraki davranış tanımlanmadı.

Bu işlev için bir çağrı bulunan durumu bayrakları özel ayarlar *penv* nesnesi, ancak değil yükselt Bu özel durumlar.

Bu işlevi kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
