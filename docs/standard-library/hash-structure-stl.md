---
description: 'Daha fazla bilgi edinin: karma yapısı (C++ Standart Kitaplığı)'
title: Karma yapısı (C++ Standart Kitaplığı) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- thread/std::hash
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
ms.openlocfilehash: 095566b6855c837c3ee6049a5cbedfbb087420bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324074"
---
# <a name="hash-structure-c-standard-library"></a>hash Yapısı (C++ Standart Kitaplığı)

Tarafından benzersiz olarak belirlenen bir değer döndüren bir üye işlevi tanımlar `Val` . Üye işlevi, türündeki değerleri [](../standard-library/hash-class.md) `thread::id` Dizin değerlerinin bir dağıtımına eşlemek için uygun bir karma işlevi tanımlar.

## <a name="syntax"></a>Syntax

```cpp
template <>
struct hash<thread::id> :
    public unary_function<thread::id, size_t>
{
    size_t operator()(thread::id Val) const;

};
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<thread>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<thread>](../standard-library/thread.md)\
[unary_function yapısı](../standard-library/unary-function-struct.md)
