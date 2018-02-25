---
title: stdext Namespace | Microsoft Docs
ms.custom: 
ms.date: 09/06/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- stdext
dev_langs:
- C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 265a10e71064f2bf3a318a272b751009b1b193be
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="stdext-namespace"></a>stdext Ad Alanı

Üyeleri [ \<hash_map >](../standard-library/hash-map.md) ve [ \<hash_set >](../standard-library/hash-set.md) üstbilgi dosyaları olmayan şu anda ISO C++ standart bir parçası. Bu nedenle, bu tür ve üyelerin gelen taşınmış `std` ad alanına ad alanı `stdext`, C++ Standart uyumluluğunu kalmasına.

İle derleme yapılırken [/Ze](../build/reference/za-ze-disable-language-extensions.md), derleyici kullanılmasına uyarır varsayılan olduğu `std` üyeleri için \<hash_map > ve \<hash_set > üst bilgi dosyaları. Uyarıyı devre dışı bırakmak için [uyarı](../preprocessor/warning.md) pragması.

Kullanımıyla ilgili bir hata oluştur derleyici olmasını `std` üyeleri için \<hash_map > ve \<hash_set > başlık dosyaları ile **/Ze**, önce aşağıdaki yönergesi eklemek `#include` tüm C++ standart kitaplık üstbilgi dosyaları.

```cpp  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  

İle derleme yapılırken **/Za**, derleyici bir hata oluşturur.  

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)

