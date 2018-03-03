---
title: "Tür denetimi (CRT) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.types
dev_langs:
- C++
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d18ae0818dd839bee0d93bd7194dadcc9abf6627
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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