---
title: Derleyici Hatası C2913 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2913
dev_langs:
- C++
helpviewer_keywords:
- C2913
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6da5d739c4dd9ccec71c26a3fc9101cde1535ce3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103132"
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