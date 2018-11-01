---
title: __outword
ms.date: 11/04/2016
f1_keywords:
- __outword
helpviewer_keywords:
- __outword intrinsic
- out instruction
ms.assetid: 995f8834-0f50-4b4f-a7a2-af0e7c371cda
ms.openlocfilehash: e5a6274fef9d9e9e4a168b9849ab0021c32a4716
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626193"
---
# <a name="outword"></a>__outword

**Microsoft'a özgü**

Oluşturur `out` sağlayan sözcüğü gönderir yönergesinin `Data` çıkış tarafından belirtilen g/ç bağlantı noktasına `Port`.

## <a name="syntax"></a>Sözdizimi

```
void __outword( 
   unsigned short Port, 
   unsigned short Data 
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı noktası*<br/>
[in] Veri göndermek için bağlantı noktası.

*Veri*<br/>
[in] Gönderilecek veri.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__outword`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)