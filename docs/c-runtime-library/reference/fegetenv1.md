---
title: fegetenv | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3569b015784f41fae4a4a91b6a32fe08dd57284
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="fegetenv"></a>fegetenv

Belirtilen nesne geçerli kayan nokta ortamı depolar.

## <a name="syntax"></a>Sözdizimi

```C
int fegetenv(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parametreler

*penv*<br/>
İşaretçi bir **fenv_t** geçerli kayan nokta ortam değerleri içeren nesne.

## <a name="return-value"></a>Dönüş Değeri

Kayan nokta ortam içinde başarıyla depolanmışsa 0 döndürür *penv*. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fegetenv** işlevi gösterdiği nesne geçerli kayan nokta ortamı depolar *penv*. Kayan nokta ortamıdır durumu bayrakları ve kayan nokta hesaplamaları etkileyecek denetim modları kümesi. Bu yuvarlama yönünü mod ve durum bayrakları kayan nokta özel durumları içerir.  Varsa *penv* geçerli bir göstermiyor **fenv_t** nesnesi, sonraki davranış tanımlanmadı.

Bu işlevi kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
