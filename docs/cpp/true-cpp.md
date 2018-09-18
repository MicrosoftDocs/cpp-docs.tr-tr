---
title: TRUE (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- true_cpp
dev_langs:
- C++
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e43fbfd9b3cff9ea617238ed7b4cccd08f780cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018710"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>Sözdizimi

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>Açıklamalar

İki değer türünde bir değişken için bu anahtar sözcük biridir [bool](../cpp/bool-cpp.md) ya da bir koşullu ifade (bir koşullu ifade, artık doğru bir Boole ifadesi). Varsa `i` türünde **bool**, then deyimi `i = true;` atar **true** için `i`.

## <a name="example"></a>Örnek

```cpp
// bool_true.cpp
#include <stdio.h>
int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)