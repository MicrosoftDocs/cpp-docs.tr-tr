---
title: Bağlayıcı Araçları Uyarısı LNK4248
ms.date: 11/04/2016
f1_keywords:
- LNK4248
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
ms.openlocfilehash: 81f3c2abc41673e6e4c9e3f59ff1dd515e1cf365
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685431"
---
# <a name="linker-tools-warning-lnk4248"></a>Bağlayıcı Araçları Uyarısı LNK4248

çözümlenmemiş TypeRef belirteci (belirteç), ' Type ' için görüntü çalışmayabilir

Bir türün MSIL meta verilerinde bir tanımı yok.

LNK4248, bir MSIL modülünde ( **/clr**ile derlenen) bir tür için yalnızca bir iletme bildirimi olduğunda ve türü MSIL modülünde başvurulduğu ve MSIL modülünün tür tanımına sahip bir yerel modülle bağlantılı olduğu durumlarda gerçekleşebilir.

Bu durumda bağlayıcı, MSIL meta verilerinde yerel tür tanımı sağlar ve bu durum doğru davranış sağlayabilir.

Ancak, bir iletme türü bildirimi bir CLR türü ise, bağlayıcının yerel tür tanımı doğru olmayabilir

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. MSIL modülünde tür tanımını belirtin.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek LNK4248 oluşturur. Çözümlemek için A yapısını tanımlayın.

```cpp
// LNK4248.cpp
// compile with: /clr /W1
// LNK4248 expected
struct A;
void Test(A*){}

int main() {
   Test(0);
}
```

Aşağıdaki örnek bir türün ileri tanımına sahiptir.

```cpp
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

Aşağıdaki örnek LNK4248 oluşturur.

```cpp
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
