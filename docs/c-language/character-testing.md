---
description: 'Daha fazla bilgi için: karakter testi'
title: Karakter Test Etme
ms.date: 11/04/2016
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
ms.openlocfilehash: b7d73bce671787622814e11d8f3add7a1092572a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190542"
---
# <a name="character-testing"></a>Karakter Test Etme

**ANSI 4.3.1** ,,,, `isalnum` `isalpha` `iscntrl` `islower` `isprint` Ve `isupper` işlevleri tarafından test edilen karakter kümeleri

Aşağıdaki listede, Microsoft C derleyicisi tarafından uygulanan bu işlevler açıklanmaktadır.

|İşlev|Şunlara yönelik testler|
|--------------|---------------|
|`isalnum`|Karakterler 0-9, A-Z, a-z ASCII 48-57, 65-90, 97-122|
|`isalpha`|Karakterler A-Z, A-z ASCII 65-90, 97-122|
|`iscntrl`|ASCıı 0 -31, 127|
|`islower`|A-z ASCII 97-122 karakterleri|
|`isprint`|A-Z, A-z, 0-9, noktalama, boşluk ASCII 32-126|
|`isupper`|A-Z ASCII 65-90 karakterleri|

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık Işlevleri](../c-language/library-functions.md)
