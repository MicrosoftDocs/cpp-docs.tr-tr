---
title: __outbytestring
ms.date: 09/02/2019
f1_keywords:
- __outbytestring
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
ms.openlocfilehash: 31caf17db5d56efccd6b30200994b1080356b4c1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217177"
---
# <a name="__outbytestring"></a>__outbytestring

**Microsoft 'a özgü**

`Count` `Port` `rep outsb` Tarafından işaretedilenilkbaytsayısınıtarafındanbelirtilenbağlantınoktasınagönderenyönergeyiüretir.`Buffer`

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

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
