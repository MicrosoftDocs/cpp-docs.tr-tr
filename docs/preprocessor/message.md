---
title: " iletisi"
ms.date: 11/04/2016
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
ms.openlocfilehash: e9383238fd308ec59a9767f56af1c07fc3cfcf07
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030212"
---
# <a name="message"></a> iletisi
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

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)