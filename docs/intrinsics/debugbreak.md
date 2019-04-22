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
ms.openlocfilehash: b52c34014402a235e03c45f82dcd1e5c542e4919
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023106"
---
# <a name="debugbreak"></a>__debugbreak

**Microsoft'a özgü**

Bir kesme noktası, kullanıcı hata ayıklayıcıyı çalıştırmak için burada istenir kodunuzda neden olur.

## <a name="syntax"></a>Sözdizimi

```
void __debugbreak();
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`__debugbreak`|x86, ARM, x64|\<intrin.h >|

## <a name="remarks"></a>Açıklamalar

`__debugbreak` Derleyici iç, benzer [DebugBreak](https://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), bir kesme noktası neden taşınabilir bir Win32 yolu.

> [!NOTE]
>  İle derlerken **/CLR**, işlevi içeren `__debugbreak` MSIL olarak derlenmiş. `asm int 3` bir işlev için yerel olarak derlenmesine neden olur. Daha fazla bilgi için [__asm](../assembler/inline/asm.md).

Örneğin:

```
main() {
   __debugbreak();
}
```

benzer:

```
main() {
   __asm {
      int 3
   }
}
```

x x86 bilgisayar.

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)