---
title: Karakter Test Etme
ms.date: 11/04/2016
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
ms.openlocfilehash: b02d07ca2796e5088c3021f1ae8795ea92761943
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740095"
---
# <a name="character-testing"></a>Karakter Test Etme

**ANSI 4.3.1** `isalnum` ,`isalpha` ,,`isupper` , Ve işlevleri tarafından test edilen karakter kümeleri `islower` `iscntrl` `isprint`

Aşağıdaki listede, Microsoft C derleyicisi tarafından uygulanan bu işlevler açıklanmaktadır.

|İşlev|Şunlara yönelik testler|
|--------------|---------------|
|`isalnum`|Karakterler 0-9, A-Z, a-z ASCII 48-57, 65-90, 97-122|
|`isalpha`|Karakterler A-Z, A-z ASCII 65-90, 97-122|
|`iscntrl`|ASCII 0 -31, 127|
|`islower`|A-z ASCII 97-122 karakterleri|
|`isprint`|A-Z, A-z, 0-9, noktalama, boşluk ASCII 32-126|
|`isupper`|A-Z ASCII 65-90 karakterleri|

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)
