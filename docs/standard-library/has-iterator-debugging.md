---
title: _HAS_ITERATOR_DEBUGGING | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _HAS_ITERATOR_DEBUGGING
dev_langs: C++
helpviewer_keywords: _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c680338fa84fa0f00e01ea4612d07c851570a36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING  
  
Yerine geçen [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), bu makrosu özelliği hata ayıklama yineleyici hata ayıklama derlemede etkin olup olmadığını tanımlar. Varsayılan olarak, hata ayıklama yineleyici hata ayıklama derlemelerinde etkin ve perakende yapılarında devre dışı. Daha fazla bilgi için bkz: [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md).  
  
> [!IMPORTANT]
> Doğrudan kullanımını `_HAS_ITERATOR_DEBUGGING` makrosu kullanım dışıdır. Bunun yerine, kullanın `_ITERATOR_DEBUG_LEVEL` denetlemek için yineleyici hata ayıklama, ayarları. Daha fazla bilgi için bkz: [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Açıklamalar  
Yineleyici hata ayıklama derlemelerinde hata ayıklamayı etkinleştirmek için ayarlanmış `_ITERATOR_DEBUG_LEVEL` 2. Bu eşdeğer olan bir `_HAS_ITERATOR_DEBUGGING` ayar 1 ya da etkin:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 2  
```  
  
`_ITERATOR_DEBUG_LEVEL`2 olarak ayarlanmış (ve `_HAS_ITERATOR_DEBUGGING` 1 olarak ayarlayın) perakende oluşturur.  
  
Hata ayıklama yineleyiciler hata ayıklama derlemelerinde devre dışı bırakmak için ayarlanmış `_ITERATOR_DEBUG_LEVEL` için 0 veya 1. Bu eşdeğer olan bir `_HAS_ITERATOR_DEBUGGING` 0 ya da devre dışı ayarlama:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
 [Hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md)   
 [İşaretli yineleyiciler](../standard-library/checked-iterators.md)   
 [Güvenli Kitaplıklar: C++ Standart Kitaplık](../standard-library/safe-libraries-cpp-standard-library.md)

