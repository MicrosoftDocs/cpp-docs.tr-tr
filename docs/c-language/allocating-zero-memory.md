---
title: Sıfır bellek ayırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc3b7a92cdc8a05c73f15c7cea917d86a3b6bb46
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085062"
---
# <a name="allocating-zero-memory"></a>Sıfır Bellek Ayırma

**ANSI 4.10.3** davranışını `calloc`, `malloc`, veya `realloc` istenen boyut sıfırsa işlevi

`calloc`, `malloc` ve `realloc` işlevleri, bir bağımsız değişken olarak sıfırı kabul eder. Gerçek bellek tahsis edilmez, ancak geçerli bir işaretçi döndürülür ve bellek bloğu daha sonra realloc tarafından değiştirilebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)