---
description: 'Hakkında daha fazla bilgi edinin: __invlpg'
title: __invlpg
ms.date: 09/02/2019
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: 16d8f51c8bf36ea94be7b1325ee5bed256c29693
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167909"
---
# <a name="__invlpg"></a>__invlpg

**Microsoft'a Özgü**

`invlpg` *Adrese* göre işaret edilen bellekle ilişkili sayfa için çeviri ARABELLEĞI arabelleğini (tlb) geçersiz kılan x86 yönergesini üretir.

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

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

İç, `__invlpg` ayrıcalıklı bir yönerge yayar ve yalnızca bir ayrıcalık düzeyi (cpl) 0 olan çekirdek modunda kullanılabilir.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
