---
title: Derleyici hatası C2868
ms.date: 11/04/2016
f1_keywords:
- C2868
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
ms.openlocfilehash: 0cbcf7dc80aedc554594f88992059f98b7091c21
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201648"
---
# <a name="compiler-error-c2868"></a>Derleyici hatası C2868

> '*tanımlayıcı*': using bildirimi için geçersiz sözdizimi; tam ad bekleniyor

[Using bildirimi](../../cpp/using-declaration.md) , tanımlayıcı adı ile biten bir kapsam işleci (`::`) ayrılmış bir ad alanı, sınıf veya numaralandırma adları dizisi için *nitelenmiş bir ad*gerektirir. Genel ad alanından bir ad tanıtmak için tek bir kapsam çözümleme işleci kullanılabilir.

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
