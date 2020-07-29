---
title: gizli (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: e0e3c5cb0355f3bedd8ecee57b034f0d9dde87df
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224441"
---
# <a name="hidden"></a>gizli

Öğenin var olduğunu ancak kullanıcıya dayalı bir tarayıcıda gösterilmemelidir.

## <a name="syntax"></a>Sözdizimi

```cpp
[hidden]
```

## <a name="remarks"></a>Açıklamalar

**Gizli** C++ özniteliği, [gizli](/windows/win32/Midl/hidden) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Gizli**dizi [kullanımıyla ilgili bir örnek için bkz](bindable.md) ..

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|**arabirim**, **`class`** , **`struct`** , yöntem, Özellik|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass** (veya öğesine uygulandığında **`class`** **`struct`** )|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)
