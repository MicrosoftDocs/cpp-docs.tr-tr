---
title: Yapılandırılmış özel durum işleme (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5b6aafa91ecfde27cc38cccc52f36af43ad21ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="structured-exception-handling-cc"></a>Yapılandırılmış Özel Durum İşleme (C/C++)
Yapılandırılmış özel durum işleme (SEH) Windows ve Visual C++ desteklemesine rağmen çünkü daha taşınabilir ve esnek kodu sağlar ISO standart C++ özel durum işleme kullanmanızı öneririz. Bununla birlikte, var olan kodda ya da programlar belirli türleri için hala SEH kullanmanız gerekebilir.  
  
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
  
## <a name="grammar"></a>Dilbilgisi  
 *try dışında deyimi* :  
  
 `__try` *Bileşik deyim*  
  
 `__except` ( `expression` ) *bileşik deyim*  
  
## <a name="remarks"></a>Açıklamalar  
 SEH ile yürütme beklenmedik bir şekilde kesilip kesilmediğini bellek blokları ve dosyalar gibi kaynakları doğru olduğundan emin olun. Belirli sorunları da işleyebilir — Örneğin, yetersiz bellek — bağlı olmayan kısa yapılandırılmış kodu kullanarak `goto` deyimleri veya karmaşık dönüş kodları test etme.  
  
 Try-except ve try-finally deyimleri bu makalede başvurulan Microsoft C dil uzantıları. Bunlar, bir program yürütme aksi sonlandırmak olayları sonra denetimini uygulamaları etkinleştirerek SEH destekler. C++ kaynak dosyalarını içeren SEH çalışmasına rağmen C++ için özel olarak tasarlanmıştır. Kullanarak derleme C++ programı SEH kullanıyorsanız [/EH](../build/reference/eh-exception-handling-model.md) seçeneği — belirli değiştiricileri birlikte — yerel nesneleri için Yıkıcılar çağrılır, ancak başka bir yürütme davranışı beklediğiniz olmayabilir. (Bir çizim için bu makalenin sonraki bölümlerinde örneğe bakın.) Çoğu durumda, SEH yerine, ISO-standart kullanmanızı öneririz [C++ özel durum işleme](../cpp/try-throw-and-catch-statements-cpp.md), Visual C++ de desteklediği. C++ özel durum işleme kullanarak kodunuzu daha taşınabilir olan ve herhangi bir tür özel durumlar işleyebilir emin olabilirsiniz.  
  
 SEH kullanan C modülleri varsa, bunları bu kullanım C++ özel durum işleme C++ modüllerle karıştırabilirsiniz. Bilgi için bkz: [özel durum işleme farkları](../cpp/exception-handling-differences.md).  
  
 SEH için iki mekanizma vardır:  
  
-   [Özel durum işleyicileri](../cpp/writing-an-exception-handler.md), hangi yanıt vermesi veya özel durum yok sayın.  
  
-   [Sonlandırma işleyicileri](../cpp/writing-a-termination-handler.md), bir özel durum sonlandırma kodu bloğunda neden olduğunda denir.  
  
 Bu iki tür işleyicileri farklıdır, ancak "yığını geriye doğru izleme olarak." bilinen bir işlemle yakından ilgili Özel durum oluştuğunda Windows için şu anda etkin olan en son yüklenen bir özel durum işleyicisi arar. İşleyici işlemlerden birini yapabilirsiniz:  
  
-   Özel durum tanımak ve diğer işleyicilerin denetim geçirmek başarısız.  
  
-   Özel durum algılar ancak onu yok sayın.  
  
-   Özel durum tanıyabilir ve bunu işler.  
  
 Özel durum tanıdığı özel durum işleyicisi özel durum oluştuğunda çalışmakta işlevinde olmayabilir. Bazı durumlarda, bir işlevdeki yığında çok daha yüksek olabilir. Şu anda çalışan işlevi ve diğer işlevleri yığın çerçevesinde sonlandırılır. Bu işlem sırasında yığın "unwound;" başka bir deyişle, yerel değişkenleri sonlandırılan işlevleri — edilmedikleri sürece `static`— yığından temizlenir.  
  
 Yığın unwinds gibi işletim sistemi için her işlevi yazdıktan herhangi sonlandırma işleyicileri çağırır. Sonlandırma işleyicisi kullanarak, aksi takdirde nedeniyle anormal bir sonlandırma açık kalır kaynakları temizleyebilirsiniz. Önemli bir bölümü girdiyseniz sonlandırma işleyicisi çıkabilirsiniz. Program kapatmak için olacaksa, kapatma ve geçici dosyaları kaldırma gibi diğer temizlik görevleri gerçekleştirebilir.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)  
  
-   [Sonlandırma İşleyicisi Yazma](../cpp/writing-a-termination-handler.md)  
  
-   [Yapılandırılmış Özel Durum İşlemeyi C++ ile Kullanma](../cpp/using-structured-exception-handling-with-cpp.md)  
  
## <a name="example"></a>Örnek  
 Bir C++ programı SEH kullanıyorsanız ve kullanarak derleme yerel nesneler olarak adlandırılır için Yıkıcılar daha önce belirtildiği gibi **/EH** belirli değiştiricileri seçeneğiyle — Örneğin, **/EHsc** ve **/EHa**. Ancak, yürütme sırasında davranışı C++ özel durumlarını da kullanıyorsanız, beklediğiniz olmayabilir. Aşağıdaki örnek, bu davranış farklılıkları gösterir.  
  
```cpp  
#include <stdio.h>  
#include <Windows.h>  
#include <exception>  
  
class TestClass  
{  
public:  
    ~TestClass()  
    {  
        printf("Destroying TestClass!\r\n");  
    }  
};  
  
__declspec(noinline) void TestCPPEX()  
{  
#ifdef CPPEX  
    printf("Throwing C++ exception\r\n");  
    throw std::exception("");  
#else  
    printf("Triggering SEH exception\r\n");  
    volatile int *pInt = 0x00000000;  
    *pInt = 20;  
#endif  
}  
  
__declspec(noinline) void TestExceptions()  
{  
    TestClass d;  
    TestCPPEX();  
}  
  
int main()  
{  
    __try  
    {  
        TestExceptions();  
    }  
    __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf("Executing SEH __except block\r\n");  
    }  
  
    return 0;  
}  
  
```  
  
 Kullanırsanız **/EHsc** Bu kod, ancak yerel test denetimi derlemek için `CPPEX` olan tanımlanmamışsa, yoktur hiçbir yürütülmesi `TestClass` yıkıcı ve çıktı görünümler gibi bu:  
  
```Output  
Triggering SEH exception  
Executing SEH __except block  
```  
  
 Kullanırsanız **/EHsc** Kodu derlemek için ve `CPPEX` kullanılarak tanımlanmış `/DCPPEX` (C++ özel durum böylece), `TestClass` yıkıcı yürütür ve çıktı şuna benzer:  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 Kullanırsanız **/EHa** Kodu derlemek için `TestClass` yıkıcı yürütür olup kullanarak özel durum oluştu bağımsız olarak `std::throw` veya özel durum tetiklemek için SEH kullanarak (`CPPEX` veya tanımlanmış). Çıktı şu şekildedir:  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 Daha fazla bilgi için bkz: [/EH (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md).  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme](../cpp/exception-handling-in-visual-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [\<Özel Durum >](../standard-library/exception.md)   
 [Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Yapılandırılmış özel durum işleme (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)