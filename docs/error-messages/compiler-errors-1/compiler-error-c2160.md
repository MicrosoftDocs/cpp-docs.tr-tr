---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2160'
title: Derleyici hatası C2160
ms.date: 11/04/2016
f1_keywords:
- C2160
helpviewer_keywords:
- C2160
ms.assetid: a1f694a7-fb16-4437-b7f5-a1af6da94bc5
ms.openlocfilehash: 84c257fc249d136c495adbcb22cd59701d6c363c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181195"
---
# <a name="compiler-error-c2160"></a>Derleyici hatası C2160

' # # ' makro tanımının başlangıcında oluşamaz

Makro tanımı, belirteç yapıştırma işleci (# #) ile başladı.

Aşağıdaki örnek C2160 oluşturur:

```cpp
// C2160.cpp
// compile with: /c
#define mac(a,b) #a   // OK
#define mac(a,b) ##a   // C2160
```
