---
title: max_is (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.max_is
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
ms.openlocfilehash: b4931962febb1e68701aa3fe271e08f3aa8d9238
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166763"
---
# <a name="max_is"></a>max_is

Geçerli bir dizi dizininin en büyük değerini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ max_is("expression") ]
```

### <a name="parameters"></a>Parametreler

*ifadesini*<br/>
Bir veya daha fazla C-dil ifadesi. Boş bağımsız değişken yuvalarına izin veriliyor.

## <a name="remarks"></a>Açıklamalar

**Max_is** C++ özniteliği [max_is](/windows/win32/Midl/max-is) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**Struct** veya **Union**içindeki alan, arabirim parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|**size_is**|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Örnek

Dizinin bir bölümünü belirtme örneği için bkz. [first_is](first-is.md) .

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)
