---
description: 'Daha fazla bilgi edinin: kapsayıcı sınıfı:: takas'
title: Kapsayıcı Sınıfı::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: a38dd6d14ada3ad50927060ccec1542ebf2fd4ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233363"
---
# <a name="container-classswap"></a>Kapsayıcı Sınıfı::swap

> [!NOTE]
> Bu konu, C++ standart kitaplığı 'nda kullanılan kapsayıcılardan oluşan işlevsel bir örnek olarak Microsoft C++ belgelerinde yer almaktadır. Daha fazla bilgi için bkz. [C++ standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

**\* Bu** ve bağımsız değişkeni arasındaki denetlenen dizileri değiştirir.

## <a name="syntax"></a>Syntax

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Açıklamalar

**\* Bu. Get \_ ayırıcısı = =** _Right_**.get_allocator**, sabit bir zamanda takas yapar. Aksi takdirde, bir dizi öğe ataması ve Oluşturucu çağrısı, iki denetimli dizi içindeki öğe sayısıyla orantılı olarak gerçekleştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[Örnek kapsayıcı sınıfı](../standard-library/sample-container-class.md)
