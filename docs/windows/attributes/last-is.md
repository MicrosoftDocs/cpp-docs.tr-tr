---
title: last_is (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.last_is
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
ms.openlocfilehash: 62377415dc0809033fcdcb8bd4e7997f667c1691
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214818"
---
# <a name="last_is"></a>last_is

İletilmek üzere son dizi öğesinin dizinini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ last_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*ifadesini*<br/>
Bir veya daha fazla C-dil ifadesi. Boş bağımsız değişken yuvalarına izin veriliyor.

## <a name="remarks"></a>Açıklamalar

**Last_is** C++ özniteliği [last_is](/windows/win32/Midl/last-is) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Dizinin bir bölümünü belirtme örneği için bkz. [first_is](first-is.md) .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**Struct** veya **Union**içindeki alan, arabirim parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)
