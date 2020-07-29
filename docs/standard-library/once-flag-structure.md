---
title: once_flag Yapısı
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 55c3f90f72857a4e4cd3f9075ce5bae10e14d218
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202733"
---
# <a name="once_flag-structure"></a>once_flag Yapısı

**`struct`** Başlatma kodunun birden çok iş parçacığının bulunması durumunda bile yalnızca bir kez çağrıldığından emin olmak için [call_once](../standard-library/mutex-functions.md#call_once) şablon işlevi ile birlikte kullanılan bir öğesini temsil eder.

## <a name="syntax"></a>Sözdizimi

struct once_flag {constexpr once_flag () noexcept;};

## <a name="remarks"></a>Açıklamalar

`once_flag` **`struct`** Yalnızca bir varsayılan oluşturucuya sahiptir.

Türündeki nesneler `once_flag` oluşturulabilir, ancak bunlar kopyalanamazlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<mutex>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
