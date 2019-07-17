---
title: piecewise_contruct_t yapısı
ms.date: 11/04/2016
f1_keywords:
- utility/std::piecewise_contruct_t
helpviewer_keywords:
- piecewise_contruct_t class
- piecewise_contruct_t structure
ms.openlocfilehash: 6a9a6af97ca5c7751d64cd1fa70c9d9eba87da7c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267864"
---
# <a name="piecewisecontructt-structure"></a>piecewise_contruct_t yapısı

Struct `piecewise_construct_t` ayrı oluşturucusu ve işlev aşırı yüklemesi tutmak için kullanılan bir boş yapı türü. Özellikle, `pair` sahip bir oluşturucuyla `piecewise_construct_t` ilk bağımsız değişken olarak ikiye ardından `tuple` bağımsız değişkenler.

## <a name="syntax"></a>Sözdizimi

```cpp
struct piecewise_construct_t { explicit piecewise_construct_t() = default; };

inline constexpr piecewise_construct_t piecewise_construct{};
```
