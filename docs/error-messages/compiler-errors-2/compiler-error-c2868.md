---
title: Derleyici Hatası C2868
ms.date: 11/04/2016
f1_keywords:
- C2868
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
ms.openlocfilehash: 4cb259ed0f43831226fb7e1a1ccf7b28bcef7819
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165209"
---
# <a name="compiler-error-c2868"></a>Derleyici Hatası C2868

> '*tanımlayıcı*': kullanma bildirimi için geçersiz sözdizimi; tam ad bekleniyor

A [using bildirimi](../../cpp/using-declaration.md) gerektiren bir *tam adı*, kapsam işleci (`::`) tanımlayıcı adı ile biten ad alanı, sınıf veya numaralandırma adları dizisi ayrılmış. Tek bir kapsam çözümleme işleci, bir adı genel ad alanından tanıtmak için kullanılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2868 oluşturur ve ayrıca doğru kullanımını gösterir:

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