---
title: "Sıfır bellek ayırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9708f8939ff32f9320e7c8e803753e801ce9448f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="allocating-zero-memory"></a>Sıfır Bellek Ayırma
**ANSI 4.10.3** davranışını `calloc`, `malloc`, veya `realloc` istenen boyutu sıfır ise işlevi  
  
 `calloc`, `malloc` ve `realloc` işlevleri, bir bağımsız değişken olarak sıfırı kabul eder. Gerçek bellek tahsis edilmez, ancak geçerli bir işaretçi döndürülür ve bellek bloğu daha sonra realloc tarafından değiştirilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık işlevleri](../c-language/library-functions.md)