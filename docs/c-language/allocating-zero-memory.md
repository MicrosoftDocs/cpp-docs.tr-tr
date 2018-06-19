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
ms.openlocfilehash: 0de013e9ddd3fb983436bf6ee0db290458936eb5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380644"
---
# <a name="allocating-zero-memory"></a>Sıfır Bellek Ayırma
**ANSI 4.10.3** davranışını `calloc`, `malloc`, veya `realloc` istenen boyutu sıfır ise işlevi  
  
 `calloc`, `malloc` ve `realloc` işlevleri, bir bağımsız değişken olarak sıfırı kabul eder. Gerçek bellek tahsis edilmez, ancak geçerli bir işaretçi döndürülür ve bellek bloğu daha sonra realloc tarafından değiştirilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık İşlevleri](../c-language/library-functions.md)