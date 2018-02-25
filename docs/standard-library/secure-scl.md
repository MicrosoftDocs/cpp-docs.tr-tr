---
title: _SECURE_SCL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b49e101e944d4309a1d05e605a49452d9e17083c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="securescl"></a>_SECURE_SCL
  
Yerine geçen [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), bu makrosu tanımlar olup olmadığını [işaretli yineleyiciler](../standard-library/checked-iterators.md) etkinleştirilir. Varsayılan olarak işaretli yineleyiciler hata ayıklama derlemelerinde etkin ve perakende yapılarında devre dışı.  
  
> [!IMPORTANT]
> Doğrudan kullanımını `_SECURE_SCL` makrosu kullanım dışıdır. Bunun yerine, kullanın `_ITERATOR_DEBUG_LEVEL` denetlenen yineleyici ayarlarını denetlemek için. Daha fazla bilgi için bkz: [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Açıklamalar  
  
İşaretli yineleyiciler etkinleştirilmişse, güvenli olmayan yineleyici kullanımı bir çalışma zamanı hatasına neden olur ve program sonlandırılır. İşaretli yineleyiciler etkinleştirmek için ayarlanmış `_ITERATOR_DEBUG_LEVEL` 1 veya 2. Bu eşdeğer olan bir `_SECURE_SCL` ayar 1 ya da etkin:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 1  
```  
  
İşaretli yineleyiciler devre dışı bırakmak için ayarlanmış `_ITERATOR_DEBUG_LEVEL` 0. Bu eşdeğer olan bir `_SECURE_SCL` 0 ya da devre dışı ayarlama:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
İşaretli yineleyiciler ilgili uyarılar devre dışı bırakma hakkında daha fazla bilgi için bkz: [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
[İşaretli yineleyiciler](../standard-library/checked-iterators.md)   
[Hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md)   
[Güvenli Kitaplıklar: C++ Standart Kitaplık](../standard-library/safe-libraries-cpp-standard-library.md)

