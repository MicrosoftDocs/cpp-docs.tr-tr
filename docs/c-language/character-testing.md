---
title: Karakter test etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2c558c5d32f75561d5722a656450d5f18f5166a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084945"
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