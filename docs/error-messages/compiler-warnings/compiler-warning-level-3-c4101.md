---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4101'
title: Derleyici Uyarısı (düzey 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: c5e358bea4e9a584242376ed86d1bb5af2deb734
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150637"
---
# <a name="compiler-warning-level-3-c4101"></a>Derleyici Uyarısı (düzey 3) C4101

' tanımlayıcı ': başvurulmayan yerel değişken

Yerel değişken hiç kullanılmıyor. Bu uyarı belirgin durumda gerçekleşir:

```cpp
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

Ancak, bu uyarı, bir **`static`** üye işlevi sınıfın bir örneği aracılığıyla çağrılırken de gerçekleşir:

```cpp
// C4101b.cpp
// compile with:  /W3
struct S {
   static int func()
   {
      return 1;
   }
};

int main() {
   S si;   // C4101, si is never used
   int y = si.func();
   return y;
}
```

Bu durumda, derleyici `si` işlevine erişmek için bilgisini kullanır **`static`** , ancak sınıfının örneği işlevi çağırmak için gerekli değildir **`static`** ; Bu nedenle uyarı. Bu uyarıyı çözmek için şunları yapabilirsiniz:

- İçinde derleyicinin çağrısını kullanacağı bir Oluşturucu ekleyin `si` `func` .

- **`static`** Anahtar sözcüğünü öğesinin tanımından Kaldır `func` .

- **`static`** İşlevi açıkça çağırın: `int y = S::func();` .
