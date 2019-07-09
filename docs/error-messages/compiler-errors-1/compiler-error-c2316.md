---
title: Derleyici Hatası C2316
ms.date: 07/08/2019
f1_keywords:
- C2316
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
ms.openlocfilehash: 5a3d9052775a5e1cbedfd58ccaaf0ff039a8475d
ms.sourcegitcommit: 07b34ca1c1fecced9fadc95de15dc5fee4f31e5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67693438"
---
# <a name="compiler-error-c2316"></a>Derleyici Hatası C2316

> '*class_type*': yok edici ve/veya kopya oluşturucusu, erişilemez veya silinmiş olarak yakalanamıyor

Değer veya başvuru, ancak atama işleci, kopya Oluşturucu tarafından bir özel durum yakalandı veya her ikisi de erişilemez.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2015'te uyumluluk değişiklikleri yapılan bu hata, hatalı catch deyimleri türetilmiş MFC özel durumları uygulamak `CException`. Çünkü `CException` bir devralınan özel kopya Oluşturucu, sınıfın var ve CIM'in kopyalanabilir değildir ve bunlar kullanılamaz yakalandı değere göre anlamına da gelir değer geçirilemez. MFC özel durumları, daha önce Yakalanmayan Özel durumların zamanında götüren değere göre yakalanan deyimleri yakalayın. Artık derleyici doğru şekilde bu durum tanımlar ve hatası C2316 bildiriyor. Bu sorunu gidermek için MFC TRY/CATCH makroları kullanmak yerine, kendi özel durum işleyicisi yazma öneririz. Bu, kodunuz için uygun değilse, MFC özel durumları yerine başvuruya göre yakalayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2316 oluşturur ve bunu düzeltmek için bir yol gösterir:

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
