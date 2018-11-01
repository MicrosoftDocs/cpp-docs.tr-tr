---
title: iletisi
ms.date: 11/04/2016
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
ms.openlocfilehash: a55721fb954cf9383022b4fc8e84327ea4c772e7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627389"
---
# <a name="message"></a>iletisi
Derlemeyi sonlandırmadan standart çıktıya bir dize sabiti gönderir.

## <a name="syntax"></a>Sözdizimi

```
#pragma message( messagestring )
```

## <a name="remarks"></a>Açıklamalar

Tipik bir kullanımı, **ileti** pragması, derleme zamanında bilgi iletileri görüntülemek için.

*Messagestring* parametresi bir dize sabiti olarak genişleyen bir makro olabilir ve bu tür makroları dize herhangi bir birleşimini bitiştirebilirsiniz.

Önceden tanımlanmış bir makro kullanırsanız **ileti** pragması, makro bir dize döndürmelidir, aksi takdirde makronun çıktısını bir dizeye dönüştürmek gerekir.

Aşağıdaki kod parçası kullanan **ileti** pragması, derleme sırasında iletileri görüntülemek için:

```cpp
// pragma_directives_message1.cpp
// compile with: /LD
#if _M_IX86 >= 500
#pragma message("_M_IX86 >= 500")
#endif

#pragma message("")

#pragma message( "Compiling " __FILE__ )
#pragma message( "Last modified on " __TIMESTAMP__ )

#pragma message("")

// with line number
#define STRING2(x) #x
#define STRING(x) STRING2(x)

#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")

#pragma message("")
```

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)