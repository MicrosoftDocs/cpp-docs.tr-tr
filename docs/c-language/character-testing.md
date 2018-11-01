---
title: Karakter Test Etme
ms.date: 11/04/2016
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
ms.openlocfilehash: 31a90f28d710ffc1b58f9c6b3fcfd01fd8d2d00c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523207"
---
# <a name="character-testing"></a>Karakter Test Etme

**ANSI 4.3.1** karakter kümesi tarafından test edilen `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint`, ve `isupper` işlevleri

Aşağıdaki listede, Microsoft C derleyicisi tarafından uygulanan bu işlevler açıklanmaktadır.

|İşlev|Şunlara yönelik testler|
|--------------|---------------|
|`isalnum`|Karakter 0 - 48 57, 65-90, 97 122 9, A-Z, a-z ASCII|
|`isalpha`|Karakter A-Z, a-z ASCII 65-90, 97 122|
|`iscntrl`|ASCII 0-31 ŞARTLARINI KARŞILAYAN, 127|
|`islower`|A-z ASCII 97-122 karakterleri|
|`isprint`|Karakter A-Z, a-z, 0 - 9, noktalama işareti, boşluk ASCII 32 126|
|`isupper`|A-Z ASCII 65-90 karakterleri|

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)