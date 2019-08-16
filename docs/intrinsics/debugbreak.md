---
title: __debugbreak
ms.date: 11/04/2016
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: ed75b94e8bf0aca9369c56f23e8ff00ea6953642
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509505"
---
# <a name="__debugbreak"></a>__debugbreak

**Microsoft 'a özgü**

Kodunuzda bir kesme noktasına neden olur. Bu, kullanıcıdan hata ayıklayıcıyı çalıştırması istenecektir.

## <a name="syntax"></a>Sözdizimi

```
void __debugbreak();
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`__debugbreak`|x86, x64, ARM, ARM64|\<Intrin. h >|

## <a name="remarks"></a>Açıklamalar

[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)'e benzer derleyiciiçnoktası,birkesmenoktasınanedenolantaşınabilirbirWin32yoludur.`__debugbreak`

> [!NOTE]
>  **/Clr**ile derlerken, içeren `__debugbreak` bir işlev MSIL 'e derlenir. `asm int 3`bir işlevin yerel olarak derlenmesine neden olur. Daha fazla bilgi için bkz. [__asm](../assembler/inline/asm.md).

Örneğin:

```
main() {
   __debugbreak();
}
```

Şuna benzer:

```
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

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
