---
title: space_info yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::tr2::sys::space_info
dev_langs:
- C++
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e078b38dd90fcda7a6973ac1b0aee13c301823d4
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691438"
---
# <a name="spaceinfo-structure"></a>space_info Yapısı

Bir birim ilgili bilgileri tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct space_info   {
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
    };
```

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|`unsigned long long available`|Birimdeki verileri temsil etmek kullanılabilen bayt sayısını temsil eder.|
|`unsigned long long capacity`|Birim temsil edebilen bayt toplam sayısını temsil eder.|
|`unsigned long long free`|Birimdeki verileri temsil etmek için kullanılmayan bayt sayısını temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<filesystem >

**Namespace:** std::experimental::filesystem

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<FileSystem >](../standard-library/filesystem.md)<br/>
[Dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md)<br/>
