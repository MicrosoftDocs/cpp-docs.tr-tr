---
title: __readdr
ms.date: 11/04/2016
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: 9d265fe75abaa7ad3cfd508613766cc3b600ee14
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025672"
---
# <a name="readdr"></a>__readdr

Belirtilen hata ayıklama kaydı değerini okur.

## <a name="syntax"></a>Sözdizimi

```
unsigned         __readdr(unsigned int DebugRegister);
unsigned __int64 __readdr(unsigned int DebugRegister);
```

#### <a name="parameters"></a>Parametreler

*DebugRegister*<br/>
[in] Hata ayıklama tanımlayan 0 ile 7 arasında bir sabit kaydedin.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen hata ayıklama kayıt değeri.

## <a name="remarks"></a>Açıklamalar

Bu iç öğeler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç öğe olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__readdr`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__readeflags](../intrinsics/readeflags.md)