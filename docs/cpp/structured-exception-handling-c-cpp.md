---
title: Yapılandırılmış Özel Durum İşleme (C/C++)
description: Microsoft C/C++ ' da yapılandırılmış özel durum işlemeye genel bakış.
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
ms.openlocfilehash: 142e89bc82adbe7938e8825029908e814df6055c
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898631"
---
# <a name="structured-exception-handling-cc"></a>Yapılandırılmış Özel Durum İşleme (C/C++)

Yapılandırılmış özel durum işleme (SEH), donanım hataları gibi belirli olağanüstü kod durumlarını işlemek için bir Microsoft uzantısıdır. Windows ve Microsoft C++, SEH 'yi desteklese de, ISO standardı C++ özel durum işleme kullanmanızı öneririz. Kodunuzu daha taşınabilir ve esnek hale getirir. Ancak, mevcut kodu korumak veya belirli türde programlar için yine de SEH kullanmanız gerekebilir.

**Microsoft 'a özgü:**

## <a name="grammar"></a>Dilbilgisi

> *`try-except-statement`* :<br/>
> &emsp;**`__try`** *`compound-statement`* **`__except`** **`(`** *`expression`* **`)`** *`compound-statement`*
>
> *`try-finally-statement`* :<br/>
> &emsp;**`__try`** *`compound-statement`* **`__finally`** *`compound-statement`*

## <a name="remarks"></a>Açıklamalar

SEH ile, yürütme beklenmedik şekilde sonlandırılırsa bellek blokları ve dosyalar gibi kaynakların doğru şekilde serbest bırakılacağını sağlayabilirsiniz. Ayrıca, belirli sorunları (örneğin, yetersiz bellek), **`goto`** deyimlere veya dönüş kodlarının ayrıntılı test edilmesine bağlı olmayan kısa şekilde yapılandırılmış kodu kullanarak da işleyebilirsiniz.

`try-except` `try-finally` Bu makalede başvurulan ve deyimleri, C dilinin Microsoft uzantılarıdır. Uygulamalar, daha sonra yürütmeyi sonlandıran olaylardan sonra bir programın denetimini ele geçirmesine olanak tanıyarak SEH 'yi destekler. SEH C++ kaynak dosyalarıyla çalışabilse de, C++ için özel olarak tasarlanmamıştır. [ `/EHa` Veya `/EHsc` ](../build/reference/eh-exception-handling-model.md) seçeneğini kullanarak derleyebileceğiniz bir C++ programında SEH kullanırsanız, yerel nesneler için Yıkıcılar çağrılır, ancak diğer yürütme davranışı beklediğiniz gibi olmayabilir. Bir çizim için bu makalenin ilerleyen kısımlarındaki örneğe bakın. Birçok durumda, SEH yerine Microsoft C++ derleyicisinin desteklediği ISO standardı [C++ özel durum işlemeyi](../cpp/try-throw-and-catch-statements-cpp.md)kullanmanızı öneririz. C++ özel durum işlemeyi kullanarak, kodunuzun daha taşınabilir olmasını sağlayabilir ve herhangi bir türdeki özel durumları işleyebilirsiniz.

SEH kullanan C kodunuz varsa, bunu C++ özel durum işleme kullanan C++ kodu ile karıştırabilirsiniz. Bilgi için bkz. [C++ ' da yapılandırılmış özel durumları işleme](../cpp/exception-handling-differences.md).

İki SEH mekanizması vardır:

- Özel durum [işleyicileri](../cpp/writing-an-exception-handler.md)veya **`__except`** blokları, özel durum yanıt verebilir veya kapatabilir.

- [Sonlandırma işleyicileri](../cpp/writing-a-termination-handler.md)veya **`__finally`** her zaman çağrılan bloklar, bir özel durumun sonlandırmasına neden olup olmadığı.

Bu iki tür işleyici farklıdır, ancak *yığını geri sarma*olarak bilinen bir işlemle yakından ilgilidir. Yapılandırılmış bir özel durum oluştuğunda Windows, şu anda etkin olan en son yüklenen özel durum işleyicisini arar. İşleyici üç işlemlerden birini gerçekleştirebilir:

- Özel durum tanınamadı ve denetim diğer işleyicilere geçirilemez.

- Özel durumu tanıyor, ancak bunu yoksayın.

- Özel durumu tanıyor ve işleyin.

Özel durumu tanıyan özel durum işleyicisi, özel durum oluştuğunda çalışmakta olan işlevde bulunmayabilir. Yığın üzerinde çok daha yüksek bir işlev içinde olabilir. Şu anda çalışan işlev ve yığın çerçevesindeki diğer tüm işlevler sonlandırılır. Bu işlem sırasında yığın *bozuk olur.* Diğer bir deyişle, sonlandırılmış işlevlerin yerel statik olmayan değişkenleri yığından temizlenir.

Yığın olmadığından, işletim sistemi her bir işlev için yazdığınız sonlandırma işleyicilerini çağırır. Sonlandırma işleyicisi kullanarak, olağan dışı bir sonlandırma nedeniyle başka türlü açık kalacak kaynakları temizleyecekti. Kritik bir bölüm girdiyseniz, sonlandırma işleyicisinde bu işlemden çıkabilirsiniz. Program kapatıldığında, geçici dosyaları kapatma ve kaldırma gibi başka bir temizlik görevi gerçekleştirebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Özel Durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)

- [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)

- [C++ dilinde yapılandırılmış özel durumları işleme](../cpp/exception-handling-differences.md)

## <a name="example"></a>Örnek

Daha önce belirtildiği gibi, bir C++ programında SEH kullanırsanız ve veya seçeneğini kullanarak derlerseniz, yerel nesneler için Yıkıcılar çağrılır **`/EHa`** **`/EHsc`** . Ancak, aynı zamanda C++ özel durumları kullanıyorsanız, yürütme sırasındaki davranış beklenmeyebilir. Bu örnek, bu davranış farklarını gösterir.

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

**`/EHsc`** Bu kodu derlemek için kullanırsanız, ancak yerel test denetimi makrosu `CPPEX` tanımsızdır, `TestClass` yok edicisi çalıştırılmaz. Çıktı şuna benzer:

```Output
Triggering SEH exception
Executing SEH __except block
```

**`/EHsc`** Kodu derlemek için kullanırsanız ve `CPPEX` kullanılarak tanımlanmışsa `/DCPPEX` (bir C++ özel durumu oluştuğunda), `TestClass` yıkıcı çalışır ve çıktı şöyle görünür:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

**`/EHa`** Kodu derlemek için kullanırsanız, yıkıcı özel durumun `TestClass` kullanılarak `std::throw` veya özel durumun TETIKLENMESI için seh kullanılarak oluşturulup oluşturulmayacağını yürütür. Diğer bir deyişle, `CPPEX` tanımlı olup olmadığı. Çıktı şuna benzer:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

Daha fazla bilgi için bkz. [ `/EH` (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum işleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[`<exception>`](../standard-library/exception.md)<br/>
[Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Yapılandırılmış özel durum Işleme (Windows)](/windows/win32/debug/structured-exception-handling)
