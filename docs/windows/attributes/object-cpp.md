---
title: Nesne (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8828ada429875245d583c30d65259300a01f6a5d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067442"
---
# <a name="object-c"></a>nesne (C++)

Özel bir arabirim tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[object]
```

## <a name="remarks"></a>Açıklamalar

Bir arabirim tanımı önce geldiği zaman **nesne** C++ özniteliği arabirimi .idl dosyası özel bir arabirim olarak yerleştirilmesini neden olur.

Nesne ile işaretlenen herhangi bir arabirimde devralmalıdır `IUnknown`. Devralınan taban arabirimlerin herhangi, bu koşul sağlanana `IUnknown`. Temel arabirim devralır, `IUnknown`, derleyici ile işaretlenen arabirim neden olacak **nesne** türetmek için `IUnknown`.

## <a name="example"></a>Örnek

Bkz: [nonbrowsable](nonbrowsable.md) nasıl kullanılacağına ilişkin bir örnek **nesne**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)