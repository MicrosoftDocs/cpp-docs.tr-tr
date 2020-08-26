---
title: default_delete yapısı
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: 8baa9f5d294cf083fd55414cd529e438f328d1a1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845087"
---
# <a name="default_delete-struct"></a>default_delete yapısı

Bağımsız değişkenlerinde bölüm işlemini () gerçekleştiren önceden tanımlanmış bir işlev nesnesi `operator/` .

## <a name="syntax"></a>Syntax

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<memory>

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[default_delete](#default_delete)|Türündeki nesneler için Oluşturucu `default_delete` .|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[operator ()](#op_paren)|Erişim için bir başvuru işleci `default_delete` .|

## <a name="default_delete"></a><a name="default_delete"></a> default_delete

Türündeki nesneler için Oluşturucu `default_delete` .

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="operator"></a><a name="op_paren"></a> operator ()

Erişim için bir başvuru işleci `default_delete` .

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<memory>](../standard-library/memory.md)
