---
description: 'Hakkında daha fazla bilgi edinin: default_delete struct'
title: default_delete yapısı
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: 5b7d652dbb556957acf96ba63ac9ce14b628fb7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232973"
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
