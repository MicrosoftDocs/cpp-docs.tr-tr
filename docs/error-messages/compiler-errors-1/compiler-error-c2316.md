---
title: Derleyici Hatası C2316 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2316
dev_langs:
- C++
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2868d3a81fcbc94d8b20adcdc775363eb0a8eaeb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033023"
---
# <a name="compiler-error-c2316"></a>Derleyici Hatası C2316

> '*özel durum*': yok edici ve/veya kopya oluşturucusuna erişilemez olarak yakalanamıyor

Değere veya başvuruya göre bir özel durum yakalandı ancak kopya oluşturucu ve/veya atama işleci erişilemez.

Bu kod, Visual Studio 2003 önce Visual C++ sürümü tarafından kabul edildi, ancak şimdi bir hata verir.

Visual Studio 2015'te uyumluluk değişiklikleri yapılan bu hata, hatalı catch deyimleri türetilmiş MFC özel durumları uygulamak `CException`. Çünkü `CException` bir devralınan özel kopya Oluşturucu, sınıfın var ve CIM'in kopyalanamaz ve bunlar kullanılamaz yakalandı değere göre anlamına da gelir değer geçirilemez. Catch MFC özel durumları, daha önce Yakalanmayan Özel durumların zamanında götüren değere göre yakalanan deyimleri, ancak artık derleyici doğru şekilde bu durum ve raporlar hatası C2316 tanımlar. Bu sorunu gidermek için kendi özel durum işleyicileri yazmaktadır, ancak bu, kodunuz için uygun değilse, MFC özel durumları başvuruya göre bunun yerine catch yerine MFC TRY/CATCH makroları kullanmanızı öneririz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2316 oluşturur:

```
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

extern "C" int printf_s(const char*, ...);

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&)
    {
    }
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
    catch (B b) {   // C2316
        printf_s("Caught an exception!\n");
    }
}
```