---
title: Derleyici hatası C2355
ms.date: 11/04/2016
f1_keywords:
- C2355
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
ms.openlocfilehash: e44501f7df05a8b277cd52107ff35c4c4d30578f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759951"
---
# <a name="compiler-error-c2355"></a>Derleyici hatası C2355

' this ': yalnızca statik olmayan üye işlevlerin veya statik olmayan veri üyesi başlatıcılarının içinde başvurulabilir

`this` işaretçi yalnızca statik olmayan üye işlevleri içinde veya statik olmayan veri üyesi başlatıcılarda geçerlidir. Bu hata, sınıf bildirimi dışında bir üye işlev tanımının sınıf kapsamı düzgün bir şekilde nitelenmediğinde oluşur. Hata, `this` işaretçisi sınıfında bildirilmemiş bir işlevde kullanıldığında da oluşabilir.

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
