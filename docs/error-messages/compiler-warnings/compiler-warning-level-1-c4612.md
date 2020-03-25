---
title: Derleyici Uyarısı (düzey 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: f9478caef9eaba9c72dc282179100daf2d94c6d5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185990"
---
# <a name="compiler-warning-level-1-c4612"></a>Derleyici Uyarısı (düzey 1) C4612

> içerme dosya adında hata

## <a name="remarks"></a>Açıklamalar

Bu uyarı, bir dosya adı yanlış veya eksik olduğunda **#pragma include_alias** ile oluşur.

**#Pragma include_alias** deyimin bağımsız değişkenleri tırnak formunu ("*filename*") veya açılı ayraç formunu (\<*dosya adı*>) kullanabilir, ancak her ikisi de aynı formu kullanmalıdır.

## <a name="example"></a>Örnek

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```
