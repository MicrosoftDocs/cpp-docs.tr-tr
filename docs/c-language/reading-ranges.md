---
title: Okuma aralıkları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76530dfdac917dfbde50bc3fb1b17a3c31178729
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030253"
---
# <a name="reading-ranges"></a>Okuma Aralıkları

**ANSI 4.9.6.2** ilk bir tire (-) karakteri ya da son karakter % için scanlist içindeki yorumunu [dönüştürme `fscanf` işlevi

Aşağıdaki satır

```
fscanf( fileptr, "%[A-Z]", strptr);
```

herhangi bir sayıda aralığına A-Z dizesi hangi karakter okur `strptr` noktaları.

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)