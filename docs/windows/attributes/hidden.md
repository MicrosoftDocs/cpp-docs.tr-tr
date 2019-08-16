---
title: gizli (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: 75b03877b1204d6e1c4770f5ba9c8c88338b3394
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501457"
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

**Gizli**dizi kullanımıyla ilgili [](bindable.md) bir örnek için bkz.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**arabirim**, **sınıf**, **Yapı**, yöntem, Özellik|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass** ( **sınıfa** veya **yapıya**uygulandığında)|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)