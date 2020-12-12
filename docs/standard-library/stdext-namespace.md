---
description: 'Daha fazla bilgi için: stdext ad alanı'
title: stdext Ad Alanı
ms.date: 09/06/2017
f1_keywords:
- stdext
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
ms.openlocfilehash: bb81dde22014ec91f7212ce4313c21a8410f30a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153791"
---
# <a name="stdext-namespace"></a>stdext Ad Alanı

[\<hash_map>](../standard-library/hash-map.md)Ve [\<hash_set>](../standard-library/hash-set.md) üst bilgi dosyalarının üyeleri şu anda ISO C++ standardının bir parçası değildir. Bu nedenle, bu türler ve Üyeler `std` `stdext` C++ standardı ile uyumlu kalacak şekilde ad alanından ad alanına taşınmıştır.

Varsayılan olan [/ze](../build/reference/za-ze-disable-language-extensions.md)ile derlerken, derleyici `std` \<hash_map> ve \<hash_set> üst bilgi dosyalarının üyeleri için kullanımını uyarır. Uyarıyı devre dışı bırakmak için [Uyarı](../preprocessor/warning.md) pragmasını kullanın.

Derleyicinin `std` /Ze ile ve üst bilgi dosyalarının üyeleri için kullanımı için bir hata oluşturmasını sağlamak üzere \<hash_map> \<hash_set> , herhangi bir `#include` C++ standart kitaplığı üstbilgi dosyasından önce aşağıdaki yönergeyi ekleyin.

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

**/Za** ile derlerken, derleyici bir hata oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)
