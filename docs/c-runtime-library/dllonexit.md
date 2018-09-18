---
title: __dllonexit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __dllonexit
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- __dllonexit
dev_langs:
- C++
helpviewer_keywords:
- __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c2c04f623ba8cac2f3b967007079d41689d2346
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062871"
---
# <a name="dllonexit"></a>__dllonexit

Çıkış zaman çağrılacak bir yordam kaydeder.

## <a name="syntax"></a>Sözdizimi

```
_onexit_t __dllonexit(   _onexit_t func,
   _PVFV **  pbegin,
   _PVFV **  pend
   )
```

#### <a name="parameters"></a>Parametreler

*FUNC*<br/>
Çıkıştan sonra yürütülecek bir işlevi işaretçisi.

*pbegin*<br/>
Başlangıç noktalarına yürütmek için işlevlerin listesi ayırma bir değişken işaretçisi.

*bekleme*<br/>
İşaretçi değişkenine bir listesinin sonuna işaret yürütmek için işlevleri ayırın.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, kullanıcının işlevi işaretçisi. Aksi takdirde, bir **NULL** işaretçi.

## <a name="remarks"></a>Açıklamalar

`__dllonexit` İşlevi alınmak üzere [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) dışında bu işlev tarafından kullanılan genel değişkenler için bu yordamı görünür olmayan işlev. Global değişkenler yerine, bu işlev kullanır `pbegin` ve `pend` parametreleri.

`_onexit` Ve `atexit` DLL'de işlevleri MSVCRT ile bağlı. LIB, kendi atexit/_onexit listesi sürdürmeniz gerekir. Bu yordam böyle DLL tarafından çağrılan çalışan kalır.

`_PVFV` Türü olarak tanımlanmış olan `typedef void (__cdecl *_PVFV)(void)`.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli bir dosya|
|-------------|-------------------|
|__dllonexit|OnExit.c|

## <a name="see-also"></a>Ayrıca Bkz.

[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)