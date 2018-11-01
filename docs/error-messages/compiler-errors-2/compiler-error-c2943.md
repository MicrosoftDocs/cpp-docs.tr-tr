---
title: Derleyici Hatası C2943
ms.date: 11/04/2016
f1_keywords:
- C2943
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
ms.openlocfilehash: 53340611ef92aac7c9bed30f364fed424fdfe140
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469539"
---
# <a name="compiler-error-c2943"></a>Derleyici Hatası C2943

'class': türü sınıf kimliği için bir şablon bir tür bağımsız değişkeni yeniden tanımlandı

Bir sembol yerine, genel veya Şablon sınıfı, bir genel veya şablon türü bağımsız değişken olarak kullanamazsınız.

Aşağıdaki örnek, C2943 oluşturur:

```
// C2943.cpp
// compile with: /c
template<class T>
class List {};

template<class List<int> > class MyList;   // C2943
template<class T >  class MyList;
```