---
title: Bağlayıcı Araçları Uyarısı LNK4248
ms.date: 11/04/2016
f1_keywords:
- LNK4248
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
ms.openlocfilehash: 4ba05ef067c539dc9c0aca6dc2a395748fd217a2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988105"
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

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

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
