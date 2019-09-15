---
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
ms.openlocfilehash: b2e3566eb96174d0f0ccd6beb401824cc052c995
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941243"
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
Geçerli kayan nokta ortam değerlerini içeren bir **fenv_t** nesnesi işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Kayan nokta ortamı *penv*'de başarıyla depolanıyorsa 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fegetenv** işlevi, geçerli kayan nokta ortamını *penv*tarafından işaret edilen nesnede depolar. Kayan nokta ortamı, kayan nokta hesaplamalarını etkileyen durum bayrakları ve denetim modları kümesidir. Bu, kayan nokta özel durumları için yuvarlama yönü modunu ve durum bayraklarını içerir.  *Penv* geçerli bir **fenv_t** nesnesine işaret içermiyorsa, sonraki davranış tanımsızdır.

Bu işlevi kullanmak için, çağrıdan önce `#pragma fenv_access(on)` yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir. Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv. h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
