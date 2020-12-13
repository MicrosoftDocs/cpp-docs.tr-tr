---
description: 'Daha fazla bilgi edinin: önemli hata C1308'
title: Önemli hata C1308
ms.date: 11/04/2016
f1_keywords:
- C1308
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
ms.openlocfilehash: 9d9b8cee128b9ed830c4ba3651ee609d91d42eac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177880"
---
# <a name="fatal-error-c1308"></a>Önemli hata C1308

derlemelerin bağlanması desteklenmiyor

Bir. netmodule 'e giriş olarak izin verilir, ancak bir derleme değildir. Bu hata, ile derlenen bir derlemeyi bağlamak için bir deneme yapıldığında oluşturulabilir `/clr:safe` .

Daha fazla bilgi için, bkz [.. netmodule dosyaları bağlayıcı girişi olarak](../../build/reference/netmodule-files-as-linker-input.md).

Aşağıdaki örnek C1308 oluşturur:

```cpp
// C1308.cpp
// compile with: /clr:safe /LD
public ref class MyClass {
public:
   int i;
};
```

ardından,

```cpp
// C1308b.cpp
// compile with: /clr /link C1308b.obj C1308.dll
// C1308 expected
#using "C1308.dll"
int main() {
   MyClass ^ my = gcnew MyClass();
}
```
