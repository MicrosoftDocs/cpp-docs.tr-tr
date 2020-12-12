---
description: 'Şu konuda daha fazla bilgi edinin: yerel (C++)'
title: Yerel (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: 7fa1366b78576224f8fcc0d91392fe1fc6cb8af9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327517"
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

**Yerel** kullanım hakkında bir örnek için bkz. [call_as](call-as.md) .

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**Interface**, Interface yöntemi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|`dispinterface`|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[call_as](call-as.md)
