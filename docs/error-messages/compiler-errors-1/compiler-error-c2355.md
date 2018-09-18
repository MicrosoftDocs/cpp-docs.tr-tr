---
title: Derleyici Hatası C2355 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2355
dev_langs:
- C++
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 456049c60ce39fce3cdbf04512f306027e30db25
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035194"
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