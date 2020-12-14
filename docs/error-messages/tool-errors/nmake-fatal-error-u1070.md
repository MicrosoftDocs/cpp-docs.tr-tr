---
description: 'Hakkında daha fazla bilgi edinin: NMAKE önemli hatası U1070'
title: NMAKE Önemli Hatası U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: a3d0ee448062fec8a024501b0c08d5f0466d974b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283530"
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE Önemli Hatası U1070

' makroadı ' makro tanımında döngüye

Verilen makro tanımı, tanımı verilen makroyu içeren bir makro içeriyordu. Döngüsel makro tanımları geçersiz.

## <a name="example"></a>Örnek

Aşağıdaki makro tanımları

```
ONE=$(TWO)
TWO=$(ONE)
```

Şu hataya neden olur:

```
cycle in macro definition 'TWO'
```
