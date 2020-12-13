---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4305'
title: Derleyici Uyarısı (düzey 1) C4305
ms.date: 01/17/2018
f1_keywords:
- C4305
helpviewer_keywords:
- C4305
ms.openlocfilehash: a6cee5be3b5929c0fbf487a8c40d37e269e6a994
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340092"
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

Bu sorunu düzeltmek için doğru türdeki bir değeri kullanarak başlatın veya doğru türe açık bir tür dönüştürme kullanın. Örneğin, bir **`float`** **`double`** **`float`** değişken başlatmak veya bağımsız değişken alan bir oluşturucuya geçirmek için bir yerine 2.71828 f (kayan nokta değişmez değerleri için varsayılan tür) gibi bir değişmez değer kullanın **`float`** .
