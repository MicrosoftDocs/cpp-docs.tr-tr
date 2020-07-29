---
title: last_is (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.last_is
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
ms.openlocfilehash: 7aa8acb52d19bc7f70513e44770817ae7fc403b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224415"
---
# <a name="last_is"></a>last_is

İletilmek üzere son dizi öğesinin dizinini belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ last_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*ifadesini*<br/>
Bir veya daha fazla C-dil ifadesi. Boş bağımsız değişken yuvalarına izin veriliyor.

## <a name="remarks"></a>Açıklamalar

**Last_is** C++ özniteliği, [last_is](/windows/win32/Midl/last-is) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Dizinin bir bölümünü belirtme örneği için bkz. [first_is](first-is.md) .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|**`struct`** Or **`union`** , Interface parametresi, Interface yöntemi içindeki alan|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)
