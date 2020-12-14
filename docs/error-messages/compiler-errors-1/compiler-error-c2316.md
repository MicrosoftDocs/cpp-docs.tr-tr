---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2316'
title: Derleyici hatası C2316
ms.date: 07/08/2019
f1_keywords:
- C2316
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
ms.openlocfilehash: 0e2f528b3f13964a971b88fca110980947bd7d11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282217"
---
# <a name="compiler-error-c2316"></a>Derleyici hatası C2316

> '*class_type*': yıkıcı ve/veya kopya Oluşturucu erişilemez olduğundan veya silindiğinden yakalanamıyor

Bir özel durum değere veya başvuruya göre yakalandı, ancak kopya oluşturucuya, atama işlecine veya her ikisine birden erişilemez.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2015 ' deki uygunluk değişiklikleri bu hata, öğesinden türetilmiş MFC özel durumlarının hatalı catch ifadelerine uygulanabilir `CException` . `CException`Devralınmış bir özel kopya oluşturucusuna sahip olduğundan, sınıf ve türetmeleri kopyalanabilir değildir ve değer tarafından yakalanamazlar, bu da değere göre yakalanamazlar. Daha önce çalışma zamanında yakalanamayan özel durumlara bir değere göre MFC özel durumlarını yakalanan catch deyimleri. Artık derleyici bu durumu doğru şekilde tanımlar ve hata C2316 raporlar. Bu sorunu onarmak için, kendi özel durum işleyicilerinizi yazmak yerine MFC TRY/CATCH makrolarını kullanmanızı öneririz. Kodunuz için uygun değilse, bunun yerine MFC özel durumlarını başvuruya göre yakalayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2316 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&) {}
};

void f(const B&)
{
}

int main()
{
    try
    {
        B aB;
        f(aB);
    }
    catch (B b)    // C2316
    {
        printf_s("Caught an exception!\n");
    }
}
```
