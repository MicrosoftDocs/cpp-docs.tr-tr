---
title: "Derleyici Uyarısı (düzey 1) C4305 | Microsoft Docs"
ms.custom: 
ms.date: 1/17/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4305
dev_langs:
- C++
helpviewer_keywords:
- C4305
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fe4b2b420c44584fdd5b4d48b4264bbc7a51bee
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
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
