---
title: fesetenv
ms.date: 04/05/2018
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
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
ms.openlocfilehash: 8c91bfbb89df964fed0a632d5fb5ebac47ebe948
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334202"
---
# <a name="fesetenv"></a>fesetenv

Geçerli bir kayan nokta ortamını ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int fesetenv(
   const fenv_t *penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
İşaretçi bir **fenv_t** yapılan bir çağrıyla kümesi olarak bir kayan nokta ortamı içeren nesne [fegetenv](fegetenv1.md) veya [feholdexcept](feholdexcept2.md). Varsayılan başlatma kayan nokta ortamını kullanarak da belirtebilirsiniz **FE_DFL_ENV** makrosu.

## <a name="return-value"></a>Dönüş Değeri

Ortam başarılı bir şekilde ayarlarsanız, 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fesetenv** işlevi kayan nokta geçerli ortamdan depolanan değere ayarlar **fenv_t** nesne tarafından işaret edilen *penv*. Kayan nokta ortamıdır durumu bayrakları ve kayan nokta hesaplamalarının etkileyen Denetim modu kümesi. Bu yuvarlama modu ve durumu bayrakları için kayan nokta özel durumlarını içerir.  Varsa *penv* değil **FE_DFL_ENV** veya geçerli bir işaret etmiyor **fenv_t** nesnesi, sonraki davranışı tanımsızdır.

Bu işlev çağrısı bulunan durumu bayrakları özel ayarlar *penv* nesnesi değil Bu özel durumlar oluşturabilir.

Bu işlevi kullanmak için erişim kullanarak engelleyebilir kayan nokta iyileştirmelerinin kapatmanız gerekir `#pragma fenv_access(on)` çağrıdan önceki yönerge. Daha fazla bilgi için [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
