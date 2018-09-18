---
title: Derleyici Hatası C2868 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2868
dev_langs:
- C++
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2de22b34f9dc564ef89d7776af86718af70d51eb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037872"
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