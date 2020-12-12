---
description: 'Hakkında daha fazla bilgi edinin: __outword'
title: __outword
ms.date: 09/02/2019
f1_keywords:
- __outword
helpviewer_keywords:
- __outword intrinsic
- out instruction
ms.assetid: 995f8834-0f50-4b4f-a7a2-af0e7c371cda
ms.openlocfilehash: 07136a5ae293f7e23a1cf6b0baa2b3a0f0cc54d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257582"
---
# <a name="__outword"></a>__outword

**Microsoft'a Özgü**

`out`Word *verilerini* *bağlantı noktası* tarafından belirtilen g/ç bağlantı noktasına gönderen yönergeyi oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
void __outword(
   unsigned short Port,
   unsigned short Data
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Verilerin gönderileceği bağlantı noktası.

*Verileri*\
'ndaki Gönderilecek veriler.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__outword`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
