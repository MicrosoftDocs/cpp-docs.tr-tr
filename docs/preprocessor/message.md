---
description: pragmaMicrosoft C/C++ içinde ileti yönergesi hakkında daha fazla bilgi edinin
title: İleti pragma
ms.date: 01/22/2021
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragma, message
no-loc:
- pragma
ms.openlocfilehash: 6f5e39896e0ba644f9d40665e80cbf7de9026223
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713499"
---
# <a name="message-no-locpragma"></a>`message` pragma

Derlemeyi sonlandırmadan standart çıktıya bir dize sabiti gönderir.

## <a name="syntax"></a>Syntax

> **`#pragma message(`***ileti dizesi***`)`**

## <a name="remarks"></a>Açıklamalar

Öğesinin tipik kullanımı, **`message`** pragma derleme zamanında bilgilendirici iletileri görüntülemektir.

*İleti dizesi* parametresi bir dize değişmez değerine genişleyen bir makro olabilir ve bu tür makroları herhangi bir kombinasyonda dize sabit değerleri ile birleştirebilirsiniz.

İçinde önceden tanımlanmış bir makro kullanıyorsanız **`message`** pragma , makro bir dize döndürmelidir. Aksi takdirde, makronun çıkışını bir dizeye dönüştürmeniz gerekir.

Aşağıdaki kod parçası, **`message`** pragma derleme sırasında iletileri göstermek için kullanır:

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

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
