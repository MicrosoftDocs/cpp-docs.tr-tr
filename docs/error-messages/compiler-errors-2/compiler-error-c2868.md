---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2868'
title: Derleyici hatası C2868
ms.date: 11/04/2016
f1_keywords:
- C2868
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
ms.openlocfilehash: c6a6368fbdfe61014a606fadce92322234e438f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333798"
---
# <a name="compiler-error-c2868"></a>Derleyici hatası C2868

> '*tanımlayıcı*': using bildirimi için geçersiz sözdizimi; tam ad bekleniyor

[Using bildirimi](../../cpp/using-declaration.md) , tanımlayıcı adı ile biten bir ad alanı, sınıf veya sabit listesi adı için bir *tam ad*, kapsam işleci ( `::` ) ayrılmış bir dizi gerektirir. Genel ad alanından bir ad tanıtmak için tek bir kapsam çözümleme işleci kullanılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2868 oluşturur ve ayrıca doğru kullanımı gösterir:

```cpp
// C2868.cpp
class X {
public:
   int i;
};

class Y : X {
public:
   using X::i;   // OK
};

int main() {
   using X;   // C2868
}
```
