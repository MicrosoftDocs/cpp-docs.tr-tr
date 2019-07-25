---
title: space_info Yapısı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::space_info
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
ms.openlocfilehash: 2a9856746a8bbc796871663a81bd8911d34dcd4a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457549"
---
# <a name="spaceinfo-structure"></a>space_info Yapısı

Bir birimle ilgili bilgileri tutar.

## <a name="syntax"></a>Sözdizimi

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

**Üst bilgi:** \<dosya sistemi >

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<dosya sistemi >](../standard-library/filesystem.md)\
[Dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md)
