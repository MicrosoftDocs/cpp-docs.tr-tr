---
title: Derleyici Hatası C2913
ms.date: 11/04/2016
f1_keywords:
- C2913
helpviewer_keywords:
- C2913
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
ms.openlocfilehash: deeabdb08f4b0fb3cd722d5d33a4d2cfffb15d61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256953"
---
# <a name="compiler-error-c2913"></a>Derleyici Hatası C2913

Açık özelleştirme; 'bildirim' sınıf şablonunun bir özelleştirmesi değil

Bir şablon olmayan sınıf özelleştirilemiyor.

Aşağıdaki örnek, C2913 oluşturur:

```
// C2913.cpp
// compile with: /c
class X{};
template <class T> class Y{};

template<> class X<int> {};   // C2913
template<> class Y<int> {};
```