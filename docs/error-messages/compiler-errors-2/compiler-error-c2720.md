---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2720'
title: Derleyici hatası C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: 187142af02289374235725340a206f35b6a42493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155663"
---
# <a name="compiler-error-c2720"></a>Derleyici hatası C2720

> '*tanımlayıcı*': '*belirtici*' depolama sınıfı belirticisi üyelerde geçersizdir

Depolama sınıfı, bildirim dışındaki sınıf üyelerinde kullanılamaz. Bu hatayı onarmak için, gereksiz [depolama sınıfı](../../cpp/storage-classes-cpp.md) belirticisini sınıf bildiriminin dışındaki üyenin tanımından kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2720 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```
