---
title: deneyin-except deyimi | Microsoft Docs
ms.custom: ''
ms.date: 10/05/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e938f5b7e5f25461ae921fbfa3c49920eca86eb
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861934"
---
# <a name="try-except-statement"></a>try-except Deyimi

**Microsoft'a özgü**

**Deneyin-dışında** ifadesi bir Microsoft uzantısı c ve C++ dilleri destekleyen yapılandırılmış özel durum işleme.

## <a name="syntax"></a>Sözdizimi

> **__try** <br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;Korumalı kod<br/>
> }<br/>
> **__except** ( *ifade* )<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;özel durum işleyici kodu<br/>
> }<br/>

## <a name="remarks"></a>Açıklamalar

**Deneyin-dışında** deyimi, C için bir Microsoft uzantısıdır ve edinmek için hedef uygulamalar sağlayan C++ dilleri, normalde programın yürütülmesini sonlandıran olaylar gerçekleştiğinde denetim. Bu tür olayların adlı *özel durumları*, ve uğraşan mekanizması olarak adlandırılan *yapılandırılmış özel durum işleme* (SEH).

İlgili bilgiler için bkz. [try-finally deyimi](../cpp/try-finally-statement.md).

Özel durumlar, donanım tabanlı veya yazılım tabanlı olabilir. Uygulamalar donanım veya yazılım özel durumlarından tamamen kurtarılamadığında bile, yapılandırılmış özel durum işleme hata bilgilerinin görüntülenmesini ve sorunun tanılanmasına yardımcı olmak için uygulamanın iç durumunun yakalanmasını sağlar. Bu, özellikle kolayca yeniden oluşturulamayan aralıklı sorunlar için yararlıdır.

> [!NOTE]
> Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. C++ programları için C++ özel durum işleme mekanizmasını kullanmanız önerilir ([try, catch ve throw](../cpp/try-throw-and-catch-statements-cpp.md) deyimleri).

Sonra gelen bileşik deyim **__try** yan tümcesi ise gövdedir veya korunan bölümdür. Sonra gelen bileşik deyim **__except** yan tümcesi özel durum işleyicisidir. İşleyici, korunan bölümün gövdesi yürütülürken bir özel durum oluşturulursa yapılacak işlemleri belirtir. Yürütme aşağıdaki gibi çalışır:

1. Korunan bölüm yürütülür.

1. Korunan bölümün yürütülmesi sırasında hiçbir özel durum oluşursa yürütme tümcesinden sonraki deyimden devam eder **__except** yan tümcesi.

1. Özel bir durum oluştuğunda korunan bölümün yürütülmesi sırasında veya korunan bölümün çağırdığı herhangi bir yordamda **__except** *ifade* (adlı *filtre* ifade) değerlendirilir ve değer özel durumun nasıl işlendiğini belirler. Üç olası değer vardır:

   - Exceptıon_contınue_executıon (-1) özel durum kapatıldı. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.

   - Exceptıon_contınue_search (0) özel durum tanınmıyor. Yığında bir işleyici ilk içeren için aramaya devam edin **deneyin-dışında** deyimleri, ardından sonraki en yüksek önceliğe sahip işleyicileri için.

   - Exceptıon_execute_handler (1) özel durum tanınır. Yürüterek denetimi özel durum işleyicisine aktarma **__except** bileşik deyimini sonra yürütmeye devam **__except** blok.

Çünkü **__except** ifadesi C ifadesi olarak değerlendirildiği, tek bir değer, koşullu ifade işleci veya virgül işlecinin sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.

Her uygulamanın kendi özel durum işleyicisi olabilir.

İçine atlanamaz değil bir **__try** deyimi, ancak herhangi birinden dışarı atlanabilir. Özel durum işleyicisi bir işlem yürütülürken sonlandırılırsa sonlandırılırsa çağrılmaz bir **deneyin-dışında** deyimi.

### <a name="the-leave-keyword"></a>__leave Anahtar Sözcüğü

**__Leave** anahtar sözcüğü yalnızca korunan bölümünde geçerlidir bir **deneyin-dışında** deyimi ve etkisi korunan bölümün sonuna atlama etmektir. Yürütme, özel durum işleyicisinden sonra ilk deyimde devam eder.

A **goto** deyimi korumalı bölümün dışına da atlayabilir ve olduğu gibi performansı düşmez bir **try-finally** deyimi yığın geriye doğru izleme gerçekleşmediği için. Ancak, kullanmanızı öneririz **__leave** anahtar sözcüğü yerine **goto** deyimi korunan bölümün büyük veya karmaşık ise programlama hata yapma olasılığını olduğundan.

### <a name="structured-exception-handling-intrinsic-functions"></a>Yapılandırılmış Özel Durum İşleme İç İşlevleri

Yapılandırılmış özel durum işleme ile kullanılabilecek iki iç işlev sağlar **deneyin-dışında** deyimi: `GetExceptionCode` ve `GetExceptionInformation`.

`GetExceptionCode` özel durum kodunu (32-bit tamsayı) döndürür.

İç işlevi `GetExceptionInformation` özel durum hakkında ek bilgi içeren bir yapıya bir işaretçi döndürür. Bu işaretçiyle, donanım özel durumu sırasında var olan makine durumuna erişebilirsiniz. Yapı aşağıdaki gibidir:

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

İşaretçi türleri `PEXCEPTION_RECORD` ve `PCONTEXT` içerme dosyasında tanımlanır \<winnt.h >, ve `_EXCEPTION_RECORD` ve `_CONTEXT` içerme dosyasında tanımlanır \<excpt.h >

Kullanabileceğiniz `GetExceptionCode` içinde özel durum işleyicisi. Ancak, kullanabileceğiniz `GetExceptionInformation` yalnızca özel durum filtresi ifadesinde. İşaret ettiği bilgiler, genellikle yığındadır ve denetim özel durum işleyicisine aktarıldığında kullanılamaz.

İç işlevi `AbnormalTermination` sonlandırma işleyicisinin içerisinde kullanılabilir. 0 döndürür gövdesinin **try-finally** sırayla deyimini sonlandırır. Diğer tüm durumlarda, 1 döndürür.

excpt.h, bu iç öğeler için bazı alternatif adlar tanımlar:

`GetExceptionCode` eşdeğerdir `_exception_code`

`GetExceptionInformation` eşdeğerdir `_exception_info`

`AbnormalTermination` eşdeğerdir `_abnormal_termination`

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

### <a name="output"></a>Çıkış

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
