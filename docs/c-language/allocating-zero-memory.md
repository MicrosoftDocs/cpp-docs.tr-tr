---
title: Sıfır Bellek Ayırma
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: c7d5f307a38fff938c94cf2e1660cec99262a10a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447313"
---
# <a name="allocating-zero-memory"></a>Sıfır Bellek Ayırma

**ANSI 4.10.3** davranışını `calloc`, `malloc`, veya `realloc` istenen boyut sıfırsa işlevi

`calloc`, `malloc` ve `realloc` işlevleri, bir bağımsız değişken olarak sıfırı kabul eder. Gerçek bellek tahsis edilmez, ancak geçerli bir işaretçi döndürülür ve bellek bloğu daha sonra realloc tarafından değiştirilebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)