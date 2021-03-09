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
ms.openlocfilehash: 9afb4146f7bbd08b35df20972345285bb353e4d3
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514232"
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

[C çalışma zamanı (CRT) ve C++ standart kitaplığı (STL) `.lib` dosyaları](../c-runtime-library/crt-library-features.md)
