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
ms.openlocfilehash: 7694c511f57b6907227d62f969b61218f836cb14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277829"
---
# <a name="compiler-warning-level-1-c4305"></a>Derleyici Uyarısı (düzey 1) C4305

> '*bağlamı*': gelen kesilmesi '*type1*'to'*type2*'  

## <a name="remarks"></a>Açıklamalar

Bu uyarı, bilgi kaybına neden bir küçük türüne bir başlatma veya bir oluşturucu bağımsız değişkeni olarak bir değere dönüştürüldüğünde görüntülenir.

## <a name="example"></a>Örnek

Bu örnek iki yolla bu uyarı görebilirsiniz gösterir:

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

Bu sorunu gidermek için doğru türde bir değer kullanarak başlatmak veya doğru türü için bir açık atama kullanın. Örneğin, bir **float** değişmez değer yerine 2.71828f gibi bir **çift** (kayan nokta değişmez değerleri için varsayılan türü) başlatmak için bir **float** , değişken veya geçirilecek bir alan oluşturucu bir **float** bağımsız değişkeni.
