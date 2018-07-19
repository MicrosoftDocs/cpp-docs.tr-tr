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
ms.openlocfilehash: 64ff69a4ab75189dd069e774eb05266e6140ff77
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940501"
---
# <a name="structured-exception-handling-cc"></a>Yapılandırılmış Özel Durum İşleme (C/C++)
Yapılandırılmış özel durum işleme (SEH), Windows ve Visual C++ desteklese de, kod daha taşınabilir ve esnek yapan ISO standardı C++ özel durum işleme kullanmanızı öneririz. Bununla birlikte, varolan kodda ya da belirli program türleri için yine de SEH kullanmanız gerekebilir.  
  
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
  
## <a name="grammar"></a>Dilbilgisi  
 *try haricinde deyimi* :  
  
 `__try` *Bileşik deyim*  
  
 `__except` ( `expression` ) *compound-statement*  
  
## <a name="remarks"></a>Açıklamalar  
 SEH ile yürütme beklenmedik şekilde sonlandırılırsa, bellek bloklarını ve dosyaları gibi kaynakların doğru olduğundan emin olabilirsiniz. Belirli sorunları da işleyebilirsiniz — Örneğin, yetersiz bellek — üzerinde kullanmayan kısa yapılandırılmış kodu kullanarak **goto** deyimleri ya da dönüş kodlarını ayrıntılı test etme.  
  
 Try-except ve try-finally deyimleri başvurulan bu makalede Microsoft C diline yönelik uzantılarıdır. Bunlar, aksi takdirde yürütme sonlanırdı olayları sonra bir program denetlemek amacıyla uygulamaları etkinleştirerek SEH destekler. SEH ile C++ kaynak dosyaları çalışır, ancak C++ için özel olarak tasarlanmıştır. Bir C++ programında kullanarak derleme SEH kullanıyorsanız [/EH](../build/reference/eh-exception-handling-model.md) seçeneği — belirli değiştiriciler birlikte — yerel nesneleri yok ediciler çağrılır ancak başka bir yürütme davranışı beklediğiniz olmayabilir. (Bir çizim için bu makalenin ilerleyen kısımlarındaki örneğe bakın.) Çoğu durumda, SEH yerine, ISO standardı kullanmanızı öneririz [C++ özel durum işleme](../cpp/try-throw-and-catch-statements-cpp.md), Visual C++ da destekler. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan ve her türden özel durumları işleyebilir emin olabilirsiniz.  
  
 SEH kullanmak C modülleri varsa, bunları bu kullanım C++ özel durum işleme ile C++ modülleri karıştırabilirsiniz. Bilgi için [özel durum işleme farkları](../cpp/exception-handling-differences.md).  
  
 SEH için iki mekanizma vardır:  
  
-   [Özel durum işleyicileri](../cpp/writing-an-exception-handler.md), hangi yanıt veya özel durum yok sayın.  
  
-   [Sonlandırma işleyicileri](../cpp/writing-a-termination-handler.md), bir özel durum, bir kod bloğu içinde sonlandırma neden olduğunda denir.  
  
 Bu işleyiciler iki tür farklıdır, ancak "yığın geriye doğru izleme olarak." bilinen bir işlemle yakından ilgili Bir özel durum oluştuğunda Windows için o anda etkin olan en son yüklenen bir özel durum işleyicisi arar. İşleyici işlemlerden birini yapabilirsiniz:  
  
-   Özel durum tanımak ve denetim diğer işleyicilerine geçirmek başarısız.  
  
-   Özel durum tanımak ancak reddedebilir.  
  
-   Özel durum tanıması ve işlemesi.  
  
 Özel durum tanıdığı bir özel durum işleyicisi özel durum oluştuğunda çalıştıran işlevinde olmayabilir. Bazı durumlarda, yığın üzerinde çok daha yüksek bir işlevi olabilir. Şu anda çalışan işlevi ve diğer işlevleri yığın çerçevesinde sonlandırılır. Bu işlem sırasında yığın "Çözülmüş"; diğer bir deyişle, yerel değişkenleri sonlandırılan işlevlerin — olmadıkları sürece **statik**— yığından temizlenir.  
  
 Yığın geriye doğru izler gibi işletim sistemi her işlev için yazdığınız tüm sonlandırma işleyicilerini çağırır. Sonlandırma işleyicisi'ni kullanarak, aksi takdirde, olağan dışı bir sonlandırma nedeniyle açık kalır kaynakları temizleyebilirsiniz. Kritik bir bölüm girdiyseniz, sonlandırma işleyicisinde çıkabilirsiniz. Programı kapatmak için olacaksa, kapatma ve geçici dosyaları kaldırma gibi diğer temizlik görevlerini gerçekleştirebilirsiniz.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)  
  
-   [Sonlandırma İşleyicisi Yazma](../cpp/writing-a-termination-handler.md)  
  
-   [Yapılandırılmış Özel Durum İşlemeyi C++ ile Kullanma](../cpp/using-structured-exception-handling-with-cpp.md)  
  
## <a name="example"></a>Örnek  
 C++ programında SEH kullanın ve kullanarak derleme yerel nesneleri olarak adlandırılan için Yıkıcılar daha önce belirtildiği gibi **/EH** belirli değiştiriciler seçeneğiyle — Örneğin, **/ehsc** ve   **/eha**. Ancak, yürütme sırasında davranışı C++ özel durumlarını da kullanıyorsanız, beklediğiniz olmayabilir. Aşağıdaki örnek, bu davranış farklılıkları gösterir.  
  
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
  
 Kullanırsanız **/ehsc** , ancak yerel test denetimi bu kodu derlemek için `CPPEX` olan tanımlanmamışsa, hiçbir yürütülmesini yoktur `TestClass` yok edicisini ve çıktı görünür şöyle:  
  
```Output  
Triggering SEH exception  
Executing SEH __except block  
```  
  
 Kullanırsanız **/ehsc** Kodu derlemek için ve `CPPEX` kullanılarak tanımlanmış `/DCPPEX` (C++ özel durum oluşturulmayacak şekilde), `TestClass` yok Edicisi yürütür ve çıktı şuna benzer:  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 Kullanırsanız **/eha** Kodu derlemek için `TestClass` yok Edicisi yürütür olup kullanarak özel durum oluştu bakılmaksızın `std::throw` veya SEH özel durumu tetiklemek için kullanarak (`CPPEX` veya tanımlanan). Çıktı şuna benzer:  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 Daha fazla bilgi için [/EH (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md).  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme](../cpp/exception-handling-in-visual-cpp.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [\<Özel Durum >](../standard-library/exception.md)   
 [Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Yapılandırılmış özel durum işleme (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)