---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3553'
title: Derleyici hatası C3553
ms.date: 11/04/2016
f1_keywords:
- C3553
helpviewer_keywords:
- C3553
ms.assetid: 7f84bf37-6419-4ad3-ab30-64266100b930
ms.openlocfilehash: 43e322b78bac05f6e301501a86ce7fbd2f27d285
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223223"
---
# <a name="compiler-error-c3553"></a>Derleyici hatası C3553

> decltype bir tür değil ifadesi bekliyor

`decltype()`Anahtar sözcüğü bir tür adı değil bağımsız değişken olarak bir ifade gerektirir. Örneğin, aşağıdaki kod parçasındaki son ifade hata C3553 verir.

```cpp
int x = 0;
decltype(x+1);
decltype(int); // C3553
```
