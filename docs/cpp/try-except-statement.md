---
title: try-except deyimi
description: Microsoft C++ __try ve __except yapılandırılmış özel durum işleme deyimlerine başvurur.
ms.date: 04/03/2020
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- _exception_info
- __except
- _except
- _exception_code
- __except_cpp
- _exception_info_cpp
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
ms.openlocfilehash: 132edf7cc9819637fafa3947686972d311924b99
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366233"
---
# <a name="try-except-statement"></a>try-except deyimi

**Deneme dışı** deyimi, C ve C++ dillerinde yapılandırılmış özel durum işlemeyi destekleyen bir Microsoft uzantısıdır. Bu uzantı **Microsoft'a özgüdür.**

## <a name="syntax"></a>Sözdizimi

> **\_\_Deneyin**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;korunan kod<br/>
> }<br/>
> hariç ( *ifade* ) ** \_ \_**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;özel durum işleyicisi kodu<br/>
> }

## <a name="remarks"></a>Açıklamalar

**Try-except** deyimi C ve C++ dillerine microsoft uzantısıdır. Normalde program yürütmesini sonlandıran olaylar oluştuğunda hedef uygulamaların denetim kazanmasını sağlar. Bu tür *olaylar, yapılandırılmış özel durumlar*veya kısa özel *durumlar* olarak adlandırılır. Bu özel durumlarla ilgilenen mekanizmaya *yapılandırılmış özel durum işleme* (SEH) adı verilir.

İlgili bilgiler [için, try-finally deyimine](../cpp/try-finally-statement.md)bakın.

Özel durumlar donanım tabanlı veya yazılım tabanlı olabilir. Yapılandırılmış özel durum işleme, uygulamalar donanım veya yazılım özel durumlarından tamamen kurtarılamasa bile yararlıdır. SEH, sorunu tanılamaya yardımcı olmak için hata bilgilerini görüntülemeyi ve uygulamanın iç durumunu bindirmeyi mümkün kılar. Özellikle çoğaltması kolay olmayan aralıklı sorunlar için kullanışlıdır.

> [!NOTE]
> Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, c++ için özel olarak tasarlanmaz. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. C++ programları için, yerel C++ özel durum işleme: [denemeler, yakalama ve ifadeleri atma](../cpp/try-throw-and-catch-statements-cpp.md) kullanmanızı öneririz.

**__try** maddesinden sonra bileşik deyimi *gövde* veya *korunan* bölümdür. **__except** ifadesi *filtre* ifadesi olarak da bilinir. Değeri, özel durum nasıl işleneceğini belirler. **__except** yan tümcesi sonra bileşik deyimi istisna işleyicisidir. Işleyici, gövde bölümünün yürütülmesi sırasında bir özel durum yükseltilirse yapılacak eylemleri belirtir. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Korunan bölümün yürütülmesi sırasında bir istisna oluşmaz ise, **__except** maddesi sonra açıklamada yürütme devam eder.

1. Korunan bölümün yürütülmesi sırasında veya herhangi bir rutinde korunan bölüm çağrıları sırasında bir özel durum oluşursa, **__except** ifadesi değerlendirilir. Üç olası değer vardır:

   - `EXCEPTION_CONTINUE_EXECUTION`(-1) İstisna reddedildi. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.

   - `EXCEPTION_CONTINUE_SEARCH`(0) İstisna tanınmaz. Önce **deneme dışı** ifadeler, sonra sonraki en yüksek önceliğe sahip işleyiciler için bir işleyici için yığını aramaya devam edin.

   - `EXCEPTION_EXECUTE_HANDLER`(1) İstisna tanınır. **__except** bileşik deyimini çalıştırarak denetimi exception işleyicisine aktarın, ardından **__except** bloğundan sonra yürütmeye devam edin.

__except **__except** ifadesi C ifadesi olarak değerlendirilir. Tek bir değerle, koşullu ifade işleciyle veya virgül işleciyle sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.

Her uygulamanın kendi özel durum işleyicisi olabilir.

**__try** bir ifadeye atlamak geçerli değil, ama birinden atlamak için geçerlidir. Bir işlem **deneme dışı** deyimi yürütmenin ortasında sonlandırılırsa, özel durum işleyicisi çağrılmaz.

Önceki sürümlerle uyumluluk **için, _try,** **_except**ve **_leave,** derleyici seçeneği [/Za \(Dil uzantılarını devre dışı kılmıyorsa](../build/reference/za-ze-disable-language-extensions.md) __try , **__except**ve **__leave** eş anlamlıdır. **_leave**

### <a name="the-__leave-keyword"></a>__leave Anahtar Sözcüğü

**__leave** anahtar sözcüğü yalnızca **deneme hariç** ifadesinin korunan bölümünde geçerlidir ve etkisi korunan bölümün sonuna atlamaktır. Yürütme, özel durum işleyicisinden sonra ilk deyimde devam eder.

**Goto** deyimi korunan bölümden de atlayabilir ve **deneme-son** deyiminde olduğu gibi performansı düşürmez. Çünkü yığın gevşeme sönme gerçekleşmez. Ancak, **goto** deyimi yerine **__leave** anahtar sözcüğü kullanmanızı öneririz. Bunun nedeni, korunan bölüm büyük veya karmaşıksa programlama hatası yapma olasılığınız daha düşük olmasıdır.

### <a name="structured-exception-handling-intrinsic-functions"></a>Yapılandırılmış Özel Durum İşleme İç İşlevleri

Yapılandırılmış özel durum işleme, **try-except** deyimiyle kullanılabilen iki içsel işlev sağlar: [GetExceptionCode](/windows/win32/Debug/getexceptioncode) ve [GetExceptionInformation](/windows/win32/Debug/getexceptioninformation).

`GetExceptionCode`özel durum kodunu (32 bit tamsayı) döndürür.

İçsel işlev, `GetExceptionInformation` özel durum hakkında ek bilgiler içeren [bir EXCEPTION_POINTERS](/windows/win32/api/winnt/ns-winnt-exception_pointers) yapısına bir işaretçiyi döndürür. Bu işaretçiyle, donanım özel durumu sırasında var olan makine durumuna erişebilirsiniz. Yapı aşağıdaki gibidir:

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

İşaretçi `PEXCEPTION_RECORD` türleri `PCONTEXT` ve include dosya \<winnt.h> `_EXCEPTION_RECORD` `_CONTEXT` tanımlanır ve include \<dosya excpt.h> tanımlanır

Özel durum `GetExceptionCode` işleyicisi içinde kullanabilirsiniz. Ancak, yalnızca `GetExceptionInformation` özel durum filtresi ifadesi içinde kullanabilirsiniz. Işaret ettiği bilgiler genellikle yığındadır ve denetim özel durum işleyicisine aktarıldığında artık kullanılamaz.

İçsel fonksiyon [AnormalSon verme](/windows/win32/Debug/abnormaltermination) bir sonlandırma işleyicisi içinde kullanılabilir. **Try-finally** deyiminin gövdesi sırayla sona ererse 0 döndürür. Diğer tüm durumlarda, 1 döndürür.

\<excpt.h> bu içsel ler için bazı alternatif adlar tanımlar:

`GetExceptionCode`eşdeğerdir`_exception_code`

`GetExceptionInformation`eşdeğerdir`_exception_info`

`AbnormalTermination`eşdeğerdir`_abnormal_termination`

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

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
