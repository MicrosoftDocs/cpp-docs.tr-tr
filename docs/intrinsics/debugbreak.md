---
title: __debugbreak
ms.date: 09/02/2019
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: e4cf2c85818a878417c560ddb5a80f8690e60a93
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217928"
---
# <a name="__debugbreak"></a>__debugbreak

**Microsoft 'a özgü**

Kodunuzda bir kesme noktasına neden olur. Bu, kullanıcıdan hata ayıklayıcıyı çalıştırması istenecektir.

## <a name="syntax"></a>Sözdizimi

```C
void __debugbreak();
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`__debugbreak`|x86, x64, ARM, ARM64|\<Intrin. h >|

## <a name="remarks"></a>Açıklamalar

[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)'e benzer derleyiciiçnoktası,birkesmenoktasınanedenolantaşınabilirbirWin32yoludur.`__debugbreak`

> [!NOTE]
> **/Clr**ile derlerken, içeren `__debugbreak` bir işlev MSIL 'e derlenir. `asm int 3`bir işlevin yerel olarak derlenmesine neden olur. Daha fazla bilgi için bkz. [__asm](../assembler/inline/asm.md).

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

ARM64 üzerinde, `__debugbreak` iç öğe yönergeyle `brk #0xF000`derlenir.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
