---
title: stdext Ad Alanı
ms.date: 09/06/2017
f1_keywords:
- stdext
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
ms.openlocfilehash: d40f3f7a99db72784cc9a32a9c37064228597d34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412429"
---
# <a name="stdext-namespace"></a>stdext Ad Alanı

Üyeleri [ \<hash_map >](../standard-library/hash-map.md) ve [ \<hash_set >](../standard-library/hash-set.md) üst bilgi dosyaları şu anda parçası değildir ISO C++ standart. Bu nedenle, bu türleri ve üyeleri öğesinden taşındı `std` ad alanına ad alanı `stdext`, C++ standardı ile uyumlu kalır.

İle derlerken [/Ze](../build/reference/za-ze-disable-language-extensions.md), varsayılan değer olan, derleyici kullanımı hakkında uyarır `std` üyelerinin \<hash_map > ve \<hash_set > üst bilgi dosyaları. Uyarı devre dışı bırakmak için [uyarı](../preprocessor/warning.md) pragması.

Derleyicinin kullanımıyla ilgili bir hata oluşturmak için `std` üyelerinin \<hash_map > ve \<hash_set > üst bilgi dosyaları ile **/Ze**, önce aşağıdaki yönerge ekleyin `#include` tüm C++ standart kitaplığı üst bilgi dosyaları.

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

İle derlerken **/Za**, derleyici bir hata oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)
