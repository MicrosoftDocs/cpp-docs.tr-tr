---
description: 'Daha fazla bilgi edinin: piecewise_contruct_t yapısı'
title: piecewise_contruct_t yapısı
ms.date: 11/04/2016
f1_keywords:
- utility/std::piecewise_contruct_t
helpviewer_keywords:
- piecewise_contruct_t class
- piecewise_contruct_t structure
ms.openlocfilehash: 7fefacff75b47c25cb9ae07cc894498eadb551df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340755"
---
# <a name="piecewise_contruct_t-structure"></a>piecewise_contruct_t yapısı

Yapı, `piecewise_construct_t` ayrı Oluşturucu ve işlev aşırı yüklemesini tutmak için kullanılan boş bir yapı türüdür. Özellikle, `pair` `piecewise_construct_t` ilk bağımsız değişken olarak ve ardından iki bağımsız değişken içeren bir oluşturucuya sahiptir `tuple` .

## <a name="syntax"></a>Syntax

```cpp
struct piecewise_construct_t { explicit piecewise_construct_t() = default; };

inline constexpr piecewise_construct_t piecewise_construct{};
```
