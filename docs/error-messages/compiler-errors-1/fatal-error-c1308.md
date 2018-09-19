---
title: Önemli hata C1308 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1308
dev_langs:
- C++
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd778e95f3ace413dbeb409da3c4b2493208e8bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104194"
---
# <a name="fatal-error-c1308"></a>Önemli hata C1308

derlemelerin bağlanması desteklenmiyor

Bağlayıcı girişi olarak .netmodule izin verilir, ancak bir derleme değil. Bu hata ile derlenmiş bir bütünleştirilmiş kod bağlantı denemesi yapıldığında oluşturulabilir `/clr:safe`.

Daha fazla bilgi için [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).

Aşağıdaki örnek, C1308 oluşturur:

```
// C1308.cpp
// compile with: /clr:safe /LD
public ref class MyClass {
public:
   int i;
};
```

Ardından,

```
// C1308b.cpp
// compile with: /clr /link C1308b.obj C1308.dll
// C1308 expected
#using "C1308.dll"
int main() {
   MyClass ^ my = gcnew MyClass();
}
```