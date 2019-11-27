---
title: try-except Deyimi
ms.date: 10/09/2018
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- _except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
ms.openlocfilehash: af378f510f11e1fe7d08619b5f33efe92a13d7be
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245172"
---
# <a name="try-except-statement"></a>try-except Deyimi

**Microsoft 'a özgü**

**Try-except** deyimleri, yapılandırılmış özel durum Işlemeyi destekleyen C ve C++ dillerin Microsoft uzantısıdır.

## <a name="syntax"></a>Sözdizimi

> **\_\_dene**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;//korunan kod<br/>
> }<br/>
> **\_\_except** ( *ifade* )<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;//özel durum işleyici kodu<br/>
> }

## <a name="remarks"></a>Açıklamalar

**Try-except** deyimleri, bir Microsoft uzantısı olan C ve C++ dillerin, normalde programın yürütülmesini sonlandıran olaylar gerçekleştiğinde denetim kazanmasını sağlar. Bu tür olaylara *özel durumlar*denir ve özel durumlarla ilgilenen mekanizmaya *yapılandırılmış özel durum işleme* (SEH) denir.

İlgili bilgiler için, [try-finally ifadesine](../cpp/try-finally-statement.md)bakın.

Özel durumlar, donanım tabanlı veya yazılım tabanlı olabilir. Uygulamalar donanım veya yazılım özel durumlarından tamamen kurtarılamadığında bile, yapılandırılmış özel durum işleme hata bilgilerinin görüntülenmesini ve sorunun tanılanmasına yardımcı olmak için uygulamanın iç durumunun yakalanmasını sağlar. Bu, özellikle kolayca yeniden oluşturulamayan aralıklı sorunlar için yararlıdır.

> [!NOTE]
> Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. Programlar C++ için, C++ özel durum işleme mekanizmasını ([try, catch ve throw](../cpp/try-throw-and-catch-statements-cpp.md) deyimlerini) kullanmanız önerilir.

**__Try** yan tümcesinden sonraki bileşik ifade gövde veya korumalı bölümdür. **__Except** yan tümcesinden sonraki bileşik ifade, özel durum işleyicisidir. İşleyici, korunan bölümün gövdesi yürütülürken bir özel durum oluşturulursa yapılacak işlemleri belirtir. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Korunan bölümün yürütülmesi sırasında hiçbir özel durum oluşursa, yürütme **__except** yan tümcesinden sonra deyimden devam eder.

1. Korunan bölümün yürütülmesi sırasında veya korunan bölüm çağrılarında herhangi bir yordam için bir özel durum oluşursa, **__except** *ifadesi* ( *filtre* ifadesi olarak adlandırılır) değerlendirilir ve değer özel durumun nasıl işlendiğini belirler. Üç olası değer vardır:

   - EXCEPTION_CONTINUE_EXECUTION (-1) özel durumu kapatıldı. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.

   - EXCEPTION_CONTINUE_SEARCH (0) özel durumu tanınmıyor. İlk olarak **try-except** deyimlerini içeren işleyiciler için bir işleyici için yığın aramaya devam edin, ardından bir sonraki en yüksek önceliğe sahip işleyiciler için.

   - EXCEPTION_EXECUTE_HANDLER (1) özel durumu tanınıyor. **__Except** bileşik bildirisini yürüterek denetimi özel durum işleyicisine aktarın, sonra **__except** bloğundan sonra yürütmeye devam edin.

**__Except** Ifadesi bir C ifadesi olarak değerlendirildiğinden, tek bir değer, koşullu ifade işleci veya virgül işleci ile sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.

Her uygulamanın kendi özel durum işleyicisi olabilir.

**__Try** ifadeye geçmek geçersizdir, ancak bunlardan birine geçmek için geçerli değildir. Bir işlem bir **try-except** ifadesinin ortasında sonlandırılırsa, özel durum işleyicisi çağrılmaz.

Önceki sürümlerle uyumluluk için **_try**, **_except**ve **_leave** **__try**, **__except**ve **__Leave** Için eş anlamlılardır. [/za \(dil uzantılarını devre dışı bırakma](../build/reference/za-ze-disable-language-extensions.md)

### <a name="the-__leave-keyword"></a>__leave Anahtar Sözcüğü

**__Leave** anahtar sözcüğü yalnızca **try-except** ifadesinin korunan bölümünde geçerlidir ve etkisi, korunan bölümün sonuna atlanmak olur. Yürütme, özel durum işleyicisinden sonra ilk deyimde devam eder.

Bir **goto** deyim ayrıca korunan bölümden de çıkabilir ve yığın geri sarma gerçekleşmediğinden bir **try-finally** ifadesinde olduğu gibi performansı düşürür. Ancak, korunan bölüm büyük veya karmaşık olduğunda bir programlama hatası yapma olasılığınız daha az olduğundan, **goto** ifadesinin yerine **__leave** anahtar sözcüğünü kullanmanızı öneririz.

### <a name="structured-exception-handling-intrinsic-functions"></a>Yapılandırılmış Özel Durum İşleme İç İşlevleri

Yapılandırılmış özel durum işleme, **try-except** ifadesiyle kullanılabilecek iki iç işlev sağlar: `GetExceptionCode` ve `GetExceptionInformation`.

`GetExceptionCode` özel durumun kodunu (32 bitlik bir tamsayı) döndürür.

İç işlev `GetExceptionInformation` özel durum hakkında ek bilgi içeren bir yapıya bir işaretçi döndürür. Bu işaretçiyle, donanım özel durumu sırasında var olan makine durumuna erişebilirsiniz. Yapı aşağıdaki gibidir:

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

`PEXCEPTION_RECORD` ve `PCONTEXT` işaretçi türleri, içerme dosyasında \<Winnt. h > tanımlanmıştır ve `_EXCEPTION_RECORD` ve `_CONTEXT` içerme dosyasında tanımlanır \<excpt. h >

Özel durum işleyicisi içinde `GetExceptionCode` kullanabilirsiniz. Ancak, yalnızca özel durum filtresi ifadesi içinde `GetExceptionInformation` kullanabilirsiniz. İşaret ettiği bilgiler, genellikle yığındadır ve denetim özel durum işleyicisine aktarıldığında kullanılamaz.

`AbnormalTermination` iç işlev sonlandırma işleyicisinde kullanılabilir. **Try-finally** ifadesinin gövdesi sıralı olarak sonlandığında 0 döndürür. Diğer tüm durumlarda, 1 döndürür.

excpt. h bu iç öğeler için bazı alternatif adlar tanımlar:

`GetExceptionCode` `_exception_code` eşdeğerdir

`GetExceptionInformation` `_exception_info` eşdeğerdir

`AbnormalTermination` `_abnormal_termination` eşdeğerdir

## <a name="example"></a>Örnek

```cpp
// exceptions_try_except_Statement.cpp
// Example of try-except and try-finally statements
#include <stdio.h>
#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION
#include <excpt.h>

int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep)
{
    puts("in filter.");
    if (code == EXCEPTION_ACCESS_VIOLATION)
    {
        puts("caught AV as expected.");
        return EXCEPTION_EXECUTE_HANDLER;
    }
    else
    {
        puts("didn't catch AV, unexpected.");
        return EXCEPTION_CONTINUE_SEARCH;
    };
}

int main()
{
    int* p = 0x00000000;   // pointer to NULL
    puts("hello");
    __try
    {
        puts("in try");
        __try
        {
            puts("in try");
            *p = 13;    // causes an access violation exception;
        }
        __finally
        {
            puts("in finally. termination: ");
            puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");
        }
    }
    __except(filter(GetExceptionCode(), GetExceptionInformation()))
    {
        puts("in except");
    }
    puts("world");
}
```

### <a name="output"></a>Çıktı

```Output
hello
in try
in try
in filter.
caught AV as expected.
in finally. termination:
        abnormal
in except
world
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
