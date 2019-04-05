---
title: __writedr
ms.date: 11/04/2016
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: c495e8c80029680512358198ca8fb0ce6e65414d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022487"
---
# <a name="writedr"></a>__writedr

Belirtilen değer, belirtilen hata ayıklama kaydı için yazar.

## <a name="syntax"></a>Sözdizimi

```
void __writedr(unsigned DebugRegister, unsigned DebugValue);
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);
```

#### <a name="parameters"></a>Parametreler

*DebugRegister*<br/>
[in] Hata ayıklama tanımlayan 0 ile 7 arasında bir sayı kaydedin.

*DebugValue*<br/>
[in] Yazma hata ayıklama için bir değer kaydedin.

## <a name="remarks"></a>Açıklamalar

Bu iç öğeler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç öğe olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__writedr`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__readdr](../intrinsics/readdr.md)