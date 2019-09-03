---
title: __writedr
ms.date: 09/02/2019
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: 715ef7432d506c2758c9c3da913e9c0ebb24e13f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219230"
---
# <a name="__writedr"></a>__writedr

Belirtilen değeri belirtilen hata ayıklama kaydına yazar.

## <a name="syntax"></a>Sözdizimi

```C
void __writedr(unsigned DebugRegister, unsigned DebugValue); /* x86 */
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue); /* x64 */
```

### <a name="parameters"></a>Parametreler

*DebugRegister*\
'ndaki Hata ayıklama kaydını tanımlayan 0 ile 7 arasında bir sayı.

*DebugValue*\
'ndaki Hata ayıklama kaydına yazılacak bir değer.

## <a name="remarks"></a>Açıklamalar

Bu iç bilgiler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__writedr`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__readdr](../intrinsics/readdr.md)
