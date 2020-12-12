---
description: 'Hakkında daha fazla bilgi edinin: __outdword'
title: __outdword
ms.date: 09/02/2019
f1_keywords:
- __outdword
helpviewer_keywords:
- out instruction
- outdword instruction
- __outdword intrinsic
ms.assetid: ed1e4994-a84b-4759-8bf9-cd48fb073f4d
ms.openlocfilehash: e1d5f79231675ca64a340138ebda24a56e485ab1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222352"
---
# <a name="__outdword"></a>__outdword

**Microsoft'a Özgü**

`out`Bağlantı noktası *bağlantı noktasına* bir doubleword *verisi* gönderme yönergesini üretir.

## <a name="syntax"></a>Sözdizimi

```C
void __outdword(
   unsigned short Port,
   unsigned long Data
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Verilerin gönderileceği bağlantı noktası.

*Verileri*\
'ndaki Gönderilecek doubleword.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__outdword`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
