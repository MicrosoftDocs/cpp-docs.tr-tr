---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2612'
title: Derleyici hatası C2612
ms.date: 11/04/2016
f1_keywords:
- C2612
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
ms.openlocfilehash: 34ff229f493ccbab8c41e011caaabea818d79de9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338678"
---
# <a name="compiler-error-c2612"></a>Derleyici hatası C2612

Sondaki ' Char ' taban/üye Başlatıcı listesinde geçersizdir

Bir Başlatıcı listesindeki son tabanın veya üyenin bir karakteri görüntülenir.

Aşağıdaki örnek C2612 oluşturur:

```cpp
// C2612.cpp
class A {
public:
   int i;
   A( int ia ) : i( ia ) + {};   // C2612
};
```
