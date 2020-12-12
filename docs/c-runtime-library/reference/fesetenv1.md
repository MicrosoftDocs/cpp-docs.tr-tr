---
description: 'Daha fazla bilgi edinin: fesetenv'
title: fesetenv
ms.date: 04/05/2018
api_name:
- fesetenv
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
- fesetenv
- fenv/fesetenv
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
ms.openlocfilehash: 662634e467eb224af813f60ab4434d4857d21d50
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289445"
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
[Fegetenv](fegetenv1.md) veya [feholdexcept](feholdexcept2.md)çağrısıyla ayarlanmış bir kayan nokta ortamı içeren **fenv_t** nesnesine yönelik işaretçi. Ayrıca, **FE_DFL_ENV** makrosunu kullanarak varsayılan başlangıç kayan nokta ortamını de belirtebilirsiniz.

## <a name="return-value"></a>Dönüş Değeri

Ortam başarıyla ayarlandıysa 0 döndürür. Aksi takdirde, sıfır dışında bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fesetenv** işlevi, *penv* tarafından işaret edilen **fenv_t** nesnesinde depolanan değerden geçerli kayan nokta ortamını ayarlar. Kayan nokta ortamı, kayan nokta hesaplamalarını etkileyen durum bayrakları ve denetim modları kümesidir. Bu, kayan nokta özel durumları için yuvarlama modunu ve durum bayraklarını içerir.  *Penv* **FE_DFL_ENV** yoksa veya geçerli bir **fenv_t** nesnesine işaret etmez, sonraki davranış tanımsızdır.

Bu işleve yapılan bir çağrı, *penv* nesnesinde olan özel durum bayraklarını ayarlar, ancak bu özel durumları oluşturmaz.

Bu işlevi kullanmak için, çağrıdan önce yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir `#pragma fenv_access(on)` . Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h>|\<cfenv>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
