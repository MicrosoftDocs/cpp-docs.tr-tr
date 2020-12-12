---
description: 'Daha fazla bilgi edinin: retval'
title: retval (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 15bfc994d18a9c61c37402aa763ecbfd96cbd768
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114864"
---
# <a name="retval"></a>retval

Üyenin dönüş değerini alan parametreyi belirler.

## <a name="syntax"></a>Syntax

```cpp
[retval]
```

## <a name="remarks"></a>Açıklamalar

**Retval** C++ özniteliği, [retval](/windows/win32/Midl/retval) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

**retval** , bir işlevin bildiriminde yer alan son bağımsız değişkende yer almalıdır.

## <a name="example"></a>Örnek

**Retval** öğesinin örnek kullanımı için [bağlanabilir](bindable.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Arabirim parametresi, arabirim yöntemi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|**dışı**|
|**Geçersiz öznitelikler**|**'ndaki**|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)
