---
title: Derleyici Hatası C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 4406aa90b26bc517308132ae9cccd003d44a9aad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408465"
---
# <a name="compiler-error-c2577"></a>Derleyici Hatası C2577

'member': yıkıcı/Sonlandırıcı dönüş türüne sahip olamaz

Yıkıcı veya Sonlandırıcı değerini döndüremez `void` veya diğer herhangi bir türü. Kaldırma `return` yok Edicisi tanımından deyimi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2577 oluşturur.

```
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```