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
ms.openlocfilehash: 895db6535299a077bc32b6485a360ae450e6c87e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2316"></a>Derleyici Hatası C2316

> '*özel durum*': yıkıcı ve/veya kopya Oluşturucu erişilemeyen gibi yakalanan olamaz  
  
Değere veya başvuruya göre bir özel durum yakalandı ancak kopya oluşturucu ve/veya atama işleci erişilemez.  
  
Bu kod, Visual Studio 2003 önce Visual C++ sürümü tarafından kabul edildi ancak şimdi hata verir.  
  
Uygunluk Visual Studio 2015 değişikliklerinin hatalı catch deyimleri türetilmiş MFC özel durumların uygulama bu hatayı `CException`. Çünkü `CException` sınıfı bir devralınan özel kopya Oluşturucu sahiptir ve türevleri copyable olmayan ve bunlar olamaz yakalanan değerle anlamına da gelir değere göre geçirilemez. Daha önce çalışma zamanında Yakalanmayan Özel durumlara neden değeriyle MFC özel durum yakalandı deyimleri catch ancak şimdi derleyici doğru şekilde bu durum ve raporlar hata C2316 tanımlar. Bu sorunu gidermek için kendi özel durum işleyicileri yazma, ancak bu kodunuz için uygun değilse, MFC özel durumları başvuruya göre bunun yerine catch yerine MFC TRY/CATCH makroları kullanmanızı öneririz.   
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2316 oluşturur:  
  
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