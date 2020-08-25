---
title: gizli (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: ffa1ce01cfd570de7b699e415f10b27acf525047
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830962"
---
# <a name="hidden"></a>gizli

Öğenin var olduğunu ancak kullanıcıya dayalı bir tarayıcıda gösterilmemelidir.

## <a name="syntax"></a>Syntax

```cpp
[hidden]
```

## <a name="remarks"></a>Açıklamalar

**Gizli** C++ özniteliği, [gizli](/windows/win32/Midl/hidden) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Gizli**dizi [kullanımıyla ilgili bir örnek için bkz](bindable.md) ..

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**arabirim**, **`class`** , **`struct`** , yöntem, Özellik|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass** (veya öğesine uygulandığında **`class`** **`struct`** )|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)
