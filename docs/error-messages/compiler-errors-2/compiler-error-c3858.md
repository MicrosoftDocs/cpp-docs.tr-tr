---
title: Derleyici Hatası C3858
ms.date: 11/04/2016
f1_keywords:
- C3858
helpviewer_keywords:
- C3858
ms.assetid: 46e178d5-a55f-4ac6-a9dc-561fbcba5c1f
ms.openlocfilehash: b4246ba76b453e8cc841062a4184dc2cb02df479
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438681"
---
# <a name="compiler-error-c3858"></a>Derleyici Hatası C3858

'type': geçerli kapsamda bildirilemez

Tür iki kez aynı kapsamda bildirilemez.

Aşağıdaki örnek, C3858 oluşturur:

```
// C3858.cpp
// compile with: /LD
template <class T>
struct Outer
{
   struct Inner;
};

template <class T>
struct Outer<T>::Inner;   // C3858
// try the following line instead
// struct Outer<T>::Inner{};
```