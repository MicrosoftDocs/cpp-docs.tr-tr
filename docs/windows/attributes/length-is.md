---
title: length_is (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.length_is
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
ms.openlocfilehash: 1de168606b57c801bc3dc1fb9aee76eb6f3d54c8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039916"
---
# <a name="lengthis"></a>length_is

Aktarılacak dizi öğelerinin sayısını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ length_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*ifade*<br/>
Bir veya daha fazla C dili ifadeleri. Boş bağımsız değişken yuvaları izin verilir.

## <a name="remarks"></a>Açıklamalar

**Length_is** C++ özniteliği ile aynı işlevlere sahip [length_is](/windows/desktop/Midl/length-is) MIDL özniteliği.

## <a name="example"></a>Örnek

Bkz: [first_is](first-is.md) örneği nasıl bir dizinin bir bölümünü belirtin.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|İçinde alan **yapı** veya **birleşim**, parametre arabirim, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|None|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[last_is](last-is.md)<br/>
[size_is](size-is.md)