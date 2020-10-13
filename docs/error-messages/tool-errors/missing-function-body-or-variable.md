---
title: Eksik İşlev Gövdesi veya Değişken
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: 835bd968035b355ded9636d446d44d4ce069c248
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008882"
---
# <a name="missing-function-body-or-variable"></a>Eksik İşlev Gövdesi veya Değişken

Yalnızca bir işlev prototipi ile derleyici hatasız devam edebilir, ancak hiçbir işlev kodu veya değişken alanı ayrıldığından bağlayıcı bir adrese çağrıyı çözemez. Bağlayıcının çözümlenmesi gereken işleve bir çağrı oluşturana kadar bu hatayı görmezsiniz.

## <a name="example-call-to-an-undefined-function"></a>Örnek: tanımsız bir işleve çağrı

Prototip derleyicinin var olduğunu düşünmesine izin verdiğinden Main içindeki işlev çağrısı LNK2019 neden olur.  Bağlayıcı, olduğunu bulur.

```cpp
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example-call-to-an-implemented-function"></a>Örnek: uygulanan bir işleve çağrı

C++ ' da, sınıf tanımında yalnızca bir prototipi değil, bir sınıf için belirli bir işlevin uygulamasını eklediğinizden emin olun. Sınıfı üstbilgi dosyasının dışında tanımlıyorsanız, işlevden () önce sınıf adını eklediğinizden emin olun `Classname::memberfunction` .

```cpp
// LNK2019_MFBV_2.cpp
// LNK2019 expected
struct A {
   static void Test();
};

// Should be void A::Test() {}
void Test() {}

int main() {
   A AObject;
   AObject.Test();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
