---
description: 'Daha fazla bilgi edinin: sıfır bellek ayırma'
title: Sıfır Bellek Ayırma
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: 7971d9e097d00607af2acf4590ff3daaf67f7127
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280150"
---
# <a name="allocating-zero-memory"></a>Sıfır Bellek Ayırma

**ANSI 4.10.3** `calloc` `malloc` `realloc` İstenen boyut sıfırsa,, veya işlevinin davranışı

`calloc`, `malloc` ve `realloc` işlevleri, bir bağımsız değişken olarak sıfırı kabul eder. Gerçek bellek tahsis edilmez, ancak geçerli bir işaretçi döndürülür ve bellek bloğu daha sonra realloc tarafından değiştirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık Işlevleri](../c-language/library-functions.md)
