---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2779'
title: Derleyici hatası C2779
ms.date: 11/04/2016
f1_keywords:
- C2779
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
ms.openlocfilehash: 88acf83feb7a5aece8f05431eec7c70869cba6a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298051"
---
# <a name="compiler-error-c2779"></a>Derleyici hatası C2779

' declaration ': Özellik yöntemleri yalnızca statik olmayan veri üyeleriyle ilişkilendirilebilir

**`property`** Genişletilmiş öznitelik bir statik veri üyesine yanlış uygulandı.

Aşağıdaki örnek C2779 oluşturur:

```cpp
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```
