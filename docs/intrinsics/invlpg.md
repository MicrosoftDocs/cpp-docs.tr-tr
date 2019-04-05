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
ms.openlocfilehash: b4f941baae9f03ed288a99d59e2b06262962e339
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023327"
---
# <a name="invlpg"></a>__invlpg

**Microsoft'a Özgü**

X86 oluşturur `invlpg` işaret ettiği bellek ile ilişkili sayfası için çeviri arabelleğinde arabelleği (TLB) geçersiz kılmaz yönerge `Address`.

## <a name="syntax"></a>Sözdizimi

```
void __invlpg(
   void* Address
);
```

#### <a name="parameters"></a>Parametreler

*Adres*<br/>
[in] Bir 64-bit adresi.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__invlpg`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

İç `__invlpg` ayrıcalıklı yönerge yayar ve yalnızca 0 ayrıcalık düzeyi (CPL) ile çekirdek modunda kullanılabilir.

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)