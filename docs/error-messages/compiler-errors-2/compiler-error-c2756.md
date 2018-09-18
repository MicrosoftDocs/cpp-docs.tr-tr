---
title: Derleyici Hatası C2756 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2756
dev_langs:
- C++
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 252f212f9034151bc5e77d1d2d6e64e1ee388faa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061220"
---
# <a name="compiler-error-c2756"></a>Derleyici Hatası C2756

'şablon türü': varsayılan şablon bağımsız değişkenlerinin kısmi özelleştirmede izin verilmez

Şablonu kısmi özelleştirmesi için varsayılan bağımsız değişken içeremez.

Aşağıdaki örnek, C2756 oluşturur ve bu sorunun nasıl gösterir:

```
// C2756.cpp
template <class T>
struct S {};

template <class T=int>
// try the following line instead
// template <class T>
struct S<T*> {};   // C2756
```