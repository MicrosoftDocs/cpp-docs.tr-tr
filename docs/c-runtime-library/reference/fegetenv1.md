---
title: fegetenv
ms.date: 04/05/2018
apiname:
- fetegenv
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
- fegetenv
- fenv/fegetenv
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
ms.openlocfilehash: d3985e4dd2b3944bcdddb79605887def7ba15473
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334417"
---
# <a name="fegetenv"></a>fegetenv

Geçerli bir kayan nokta ortamı belirtilen nesnede depolar.

## <a name="syntax"></a>Sözdizimi

```C
int fegetenv(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
İşaretçi bir **fenv_t** geçerli ortam kayan nokta değerleri içeren nesne.

## <a name="return-value"></a>Dönüş Değeri

Kayan nokta ortam içinde başarıyla depolanmışsa 0 döndürür *penv*. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fegetenv** işlevi tarafından işaret edilen nesnenin geçerli bir kayan nokta ortamı depolar *penv*. Kayan nokta ortamıdır durumu bayrakları ve kayan nokta hesaplamalarının etkileyen Denetim modu kümesi. Bu yuvarlama yönünü mod ve durum bayrakları için kayan nokta özel durumlarını içerir.  Varsa *penv* geçerli bir işaret etmiyor **fenv_t** nesnesi, sonraki davranışı tanımsızdır.

Bu işlevi kullanmak için erişim kullanarak engelleyebilir kayan nokta iyileştirmelerinin kapatmanız gerekir `#pragma fenv_access(on)` çağrıdan önceki yönerge. Daha fazla bilgi için [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
