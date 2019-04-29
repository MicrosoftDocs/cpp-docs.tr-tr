---
title: feholdexcept
ms.date: 04/05/2018
apiname:
- feholdexcept
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
- feholdexcept
- fenv/feholdexcept
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
ms.openlocfilehash: 26097398b9f9d498ab4c56690dc9c6cbb950bafb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334391"
---
# <a name="feholdexcept"></a>feholdexcept

Belirtilen nesne geçerli bir kayan nokta ortamı kaydeder, kayan nokta durumu bayrakları temizler ve mümkünse, kayan nokta ortamı stop moduna geçirir.

## <a name="syntax"></a>Sözdizimi

```C
int feholdexcept(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
İşaretçi bir **fenv_t** kayan nokta ortamın bir kopyasını içeren nesne.

## <a name="return-value"></a>Dönüş Değeri

İşlev başarıyla stop kayan nokta özel durum işleme üzerinde açabilirsiniz, ve yalnızca, döndürür sıfır.

## <a name="remarks"></a>Açıklamalar

**Feholdexcept** işlevi geçerli kayan nokta ortamda durumunu depolamak için kullanılan **fenv_t** nesne tarafından işaret edilen *penv*ve ortamı ayarlayın kayan nokta özel durumlarını üzerinde yürütme kesme değil. Bu, stop modu olarak bilinir.  Bu mod kullanarak ortamı geri yüklenene kadar devam [fesetenv](fesetenv1.md) veya [feupdateenv](feupdateenv.md).

Bir veya daha fazla kayan nokta özel durumlarını arayandan gizlemek için gereken bir alt yordam başlangıcında, bu işlevi kullanabilirsiniz. Bir özel durum raporu için sadece istenmeyen özel durumları kullanarak temizleyebilir [feclearexcept,](feclearexcept1.md) ve ardından stop modunu çağrısıyla sonlandırmak **feupdateenv**.

Bu işlevi kullanmak için erişim kullanarak engelleyebilir kayan nokta iyileştirmelerinin kapatmanız gerekir `#pragma fenv_access(on)` çağrıdan önceki yönerge. Daha fazla bilgi için [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**feholdexcept**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[fesetenv](fesetenv1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
