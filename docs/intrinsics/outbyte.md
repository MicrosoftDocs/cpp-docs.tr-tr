---
title: __outbyte
ms.date: 11/04/2016
f1_keywords:
- __outbyte
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
ms.openlocfilehash: fa17e4859e861a9be46b4ad32b7ad090f6c3dbc6
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326556"
---
# <a name="outbyte"></a>__outbyte

**Microsoft'a özgü**

Oluşturur `out` 1 tarafından belirtilen bayt gönderen yönerge `Data` çıkış tarafından belirtilen g/ç bağlantı noktasına `Port`.

## <a name="syntax"></a>Sözdizimi

```
void __outbyte(
   unsigned short Port,
   unsigned char Data
);
```

#### <a name="parameters"></a>Parametreler

*Bağlantı noktası*<br/>
[in] Veri göndermek için bağlantı noktası.

*Veri*<br/>
[in] Belirtilen bağlantı noktasına gönderilecek bayt.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__outbyte`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)