---
description: 'Hakkında daha fazla bilgi edinin: __outbytestring'
title: __outbytestring
ms.date: 09/02/2019
f1_keywords:
- __outbytestring
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
ms.openlocfilehash: feadb0b4275e370de88bfc04c8a10f90c41d0844
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222430"
---
# <a name="__outbytestring"></a>__outbytestring

**Microsoft'a Özgü**

`rep outsb` `Count` Tarafından işaret edilen ilk bayt sayısını tarafından `Buffer` belirtilen bağlantı noktasına gönderen yönergeyi üretir `Port` .

## <a name="syntax"></a>Sözdizimi

```C
void __outbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parametreler

*Bağ*\
'ndaki Verilerin gönderileceği bağlantı noktası.

*Arabelleğin*\
'ndaki Belirtilen bağlantı noktasını göndermek için veriler.

*Biriktirme*\
'ndaki Gönderilecek verilerin bayt sayısı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__outbytestring`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
