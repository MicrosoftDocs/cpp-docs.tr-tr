---
title: NMAKE Önemli Hatası U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: 008d49df3460cb7cf760e4b278db20da444555fe
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182779"
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
