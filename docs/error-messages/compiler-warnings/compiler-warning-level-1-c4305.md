---
title: Derleyici Uyarısı (düzey 1) C4305
ms.date: 01/17/2018
f1_keywords:
- C4305
helpviewer_keywords:
- C4305
ms.openlocfilehash: dc718e5f7ebe9478ed1bf2a7323db940935cb1d6
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926119"
---
# <a name="compiler-warning-level-1-c4305"></a>Derleyici Uyarısı (düzey 1) C4305

> '*Context*': '*Type1*' öğesinden '*type2*' öğesine kesildi

## <a name="remarks"></a>Açıklamalar

Bu uyarı, bir değer bir başlatma içinde daha küçük bir türe dönüştürüldüğünde veya Oluşturucu bağımsız değişkeni olarak bilgi kaybına neden olduğunda verilir.

## <a name="example"></a>Örnek

Bu örnek, bu uyarıyı görmenizin iki yolunu göstermektedir:

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

Bu sorunu düzeltmek için doğru türdeki bir değeri kullanarak başlatın veya doğru türe açık bir tür dönüştürme kullanın. Örneğin, bir **float** değişkeni başlatmak için ya da **float bağımsız değişkeni alan bir oluşturucuya** geçiş yapmak için **Double** (kayan nokta değişmez değerleri için varsayılan tür) yerine 2.71828 f gibi bir **float** sabit değeri kullanın.
