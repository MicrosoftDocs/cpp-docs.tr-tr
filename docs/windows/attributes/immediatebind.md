---
title: immediatebind (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.immediatebind
helpviewer_keywords:
- immediatebind attribute
ms.assetid: 186d40e6-9166-4d0c-9853-4e7e4d25226f
ms.openlocfilehash: d5241a6972ea0444a980e3e868c44e7e0c15dc64
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833055"
---
# <a name="immediatebind"></a>immediatebind

Veritabanına, veri bağlantılı nesnenin bir özelliğindeki tüm değişikliklerin hemen bildirileceğini bildirir.

## <a name="syntax"></a>Syntax

```cpp
[immediatebind]
```

## <a name="remarks"></a>Açıklamalar

**İmmediatebind** C++ özniteliği, [immediatebind](/windows/win32/Midl/immediatebind) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**İmmediatebind**'in nasıl kullanılacağına ilişkin bir örnek [için bkz. bağlanabilir.](bindable.md)

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[requestedit](requestedit.md)
