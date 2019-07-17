---
title: default_delete yapısı
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: e9e1fcc68539e55486f4ea27e6dd5c49bed11fdf
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268134"
---
# <a name="defaultdelete-struct"></a>default_delete yapısı

Bölme işlemi gerçekleştiren bir önceden tanımlanmış bir işlev nesnesi (`operator/`) üzerinde bağımsız değişkenleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[default_delete](#default_delete)|Türündeki nesneler için oluşturucu `default_delete`.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator()](#op_paren)|Erişmek için bir başvuru işleci `default_delete`.|

## <a name="default_delete"></a> default_delete

Türündeki nesneler için oluşturucu `default_delete`.

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="op_paren"></a> operator()

Erişmek için bir başvuru işleci `default_delete`.

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)
