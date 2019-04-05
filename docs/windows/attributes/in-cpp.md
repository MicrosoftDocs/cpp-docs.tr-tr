---
title: (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: 06d78552ef2ebb878ed630eb377e6249ba60cad4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034543"
---
# <a name="in-c"></a>in (C++)

Bir parametrenin çağıran yordamdan çağrılan yordama geçirileceğini gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
[in]
```

## <a name="remarks"></a>Açıklamalar

**İçinde** C++ özniteliği ile aynı işlevlere sahip [içinde](/windows/desktop/Midl/in) MIDL özniteliği.

## <a name="example"></a>Örnek

Bkz: [bağlanabilir](bindable.md) nasıl kullanılacağına ilişkin bir örnek **içinde**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|Arabirimi parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|**retval**|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[kimlik](id.md)<br/>
[out](out-cpp.md)