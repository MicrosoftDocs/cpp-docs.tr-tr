---
title: Derleyici Hatası C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: c6499fd3f279099ea7c5b31860e70bdaa285e3f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383054"
---
# <a name="compiler-error-c2720"></a>Derleyici Hatası C2720

> '*tanımlayıcı*': '*belirticisi*' depolama sınıfı belirticisi üyelerde geçersizdir

Depolama sınıfı sınıf üyesi bildirim dışında kullanılamaz. Bu hatayı düzeltmek için gereksiz kaldırmak [depolama sınıfı](../../cpp/storage-classes-cpp.md) üyenin sınıf bildirimi dışında tanımından tanımlayıcısı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2720 oluşturur ve bu sorunun nasıl gösterir:

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```