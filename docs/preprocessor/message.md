---
description: 'Daha fazla bilgi için: ileti pragma'
title: message pragması
ms.date: 08/29/2019
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
ms.openlocfilehash: 82b8efa7e232c24402b7fb1cce0fd1e38ff8be29
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333379"
---
# <a name="message-pragma"></a>message pragması

Derlemeyi sonlandırmadan standart çıktıya bir dize sabiti gönderir.

## <a name="syntax"></a>Syntax

> **#pragma iletisi (** *ileti dizesi* **)**

## <a name="remarks"></a>Açıklamalar

**İleti** pragma 'un tipik bir kullanımı, derleme zamanında bilgilendirici iletileri görüntülemektir.

*İleti dizesi* parametresi bir dize değişmez değerine genişleyen bir makro olabilir ve bu tür makroları herhangi bir kombinasyonda dize sabit değerleri ile birleştirebilirsiniz.

**İleti** pragma öğesinde önceden tanımlanmış bir makro kullanırsanız, makro bir dize döndürmelidir. Aksi takdirde, makronun çıkışını bir dizeye dönüştürmeniz gerekir.

Aşağıdaki kod parçası, derleme sırasında iletileri göstermek için pragma **iletisini** kullanır:

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

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
