---
title: Tür Denetleme (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.types
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
ms.openlocfilehash: fd892426bb7301acad7ce2a93430e52f25e7c9b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626120"
---
# <a name="type-checking-crt"></a>Tür Denetleme (CRT)

Derleyici, sınırlı tür, değişken sayıda bağımsız değişken şu şekilde gerçekleştirebileceği işlevleri gerçekleştirir:

|İşlev çağrısı|Bağımsız değişken türü işaretli|
|-------------------|-----------------------------|
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|İlk bağımsız değişken (biçim dizesi)|
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|İlk iki bağımsız değişken (dosya veya arabellek ve biçim dizesini)|
|`_snprintf_s`|İlk üç bağımsız değişken (dosya veya arabellek sayısı ve biçim dizesi)|
|`_open`|İlk iki bağımsız değişken (yolu ve `_open` bayrağı)|
|`_sopen_s`|İlk üç bağımsız değişken (yol, `_open` bayrağı ve Paylaşım modu)|
|`_execl`, `_execle`, `_execlp`, `_execlpe`|İlk iki bağımsız değişken (yolu ve ilk bağımsız değişken işaretçi)|
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|İlk üç bağımsız değişken (modu bayrağını, yol ve ilk bağımsız değişken işaretçi)|

Derleyici, bu işlevlerin geniş karakter karşılıkları üzerinde aynı sınırlı tür gerçekleştirir.

## <a name="see-also"></a>Ayrıca Bkz.

[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)