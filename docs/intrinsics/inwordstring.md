---
description: 'Hakkında daha fazla bilgi edinin: __inwordstring'
title: __inwordstring
ms.date: 09/02/2019
f1_keywords:
- __inwordstring
- __inwordstring_cpp
helpviewer_keywords:
- __inwordstring intrinsic
- rep insw instruction
ms.assetid: 6de37939-017a-4740-9e3d-7de78a30daba
ms.openlocfilehash: d65aaedd3fc0fd51ab276abb391ed3c58047ccda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167818"
---
# <a name="__inwordstring"></a>__inwordstring

**Microsoft'a Özgü**

Yönergeleri kullanarak belirtilen bağlantı noktasından verileri okur `rep insw` .

## <a name="syntax"></a>Sözdizimi

```C
void __inwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Okunacak bağlantı noktası.

*Arabelleğin*\
dışı Bağlantı noktasından okunan veriler buraya yazılır.

*Biriktirme*\
'ndaki Okunacak veri sözcüklerinin sayısı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__inwordstring`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
