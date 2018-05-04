---
title: Tür denetimi (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.types
dev_langs:
- C++
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 959dd52847e6140667671b9992471155d68e9646
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="type-checking-crt"></a>Tür Denetleme (CRT)
Derleyici sınırlı tür denetlemesi değişken sayıda bağımsız değişken, aşağıdaki gibi yapabileceği işlevleri gerçekleştirir:  
  
|İşlev çağrısı|Bağımsız değişken türü işaretli|  
|-------------------|-----------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|İlk bağımsız değişken (biçim dizesi)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|İlk iki bağımsız değişken (dosya veya arabellek ve biçim dizesi)|  
|`_snprintf_s`|İlk üç bağımsız değişken (dosya veya arabellek sayısı ve biçim dizesi)|  
|`_open`|İlk iki bağımsız değişkenler (yol ve `_open` bayrağı)|  
|`_sopen_s`|İlk üç bağımsız değişkenler (yol, `_open` bayrağı ve Paylaşım modu)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|İlk iki bağımsız değişken (yolu ve ilk bağımsız değişkeni işaretçisi)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|İlk üç bağımsız değişken (modu bayrağını, yol ve ilk bağımsız değişkeni işaretçisi)|  
  
 Derleyici aynı sınırlı tür bu işlevler joker karakter karşılık gelen denetleme gerçekleştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)