---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4612'
title: Derleyici Uyarısı (düzey 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: 2844b54c592f5c4c4817cfec97d57c41fa2055b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341730"
---
# <a name="compiler-warning-level-1-c4612"></a>Derleyici Uyarısı (düzey 1) C4612

> içerme dosya adında hata

## <a name="remarks"></a>Açıklamalar

Bu uyarı, bir dosya adı yanlış veya eksik olduğunda **#pragma include_alias** ile oluşur.

**#Pragma include_alias** deyimin bağımsız değişkenleri tırnak formunu ("*filename*") veya açılı ayraç formunu ( \<*filename*> ) kullanabilir, ancak her ikisi de aynı formu kullanmalıdır.

## <a name="example"></a>Örnek

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```
