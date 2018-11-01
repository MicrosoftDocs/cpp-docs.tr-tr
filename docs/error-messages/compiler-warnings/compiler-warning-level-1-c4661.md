---
title: Derleyici Uyarısı (düzey 1) C4661
ms.date: 11/04/2016
f1_keywords:
- C4661
helpviewer_keywords:
- C4661
ms.assetid: 603bb8b7-356d-4eef-924b-64d769bac5bd
ms.openlocfilehash: 7566ba3d1db8e15d2919904d3dc2316e10a7ff59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637430"
---
# <a name="compiler-warning-level-1-c4661"></a>Derleyici Uyarısı (düzey 1) C4661

'identifier': açık şablon örneği oluşturma isteği için sağlanan uygun bir tanım

Şablon sınıfının üye tanımlanmadı.

## <a name="example"></a>Örnek

```
// C4661.cpp
// compile with: /W1 /LD
template<class T> class MyClass {
public:
   void i();   // declaration but not definition
};
template MyClass< int >;  // C4661
```