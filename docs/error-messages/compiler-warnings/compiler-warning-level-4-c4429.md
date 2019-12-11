---
title: Derleyici Uyarısı (düzey 4) C4429
ms.date: 11/04/2016
f1_keywords:
- C4429
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
ms.openlocfilehash: 6702db4af5c31d21610e02b1a4ec75af27ad10f2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990832"
---
# <a name="compiler-warning-level-4-c4429"></a>Derleyici Uyarısı (düzey 4) C4429

tamamlanmamış veya hatalı biçimlendirilmiş evrensel karakter adı olabilir

Derleyici hatalı biçimlendirilmiş bir evrensel karakter adı olabilecek bir karakter sırası algıladı. Bir evrensel karakter adı, `\u` sonrasında dört onaltılık basamak, sonra sekiz onaltılık basamak `\U`.

Aşağıdaki örnek C4429 oluşturur:

```cpp
// C4429.cpp
// compile with: /W4 /WX
int \ug0e4 = 0;   // C4429
// Try the following line instead:
// int \u00e4 = 0;   // OK, a well-formed universal character name.
```
