---
title: Derleyici Hatası C2355
ms.date: 11/04/2016
f1_keywords:
- C2355
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
ms.openlocfilehash: 80871a73a7c3b4ad04b475539015f85d21ae88b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302650"
---
# <a name="compiler-error-c2355"></a>Derleyici Hatası C2355

'this': yalnızca statik olmayan üye işlevlerin veya statik olmayan veri üyesi başlatıcıları içinde başvurulabilir

`this` İşaretçisidir yalnızca statik olmayan üye işlevleri veya statik olmayan veri üyesi başlatıcıları geçerli. Sınıf bildirimi dışında bir üye işlev tanımının sınıf kapsamı düzgün nitelendirilmiş olduğunda bu hatayı neden olabilir. Hata olduğunda `this` işaretçi sınıfta bildirilen olmayan bir işlev kullanılır.

Bu sorunu gidermek için bir sınıfın üye işlevi bildiriminde üye işlev tanımının eşleşir ve bu statik bildirilmedi, emin olun. Veri üyesi başlatıcıları için veri üyesi statik bildirilmedi emin olun.

Aşağıdaki örnek, C2355 oluşturur ve bu sorunun nasıl gösterir:

```
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