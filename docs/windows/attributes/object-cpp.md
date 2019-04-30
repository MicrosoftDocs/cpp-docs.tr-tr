---
title: Nesne (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: c0f544e84e5110761dfd01e25abef4352f055ff5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407542"
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

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)