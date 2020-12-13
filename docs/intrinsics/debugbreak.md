---
description: 'Hakkında daha fazla bilgi edinin: __debugbreak'
title: __debugbreak
ms.date: 09/02/2019
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: 83a670d9fa9c1f6b41c1c405c59af71c7aa0c8a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337115"
---
# <a name="__debugbreak"></a>__debugbreak

**Microsoft'a Özgü**

Kodunuzda bir kesme noktasına neden olur. Bu, kullanıcıdan hata ayıklayıcıyı çalıştırması istenecektir.

## <a name="syntax"></a>Syntax

```C
void __debugbreak();
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`__debugbreak`|x86, x64, ARM, ARM64|\<intrin.h>|

## <a name="remarks"></a>Açıklamalar

`__debugbreak` [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)'e benzer derleyici iç noktası, bir kesme noktasına neden olan taşınabilir bir Win32 yoludur.

> [!NOTE]
> **/Clr** ile derlerken, içeren BIR işlev `__debugbreak` MSIL 'e derlenir. `asm int 3` bir işlevin yerel olarak derlenmesine neden olur. Daha fazla bilgi için bkz. [__asm](../assembler/inline/asm.md).

Örneğin:

```C
main() {
   __debugbreak();
}
```

Şuna benzer:

```C
main() {
   __asm {
      int 3
   }
}
```

bir x86 bilgisayarda.

ARM64 üzerinde, `__debugbreak` iç öğe yönergeyle derlenir `brk #0xF000` .

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
