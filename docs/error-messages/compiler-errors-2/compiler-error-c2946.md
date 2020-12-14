---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2946'
title: Derleyici hatası C2946
ms.date: 11/04/2016
f1_keywords:
- C2946
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
ms.openlocfilehash: 7a74b17c10acd55a254c0d7fba5c8269689e3094
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249509"
---
# <a name="compiler-error-c2946"></a>Derleyici hatası C2946

açık örnek oluşturma; ' class ', şablon sınıfı bir özelleştirme değil

Şablonlu olmayan bir sınıfı açıkça örnekleyemezsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2946 oluşturur.

```cpp
// C2946.cpp
class C {};
template C;  // C2946
int main() {}
```
