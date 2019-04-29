---
title: NMAKE Önemli Hatası U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: 35bea47f6626dfe283a537d3d96340921c37f3f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367245"
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