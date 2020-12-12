---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2355'
title: Derleyici hatası C2355
ms.date: 11/04/2016
f1_keywords:
- C2355
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
ms.openlocfilehash: f28799d4fbd72c7a5959bc4c68e1810b26052844
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328381"
---
# <a name="compiler-error-c2355"></a>Derleyici hatası C2355

' this ': yalnızca statik olmayan üye işlevlerin veya statik olmayan veri üyesi başlatıcılarının içinde başvurulabilir

**`this`** İşaretçi yalnızca statik olmayan üye işlevleri içinde veya statik olmayan veri üyesi başlatıcılarında geçerlidir. Bu hata, sınıf bildirimi dışında bir üye işlev tanımının sınıf kapsamı düzgün bir şekilde nitelenmediğinde oluşur. Bu hata, **`this`** işaretçi sınıfında bildirilmemiş bir işlevde kullanıldığında da oluşabilir.

Bu sorunu onarmak için, üye işlev tanımının sınıftaki bir üye işlev bildirimiyle eşleştiğinden ve statik olarak bildirilmemiş olduğundan emin olun. Veri üyesi başlatıcıları için, veri üyesinin statik olarak bildirilmemiş olduğundan emin olun.

Aşağıdaki örnek C2355 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2355.cpp
// compile with: /c
class MyClass {};
MyClass *p = this;   // C2355

// OK
class MyClass2 {
public:
   void Test() {
      MyClass2 *p = this;
   }
};
```
