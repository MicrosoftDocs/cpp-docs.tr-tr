---
description: 'Hakkında daha fazla bilgi edinin: tür denetimi (CRT)'
title: Tür Denetleme (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.types
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
ms.openlocfilehash: cf27847bf2aeef278fb4699cea5a0cf74a961086
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162365"
---
# <a name="type-checking-crt"></a>Tür Denetleme (CRT)

Derleyici, aşağıdaki gibi değişken sayıda bağımsız değişken alan işlevler üzerinde sınırlı tür denetimi gerçekleştirir:

|İşlev çağrısı|Tür denetimli bağımsız değişkenler|
|-------------------|-----------------------------|
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|İlk bağımsız değişken (biçim dizesi)|
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|İlk iki bağımsız değişken (dosya veya arabellek ve biçim dizesi)|
|`_snprintf_s`|İlk üç bağımsız değişken (dosya veya arabellek, sayı ve biçim dizesi)|
|`_open`|İlk iki bağımsız değişken (yol ve `_open` bayrak)|
|`_sopen_s`|İlk üç bağımsız değişken (yol, `_open` bayrak ve Paylaşım modu)|
|`_execl`, `_execle`, `_execlp`, `_execlpe`|İlk iki bağımsız değişken (yol ve ilk bağımsız değişken işaretçisi)|
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|İlk üç bağımsız değişken (mod bayrağı, yol ve ilk bağımsız değişken işaretçisi)|

Derleyici, bu işlevlerin geniş karakterli karşılıklarıyla aynı sınırlı tür denetimini gerçekleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)
