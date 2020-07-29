---
title: Derleyici hatası C2355
ms.date: 11/04/2016
f1_keywords:
- C2355
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
ms.openlocfilehash: 4e78d20fb59beead08aaddcf85138f845cfc0390
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212767"
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
