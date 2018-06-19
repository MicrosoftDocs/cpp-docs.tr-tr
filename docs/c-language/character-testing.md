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
ms.openlocfilehash: cdf65de941486cb8256ba8e30a3f186d3e3702d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381700"
---
# <a name="character-testing"></a>Karakter Test Etme
**ANSI 4.3.1** tarafından karakter kümesi test için `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint`, ve `isupper` işlevleri  
  
 Aşağıdaki listede, Microsoft C derleyicisi tarafından uygulanan bu işlevler açıklanmaktadır.  
  
|İşlev|Şunlara yönelik testler|  
|--------------|---------------|  
|`isalnum`|Karakter 0 - 48 57, 65-90, 97 122 9, A-Z, a-z ASCII|  
|`isalpha`|Karakter A-Z, a-z ASCII 65-90, 97 122|  
|`iscntrl`|ASCII 0-31, 127|  
|`islower`|Karakter a-z ASCII 97-122|  
|`isprint`|Karakter A-Z, a-z, 0 - 9 Noktalama, ASCII 32-126 boşluk|  
|`isupper`|A-Z 65-90 ASCII karakterleri|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık İşlevleri](../c-language/library-functions.md)