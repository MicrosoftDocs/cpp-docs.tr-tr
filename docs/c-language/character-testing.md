---
title: Karakter Test Etme
ms.date: 11/04/2016
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
ms.openlocfilehash: b02d07ca2796e5088c3021f1ae8795ea92761943
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147197"
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

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)
