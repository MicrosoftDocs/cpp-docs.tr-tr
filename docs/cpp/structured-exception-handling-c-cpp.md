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
ms.openlocfilehash: 942a7e48e4315454476bfe93c68169f461b006b2
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245125"
---
# <a name="structured-exception-handling-cc"></a>Yapılandırılmış Özel Durum İşleme (C/C++)

Yapılandırılmış özel durum işleme (SEH), donanım hataları gibi belirli olağanüstü kod durumlarını işlemek için bir Microsoft uzantısıdır. Windows ve Microsoft C++ , SEH 'yi desteklese de, kodunuzu daha taşınabilir ve esnek C++ hale getiren ISO standardı özel durum işlemeyi kullanmanızı öneririz. Bununla birlikte, mevcut kodu korumak veya belirli türde programlar için yine de SEH kullanmanız gerekebilir.

**Microsoft 'a özgü:**

## <a name="grammar"></a>Dilbilgisi

*try-except-deyimleri* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *bileşik deyim* **__except** **(** *ifade* **)** *bileşik-deyim*

*try-finally-deyimin* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *bileşik ifade* **__finally** *bileşik-ekstresi*

## <a name="remarks"></a>Açıklamalar

SEH ile, yürütme beklenmedik şekilde sonlandırılırsa bellek blokları ve dosyalar gibi kaynakların doğru şekilde serbest bırakıldığını sağlayabilirsiniz. Ayrıca, özel sorunları (örneğin, yetersiz bellek), **goto** deyimlerine veya dönüş kodlarının ayrıntılı test edilmesine bağlı olmayan kısa şekilde yapılandırılmış kodu kullanarak da işleyebilirsiniz.

Bu makalede başvurulan try-except ve try-finally deyimleri, C dilinin Microsoft uzantılarıdır. Uygulamalar, daha sonra yürütmeyi sonlandıran olaylardan sonra bir programın denetimini ele geçirmesine olanak tanıyarak SEH 'yi destekler. SEH C++ kaynak dosyalarla çalışabilse de, için C++özel olarak tasarlanmamıştır. [/EHa veya/EHsc](../build/reference/eh-exception-handling-model.md) seçeneğini C++ kullanarak DERLEYEBILECEĞINIZ bir programda SEH kullanırsanız, yerel nesneler için Yıkıcılar çağrılır, ancak diğer yürütme davranışı beklediğiniz gibi olmayabilir. Bir çizim için bu makalenin ilerleyen kısımlarındaki örneğe bakın. Birçok durumda, SEH yerine Microsoft C++ derleyicisinin de desteklediği ISO standardı [ C++ özel durum işlemeyi](../cpp/try-throw-and-catch-statements-cpp.md)kullanmanızı öneririz. Özel durum C++ işlemeyi kullanarak, kodunuzun daha taşınabilir olmasını sağlayabilir ve herhangi bir türdeki özel durumları işleyebilirsiniz.

SEH kullanan C kodunuz varsa, özel durum işleme kullanan C++ C++ kodla onu karıştırabilirsiniz. Bilgi için bkz. [içinde C++yapılandırılmış özel durumları işleme ](../cpp/exception-handling-differences.md).

İki SEH mekanizması vardır:

- Özel durum [işleyicileri](../cpp/writing-an-exception-handler.md)veya **__except** blokları, özel durum yanıt verebilir veya kapatabilir.

- [Sonlandırma işleyicileri](../cpp/writing-a-termination-handler.md)veya her zaman çağrılan **__finally** blokları, bir özel durumun sonlandırmasına neden olup olmadığı.

Bu iki tür işleyici farklıdır, ancak "yığını geri sarma" olarak bilinen bir işlemle yakından ilgilidir. Yapılandırılmış bir özel durum oluştuğunda Windows, şu anda etkin olan en son yüklenen özel durum işleyicisini arar. İşleyici üç işlemlerden birini gerçekleştirebilir:

- Özel durum tanınamadı ve denetim diğer işleyicilere geçirilemez.

- Özel durumu tanıyor, ancak bunu yoksayın.

- Özel durumu tanıyor ve işleyin.

Özel durumu tanıyan özel durum işleyicisi, özel durum oluştuğunda çalışmakta olan işlevde bulunmayabilir. Bazı durumlarda, yığın üzerinde çok daha yüksek bir işlevde olabilir. Şu anda çalışan işlev ve yığın çerçevesindeki diğer tüm işlevler sonlandırılır. Bu işlem sırasında, yığın "unwound;", diğer bir deyişle, sonlandırılmış işlevlerin yerel statik olmayan değişkenleri yığından temizlenir.

Yığın olmadığından, işletim sistemi her bir işlev için yazdığınız sonlandırma işleyicilerini çağırır. Sonlandırma işleyicisi kullanarak, olağan dışı bir sonlandırma nedeniyle başka türlü açık kalabilecek kaynakları temizleyebilirsiniz. Kritik bir bölüm girdiyseniz, sonlandırma işleyicisinde bu işlemden çıkabilirsiniz. Program kapatılırsa, geçici dosyaları kapatma ve kaldırma gibi başka bir temizlik görevi gerçekleştirebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)

- [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)

- [C++ dilinde yapılandırılmış özel durumları işleme](../cpp/exception-handling-differences.md)

## <a name="example"></a>Örnek

Daha önce belirtildiği gibi, bir C++ programda SEH kullanırsanız ve **/EHa** veya **/EHsc** seçeneğini kullanarak derlerseniz yerel nesneler için Yıkıcılar çağrılır. Ancak, özel durumlar da kullanıyorsanız C++ , yürütme sırasındaki davranış beklediğiniz gibi olmayabilir. Bu örnek, bu davranış farklarını gösterir.

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

Bu kodu derlemek için **/EHsc** kullanırsanız, ancak `CPPEX` yerel test denetimi makrosu tanımsızdır, `TestClass` yok edicinin yürütülmesi olmaz ve çıkış şöyle görünür:

```Output
Triggering SEH exception
Executing SEH __except block
```

Kodu derlemek için **/EHsc** kullanırsanız ve `CPPEX` `/DCPPEX` kullanılarak tanımlıysa (bir C++ özel durum oluşturulur), `TestClass` yıkıcısı yürütülür ve çıktı şöyle görünür:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

Kodu derlemek için **/EHa** kullanırsanız `TestClass` yıkıcısı, özel durumun `std::throw` kullanılarak mı yoksa özel durum TETIKLENMESI için seh kullanılarak mı yoksa, tanımlı `CPPEX` olup olmadığı, yani tanımlanmış olup olmamasına bakılmaksızın yürütülür. Çıktı şöyle görünür:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

Daha fazla bilgi için bkz. [/Eh (özel durum Işleme modeli)](../build/reference/eh-exception-handling-model.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[\<özel durum >](../standard-library/exception.md)<br/>
[Hatalar ve özel durum Işleme](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Yapılandırılmış özel durum Işleme (Windows)](/windows/win32/debug/structured-exception-handling)
