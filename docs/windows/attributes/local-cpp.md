---
title: Yerel (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: dea62653478e451af00fa47b72984f3b580aadc0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834095"
---
# <a name="local-c"></a>yerel (C++)

Arabirim üstbilgisinde kullanıldığında, MıDL derleyicisini üst bilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saplamalar üretilmeden önce bir yerel yordam belirler.

## <a name="syntax"></a>Syntax

```cpp
[local]
```

## <a name="remarks"></a>Açıklamalar

**Yerel** C++ özniteliği, [Yerel](/windows/win32/Midl/local) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Yerel**kullanım hakkında bir örnek için bkz. [call_as](call-as.md) .

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**Interface**, Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|`dispinterface`|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[call_as](call-as.md)
