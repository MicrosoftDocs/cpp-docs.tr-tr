---
title: retval (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 5aded4588614eb4171e31a588f125ea8aa8de7ee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166347"
---
# <a name="retval"></a>retval

Üyenin dönüş değerini alan parametreyi belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
[retval]
```

## <a name="remarks"></a>Açıklamalar

**Retval** C++ özniteliği, [retval](/windows/win32/Midl/retval) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

**retval** , bir işlevin bildiriminde yer alan son bağımsız değişkende yer almalıdır.

## <a name="example"></a>Örnek

**Retval**öğesinin örnek kullanımı için [bağlanabilir](bindable.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Arabirim parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**out**|
|**Geçersiz öznitelikler**|**in**|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)
