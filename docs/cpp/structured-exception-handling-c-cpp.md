---
title: Yapılandırılmış Özel Durum İşleme (C/C++)
ms.date: 08/14/2018
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
ms.openlocfilehash: b77a218340399578e3c9428100476787e2e60b25
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534569"
---
# <a name="structured-exception-handling-cc"></a>Yapılandırılmış Özel Durum İşleme (C/C++)

Yapılandırılmış özel durum işleme (SEH) C donanım hataları gibi bazı olağanüstü durum kodunu durumlarda düzgün bir şekilde işlemek için bir Microsoft uzantısıdır. Windows ve Visual C++ SEH uygulamasını desteklese de, olduğundan, kodunuzun daha taşınabilir ve esnek yapan ISO standardı C++ özel durum işleme kullanmanızı öneririz. Bununla birlikte, mevcut kodu sağlamak ya da belirli program türleri için yine de SEH kullanmanız gerekebilir.

**Microsoft'a özgü:**

## <a name="grammar"></a>Dilbilgisi

*try haricinde deyimi* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try** *compound-statement* **__except** **(** *ifade* **)** *bileşik deyim*

*try-finally deyimi* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try** *compound-statement* **__finally** *bileşik deyim*

## <a name="remarks"></a>Açıklamalar

SEH ile yürütme beklenmedik şekilde sonlandırılırsa bellek blokları ve dosyaları gibi kaynakları doğru şekilde serbest bırakıldığından emin olabilirsiniz. Belirli sorunları da işleyebilirsiniz — Örneğin, yetersiz bellek — üzerinde kullanmayan kısa yapılandırılmış kodu kullanarak **goto** deyimleri ya da dönüş kodlarını ayrıntılı test etme.

Try-except ve try-finally deyimleri başvurulan bu makalede Microsoft C diline yönelik uzantılarıdır. Bunlar, aksi takdirde yürütme sonlanırdı olayları sonra bir program denetlemek amacıyla uygulamaları etkinleştirerek SEH destekler. SEH ile C++ kaynak dosyaları çalışır, ancak C++ için özel olarak tasarlanmıştır. Bir C++ programında kullanarak derleme SEH kullanıyorsanız [/eha veya/ehsc](../build/reference/eh-exception-handling-model.md) seçeneğini yok ediciler yerel nesneleri çağrılır ancak başka bir yürütme davranışı beklediğiniz olmayabilir. Çizim için bu makalenin ilerleyen kısımlarındaki örneğe bakın. Çoğu durumda, SEH yerine, ISO standardı kullanmanızı öneririz [C++ özel durum işleme](../cpp/try-throw-and-catch-statements-cpp.md), Visual C++ da destekler. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan ve her türden özel durumları işleyebilir emin olabilirsiniz.

SEH kullanan C kodu varsa, C++ özel durum işleme kullanan C++ kodu ile karıştırabilirsiniz. Bilgi için [yapılandırılmış özel durumları C++'ta işlemek](../cpp/exception-handling-differences.md).

SEH için iki mekanizma vardır:

- [Özel durum işleyicileri](../cpp/writing-an-exception-handler.md), veya **__except** yanıt veya özel durum Kapat bloklar.

- [Sonlandırma işleyicileri](../cpp/writing-a-termination-handler.md), veya **__finally** veya bir özel durum sonlandırma neden olmadığını çağrılan her zaman, blok.

Bu işleyiciler iki tür farklıdır, ancak "yığın geriye doğru izleme olarak." bilinen bir işlemle yakından ilgili Yapılandırılmış bir özel durum oluştuğunda Windows için o anda etkin olan en son yüklenen bir özel durum işleyicisi arar. İşleyici işlemlerden birini yapabilirsiniz:

- Özel durum tanımak ve denetim diğer işleyicilerine geçirmek başarısız.

- Özel durum tanımak ancak reddedebilir.

- Özel durum tanıması ve işlemesi.

Özel durum tanıdığı bir özel durum işleyicisi özel durum oluştuğunda çalıştıran işlevinde olmayabilir. Bazı durumlarda, yığın üzerinde çok daha yüksek bir işlevi olabilir. Şu anda çalışan işlevi ve diğer işlevleri yığın çerçevesinde sonlandırılır. Bu işlem sırasında yığın "Çözülmüş"; diğer bir deyişle, sonlandırılmış işlevlerin yerel statik olmayan değişkenleri yığından temizlenir.

Yığın geriye doğru izler gibi işletim sistemi her işlev için yazdığınız tüm sonlandırma işleyicilerini çağırır. Sonlandırma işleyicisi'ni kullanarak, aksi takdirde, olağan dışı bir sonlandırma nedeniyle açık kalır kaynakları temizleyebilirsiniz. Kritik bir bölüm girdiyseniz, sonlandırma işleyicisinde çıkabilirsiniz. Programı kapatmak için olacaksa, kapatma ve geçici dosyaları kaldırma gibi diğer temizlik görevlerini gerçekleştirebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)

- [Sonlandırma İşleyicisi Yazma](../cpp/writing-a-termination-handler.md)

- [C++ dilinde yapılandırılmış özel durumları işleme](../cpp/exception-handling-differences.md)

## <a name="example"></a>Örnek

C++ programında SEH kullanın ve kullanarak derleme yerel nesneleri olarak adlandırılan için Yıkıcılar daha önce belirtildiği gibi **/eha** veya **/ehsc** seçeneği. Ancak, yürütme sırasında davranışı C++ özel durumlarını da kullanıyorsanız, beklediğiniz olmayabilir. Bu örnek, bu davranış farklılıkları gösterir.

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

Kullanırsanız **/ehsc** , ancak yerel test denetim makrosu bu kodu derlemek için `CPPEX` olan tanımlanmamışsa, hiçbir yürütülmesini yoktur `TestClass` yok edicisini ve çıktı görünür şöyle:

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

Kullanırsanız **/eha** Kodu derlemek için `TestClass` yok Edicisi yürütür olup kullanarak özel durum oluştu bakılmaksızın `std::throw` veya SEH özel durumu, diğer bir deyişle, tetiklemek için kullanarak olmadığını `CPPEX` tanımlanan veya değil. Çıktı şuna benzer:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

Daha fazla bilgi için [/EH (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[\<Özel Durum >](../standard-library/exception.md)<br/>
[Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Yapılandırılmış özel durum işleme (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)
