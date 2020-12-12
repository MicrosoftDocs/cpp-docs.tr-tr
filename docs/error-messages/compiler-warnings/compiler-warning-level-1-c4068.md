---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4068'
title: Derleyici Uyarısı (düzey 1) C4068
ms.date: 11/04/2016
f1_keywords:
- C4068
helpviewer_keywords:
- C4068
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
ms.openlocfilehash: 03a60c1a26f38183fa191665a8a9566b9dd2915d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267644"
---
# <a name="compiler-warning-level-1-c4068"></a>Derleyici Uyarısı (düzey 1) C4068

bilinmeyen pragma

Derleyici tanınmayan bir [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)yoksaydı. Kullanmakta olduğunuz derleyicinin **pragmaya** izin verildiğinden emin olun. Aşağıdaki örnek C4068 oluşturur:

```cpp
// C4068.cpp
// compile with: /W1
#pragma NotAValidPragmaName   // C4068, use valid name to resolve
int main()
{
}
```
