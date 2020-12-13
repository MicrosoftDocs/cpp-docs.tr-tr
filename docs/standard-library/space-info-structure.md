---
description: 'Daha fazla bilgi edinin: space_info yapısı'
title: space_info Yapısı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::space_info
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
ms.openlocfilehash: 254866a0eb225b4ed7bcfe4e06a734c5c9d0e3ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153882"
---
# <a name="space_info-structure"></a>space_info Yapısı

Bir birimle ilgili bilgileri tutar.

## <a name="syntax"></a>Syntax

```cpp
struct space_info
{
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
};
```

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|`unsigned long long capacity`|Birimin temsil ettiği toplam bayt sayısını temsil eder.|
|`unsigned long long free`|Birimdeki verileri temsil etmek için kullanılmayan bayt sayısını temsil eder.|
|`unsigned long long available`|Birimdeki verileri temsil etmek için kullanılabilen bayt sayısını temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<filesystem>

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md)
