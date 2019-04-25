---
title: Derleyici Hatası C2756
ms.date: 11/04/2016
f1_keywords:
- C2756
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
ms.openlocfilehash: ccbbb7875fdae48fd00f87f9a63f3764c143daae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227790"
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