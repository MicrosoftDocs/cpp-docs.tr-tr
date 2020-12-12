---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4661'
title: Derleyici Uyarısı (düzey 1) C4661
ms.date: 11/04/2016
f1_keywords:
- C4661
helpviewer_keywords:
- C4661
ms.assetid: 603bb8b7-356d-4eef-924b-64d769bac5bd
ms.openlocfilehash: 401f9a7229b4eec1f6484c49b6d2b1a18d8c49f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318838"
---
# <a name="compiler-warning-level-1-c4661"></a>Derleyici Uyarısı (düzey 1) C4661

' tanımlayıcı ': açık şablon örneği oluşturma isteği için uygun bir tanım belirtilmedi

Şablon sınıfının bir üyesi tanımlı değil.

## <a name="example"></a>Örnek

```cpp
// C4661.cpp
// compile with: /W1 /LD
template<class T> class MyClass {
public:
   void i();   // declaration but not definition
};
template MyClass< int >;  // C4661
```
