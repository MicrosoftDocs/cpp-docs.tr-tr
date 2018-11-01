---
title: max_is (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.max_is
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
ms.openlocfilehash: 10732d5ba3251185dc7027e3449486af3037f763
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627480"
---
# <a name="maxis"></a>max_is

Geçerli dizi dizini için maksimum değeri atar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ max_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*İfade*<br/>
Bir veya daha fazla C dili ifadeleri. Boş bağımsız değişken yuvaları izin verilir.

## <a name="remarks"></a>Açıklamalar

**Max_is** C++ özniteliği ile aynı işlevlere sahip [max_is](/windows/desktop/Midl/max-is) MIDL özniteliği.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|İçinde alan **yapı** veya **birleşim**, parametre arabirim, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|**size_is**|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Örnek

Bkz: [first_is](first-is.md) örneği nasıl bir dizinin bir bölümünü belirtin.

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)