---
description: 'Daha fazla bilgi edinin: fegetenv'
title: fegetenv
ms.date: 04/05/2018
api_name:
- fetegenv
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
- fegetenv
- fenv/fegetenv
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
ms.openlocfilehash: f4d6ab3de440d2d8d7e145111339577f04699f8b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322582"
---
# <a name="fegetenv"></a>fegetenv

Geçerli kayan nokta ortamını belirtilen nesnede depolar.

## <a name="syntax"></a>Sözdizimi

```C
int fegetenv(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
Geçerli kayan nokta ortamı değerlerini içeren **fenv_t** nesnesine yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Kayan nokta ortamı *penv*'de başarıyla depolanıyorsa 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fegetenv** işlevi, geçerli kayan nokta ortamını *penv* tarafından işaret edilen nesnede depolar. Kayan nokta ortamı, kayan nokta hesaplamalarını etkileyen durum bayrakları ve denetim modları kümesidir. Bu, kayan nokta özel durumları için yuvarlama yönü modunu ve durum bayraklarını içerir.  *Penv* geçerli bir **fenv_t** nesnesine işaret içermiyorsa, sonraki davranış tanımsızdır.

Bu işlevi kullanmak için, çağrıdan önce yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir `#pragma fenv_access(on)` . Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h>|\<cfenv>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
