---
title: Bağlayıcı araçları uyarısı LNK4248 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4248
dev_langs:
- C++
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ff2c3edd942eb0d38d16a6986044f90358c4e9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062169"
---
# <a name="linker-tools-warning-lnk4248"></a>Bağlayıcı Araçları Uyarısı LNK4248

çözümlenemeyen typeref belirteci (belirteç) için 'type'; Görüntü çalışmayabilir

Bir tür tanımı MSIL meta verilerde yok.

LNK4248 İleri dönük bildiriminin bir MSIL modülü türü için yalnızca olduğunda meydana gelebilir (ile derlenmiş **/CLR**), MSIL modülü içinde başvurulan türü olduğunda ve bir MSIL modülü için bir tanıma sahip yerel bir modül ile bağlantılı olduğunda türü.

Bu durumda, MSIL meta veriler yerel tür tanımında bağlayıcı veririz ve bu doğru davranışı sağlayabilir.

İleriye doğru tür bildirimi bir CLR türü ise, ancak ardından bağlayıcı'nın yerel bir tür tanımı doğru olmayabilir

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Bir MSIL modülü tür tanımında sağlar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK4248 oluşturur. Çözümlenecek bir yapı tanımlar.

```
// LNK4248.cpp
// compile with: /clr /W1
// LNK4248 expected
struct A;
void Test(A*){}

int main() {
   Test(0);
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir tür ileriye doğru bir tanımı içeriyor.

```
// LNK4248_2.cpp
// compile with: /clr /c
class A;   // provide a definition for A here to resolve
A * newA();
int valueA(A * a);

int main() {
   A * a = newA();
   return valueA(a);
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK4248 oluşturur.

```
// LNK4248_3.cpp
// compile with: /c
// post-build command: link LNK4248_2.obj LNK4248_3.obj
class A {
public:
   int b;
};

A* newA() {
   return new A;
}

int valueA(A * a) {
   return (int)a;
}
```