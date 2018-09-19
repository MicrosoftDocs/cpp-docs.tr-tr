---
title: Derleyici Uyarısı (düzey 1) C4305 | Microsoft Docs
ms.custom: ''
ms.date: 1/17/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4305
dev_langs:
- C++
helpviewer_keywords:
- C4305
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88ae0fb38b7e6af14525906e90486a68ce22ee56
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086830"
---
# <a name="compiler-warning-level-1-c4305"></a>Derleyici Uyarısı (düzey 1) C4305

> '*bağlam*': kesildi '*type1*'to'*type2*'

## <a name="remarks"></a>Açıklamalar

Bu uyarı, bilgi kaybına kaynaklanan bir küçük türüne bir başlatma veya bir oluşturucu bağımsız değişkeni olarak bir değere dönüştürüldüğünde görüntülenir.

## <a name="example"></a>Örnek

Bu örnek gösterir iki yolu bu uyarı görebilirsiniz:

```cpp
// C4305.cpp
// Compile by using: cl /EHsc /W4 C4305.cpp

struct item
{
    item(float) {}
};

int main()
{
    float f = 2.71828;          // C4305 'initializing'
    item i(3.14159);            // C4305 'argument'
    return static_cast<int>(f);
}
```

Bu sorunu gidermek için doğru türde bir değer kullanarak başlatmak veya doğru tür açık bir tür dönüştürme kullanın. Örneğin, bir **float** değişmez değer yerine 2.71828f gibi bir **çift** (varsayılan kayan noktalı sabit değerleri türü) başlatmak için bir **float** değişkeni veya geçirmek için bir alan oluşturucu bir **float** bağımsız değişken.
