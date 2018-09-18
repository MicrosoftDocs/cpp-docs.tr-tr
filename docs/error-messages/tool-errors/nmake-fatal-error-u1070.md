---
title: NMAKE önemli hatası U1070 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1070
dev_langs:
- C++
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6eb462e5c3c7e497cde55151bf92c62ffb2afcd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087025"
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE Önemli Hatası U1070

'makroadı' Makro tanımında döngü

Belirli bir Makro tanımında belirtilen Makro tanımında yer alan bir makro içeriyordu. Döngüsel makro tanımları geçersizdir.

## <a name="example"></a>Örnek

Aşağıdaki makro tanımları

```
ONE=$(TWO)
TWO=$(ONE)
```

Aşağıdaki hata neden:

```
cycle in macro definition 'TWO'
```