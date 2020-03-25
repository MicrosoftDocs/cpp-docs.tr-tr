---
title: gizli (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: 6b420e8f50bd217de460a81f5faaf9583c701376
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168102"
---
# <a name="hidden"></a>gizli

Öğenin var olduğunu ancak kullanıcıya dayalı bir tarayıcıda gösterilmemelidir.

## <a name="syntax"></a>Sözdizimi

```cpp
[hidden]
```

## <a name="remarks"></a>Açıklamalar

**Hidden** C++ özniteliği, [Hidden](/windows/win32/Midl/hidden) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Gizli**dizi [kullanımıyla ilgili bir örnek için bkz](bindable.md) .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**arabirim**, **sınıf**, **Yapı**, yöntem, Özellik|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass** ( **sınıfa** veya **yapıya**uygulandığında)|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)
