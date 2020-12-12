---
description: 'Hakkında daha fazla bilgi edinin: __outbyte'
title: __outbyte
ms.date: 09/02/2019
f1_keywords:
- __outbyte
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
ms.openlocfilehash: e062d561719cbcdb32ab980efde9eb568defeadb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222482"
---
# <a name="__outbyte"></a>__outbyte

**Microsoft'a Özgü**

`out` `Data` Tarafından belirtilen g/ç bağlantı noktasının belirttiği 1 baytı gönderen yönergeyi üretir `Port` .

## <a name="syntax"></a>Sözdizimi

```C
void __outbyte(
   unsigned short Port,
   unsigned char Data
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Verilerin gönderileceği bağlantı noktası.

*Verileri*\
'ndaki Belirtilen bağlantı noktasını göndermek için kullanılacak bayt.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__outbyte`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
