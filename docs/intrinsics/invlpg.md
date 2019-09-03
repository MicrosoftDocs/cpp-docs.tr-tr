---
title: __invlpg
ms.date: 09/02/2019
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: ba8bd81498f805992336b0dc4163fe18fa157a2c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221889"
---
# <a name="__invlpg"></a>__invlpg

**Microsoft 'a özgü**

*Adrese*göre işaret `invlpg` edilen bellekle ilişkili sayfa için çeviri arabelleği arabelleğini (tlb) geçersiz kılan x86 yönergesini üretir.

## <a name="syntax"></a>Sözdizimi

```C
void __invlpg(
   void* Address
);
```

### <a name="parameters"></a>Parametreler

*Adrestir*\
'ndaki 64 bitlik bir adres.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__invlpg`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İç `__invlpg` , ayrıcalıklı bir yönerge yayar ve yalnızca bir ayrıcalık düzeyi (cpl) 0 olan çekirdek modunda kullanılabilir.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
