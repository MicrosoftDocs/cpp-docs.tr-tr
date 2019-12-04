---
title: Derleyici hatası C2755
ms.date: 11/04/2016
f1_keywords:
- C2755
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
ms.openlocfilehash: fcd4bb5d49f6f6e807ad240c377debb220138c93
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759561"
---
# <a name="compiler-error-c2755"></a>Derleyici hatası C2755

' param ': kısmi özelleşmenin tür olmayan parametresi basit bir tanımlayıcı olmalıdır

Tür olmayan parametrenin bir basit tanımlayıcı olması gerekir. derleyicinin derleme zamanında tek bir tanımlayıcıya veya sabit bir değere çözebileceği bir şeydir.

Aşağıdaki örnek C2755 oluşturur:

```cpp
// C2755.cpp
template<int I, int J>
struct A {};

template<int I>
struct A<I,I*5> {};   // C2755
// try the following line instead
// struct A<I,5> {};
```
