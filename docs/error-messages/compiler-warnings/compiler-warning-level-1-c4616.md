---
title: Derleyici Uyarısı (düzey 1) C4616
ms.date: 11/04/2016
f1_keywords:
- C4616
helpviewer_keywords:
- C4616
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
ms.openlocfilehash: fd36d0cdbcaaeca4f84ce85aa80f3bb1fba616a0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185912"
---
# <a name="compiler-warning-level-1-c4616"></a>Derleyici Uyarısı (düzey 1) C4616

\#pragma warning: uyarı numarası ' number ' geçerli bir derleyici uyarısı değil

[Uyarı](../../preprocessor/warning.md) pragması 'nda belirtilen uyarı numarası yeniden atanamaz. Pragma yoksayıldı.

Aşağıdaki örnek C4616 oluşturur:

```cpp
// C4616.cpp
// compile with: /W1 /c
#pragma warning( disable : 0 )   // C4616
#pragma warning( disable : 999 )   // OK
#pragma warning( disable : 4998 )   // OK
```
