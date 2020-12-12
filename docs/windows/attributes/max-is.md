---
description: 'Hakkında daha fazla bilgi edinin: max_is'
title: max_is (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.max_is
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
ms.openlocfilehash: 305acba3a2831448cf677eb16810c567b3561b3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329803"
---
# <a name="max_is"></a>max_is

Geçerli bir dizi dizininin en büyük değerini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ max_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*expression*<br/>
Bir veya daha fazla C-dil ifadesi. Boş bağımsız değişken yuvalarına izin veriliyor.

## <a name="remarks"></a>Açıklamalar

**Max_is** C++ özniteliği, [max_is](/windows/win32/Midl/max-is) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`struct`** Or **`union`** , Interface parametresi, Interface yöntemi içindeki alan|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|**size_is**|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Örnek

Dizinin bir bölümünü belirtme örneği için bkz. [first_is](first-is.md) .

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)
