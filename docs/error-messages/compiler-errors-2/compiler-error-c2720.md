---
title: Derleyici hatası C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: 24f4329ee631eafc7c2670d9ebf28609c22e7592
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202149"
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
