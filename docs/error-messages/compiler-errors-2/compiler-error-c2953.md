---
title: Derleyici Hatası C2953
ms.date: 11/04/2016
f1_keywords:
- C2953
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
ms.openlocfilehash: 8fa0e533b23f735f948fdad0ecf11beb3766f452
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187646"
---
# <a name="compiler-error-c2953"></a>Derleyici Hatası C2953

'identifier': sınıf şablonu zaten tanımlanmış

Kaynak dosyasını denetleyin ve diğer tanımları için dosyaları içerir.

Aşağıdaki örnek, C2953 oluşturur:

```
// C2953.cpp
// compile with: /c
template <class T>  class A {};
template <class T>  class A {};   // C2953
template <class T>  class B {};   // OK
```