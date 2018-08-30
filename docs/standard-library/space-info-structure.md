---
title: space_info yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 7c0e9a636fea95a4ce829731c25605197ee00549
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206741"
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
[alanı](https://msdn.microsoft.com/7fce0b0e-523b-4598-b218-47245d0204ca)<br/>
[Dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md)<br/>
