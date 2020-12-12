---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4086'
title: Derleyici Uyarısı (düzey 1) C4086
ms.date: 11/04/2016
f1_keywords:
- C4086
helpviewer_keywords:
- C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
ms.openlocfilehash: e2bb38d781a18b98a386e17ccdb347be9fe0f0df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278123"
---
# <a name="compiler-warning-level-1-c4086"></a>Derleyici Uyarısı (düzey 1) C4086

pragma parametresinin ' 1 ', ' 2 ', ' 4 ', ' 8 ' veya ' 16 ' olması bekleniyor

Pragma parametresi gerekli değere (1, 2, 4, 8 veya 16) sahip değil.

## <a name="example"></a>Örnek

```cpp
// C4086.cpp
// compile with: /W1 /LD
#pragma pack( 3 ) // C4086
```
