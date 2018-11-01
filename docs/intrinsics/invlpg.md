---
title: __invlpg
ms.date: 11/04/2016
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: 0ff46aa15fbb8728ce02255209a32f01a168609b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629391"
---
# <a name="invlpg"></a>__invlpg

**Microsoft'a özgü**

X86 oluşturur `invlpg` işaret ettiği bellek ile ilişkili sayfası için çeviri arabelleğinde arabelleği (TLB) geçersiz kılmaz yönerge `Address`.

## <a name="syntax"></a>Sözdizimi

```
void __invlpg(
   void* Address
);
```

#### <a name="parameters"></a>Parametreler

*Adresi*<br/>
[in] Bir 64-bit adresi.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__invlpg`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

İç `__invlpg` ayrıcalıklı yönerge yayar ve yalnızca 0 ayrıcalık düzeyi (CPL) ile çekirdek modunda kullanılabilir.

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)