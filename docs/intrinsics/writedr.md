---
title: __writedr
ms.date: 09/02/2019
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: 473e7223e9974d0125e772c152ea85ae90b97342
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858067"
---
# <a name="__writedr"></a>__writedr

**Microsoft 'a özgü**

Belirtilen değeri belirtilen hata ayıklama kaydına yazar.

## <a name="syntax"></a>Sözdizimi

```C
void __writedr(unsigned DebugRegister, unsigned DebugValue); /* x86 */
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue); /* x64 */
```

### <a name="parameters"></a>Parametreler

*Debugregister*\
'ndaki Hata ayıklama kaydını tanımlayan 0 ile 7 arasında bir sayı.

*Debugvalue*\
'ndaki Hata ayıklama kaydına yazılacak bir değer.

## <a name="remarks"></a>Açıklamalar

Bu iç bilgiler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__writedr`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç](../intrinsics/compiler-intrinsics.md) bilgileri\
[__readdr](../intrinsics/readdr.md)
