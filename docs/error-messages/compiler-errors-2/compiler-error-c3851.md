---
title: Derleyici Hatası C3851 | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6d0f6da9c3295aa6a8fad4bf5dfd8e725424739
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032497"
---
# <a name="compiler-error-c3851"></a>Derleyici Hatası C3851

> '*char*': bir evrensel karakter adı temel karakter kümesindeki bir karakteri belirtemez

## <a name="remarks"></a>Açıklamalar

C++ derlenmiş kod içinde bir karakter, temel kaynak karakter kümesi dışında bir dize veya karakter sabiti temsil eden bir evrensel karakter adı kullanamazsınız. Daha fazla bilgi için [karakter kümesi](../../cpp/character-sets.md). C derlenmiş kodda, bir evrensel karakter adı karakterleri aralığında 0x20 0x7f, kapsamlı 0x24 ('$')'hariç 0x40 kullanamazsınız ('\@'), veya 0x60 ('\`').

## <a name="example"></a>Örnek

Aşağıdaki örnekleri C3851 oluşturmak ve bu sorunun nasıl göster:

```cpp
// C3851.cpp
int main()
{
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set
   int test2_A = 0;        // OK
}
```