---
title: try-except deyimi
description: __Try ve yapılandırılmış özel durum işleme deyimlerinin __except Microsoft C++ başvurusu.
ms.date: 08/25/2020
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
ms.openlocfilehash: 226c3a3df39f284d9c1267051114fc39db358f55
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898617"
---
# <a name="try-except-statement"></a>`try-except` Ekstre

`try-except`Bu ifade, C ve C++ dillerinde yapılandırılmış özel durum işlemeyi destekleyen, **Microsoft 'a özgü** bir uzantıdır.

```cpp
    // . . .
    __try {
        // guarded code
    }
    __except ( /* filter expression */ ) {
        // termination code
    }
    // . . .
```

## <a name="grammar"></a>Dilbilgisi

> *`try-except-statement`*:\
> &emsp;**`__try`** *`compound-statement`* **`__except (`**  *`expression`*  **`)`** *`compound-statement`*

## <a name="remarks"></a>Açıklamalar

`try-except`İfade, C ve C++ dillerinin Microsoft uzantısıdır. Bu, normalde program yürütmesini sonlandıran olaylar gerçekleştiğinde hedef uygulamaların denetim kazanmasını sağlar. Bu olaylar *yapılandırılmış özel durumlar*veya kısa için *özel durumlar* olarak adlandırılır. Bu özel durumlarla ilgilenen mekanizmaya *yapılandırılmış özel durum işleme* (SEH) denir.

İlgili bilgiler için, [try-finally ifadesine](../cpp/try-finally-statement.md)bakın.

Özel durumlar, donanım tabanlı ya da yazılım tabanlı olabilir. Yapılandırılmış özel durum işleme, uygulamalar donanım veya yazılım özel durumlarından tamamen kurtarılamadığında bile yararlıdır. SEH sorunu tanılamanıza yardımcı olması için hata bilgilerini görüntülemeyi ve uygulamanın iç durumunu yakalamayı olanaklı kılar. Bu, özellikle yeniden oluşturulması kolay olmayan aralıklı sorunlar için yararlıdır.

> [!NOTE]
> Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, C++ için özel olarak tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. C++ programları için yerel C++ özel durum işleme: [try, catch ve throw](../cpp/try-throw-and-catch-statements-cpp.md) deyimlerini kullanmanızı öneririz.

Yan tümcesinden sonraki bileşik ifade **`__try`** *gövde* veya *korumalı* bölümdür. **`__except`** İfade, *filtre* ifadesi olarak da bilinir. Değeri, özel durumun nasıl işlendiğini belirler. Yan tümcesinden sonraki bileşik ifade **`__except`** özel durum işleyicisidir. İşleyici, gövde bölümünün yürütülmesi sırasında bir özel durum ortaya çıktığında gerçekleştirilecek eylemleri belirtir. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Korunan bölümün yürütülmesi sırasında hiçbir özel durum oluşursa, yürütme yan tümcesinden sonraki deyimden sonra devam eder **`__except`** .

1. Korunan bölümün yürütülmesi sırasında veya korunan bölümün çağırdığı herhangi bir yordamında bir özel durum oluşursa, **`__except`** ifade değerlendirilir. Üç olası değer vardır:

   - `EXCEPTION_CONTINUE_EXECUTION` (-1) Özel durum kapatıldı. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.

   - `EXCEPTION_CONTINUE_SEARCH` (0) özel durum tanınmıyor. Bir işleyicinin yığın için, önce kapsayan `try-except` deyimler için, sonra da sonraki en yüksek önceliğe sahip işleyiciler için arama yapmaya devam edin.

   - `EXCEPTION_EXECUTE_HANDLER` (1) özel durum tanınmıyor. Bileşik ifadeyi yürüterek denetimi özel durum işleyicisine aktarın **`__except`** , sonra bloktan sonra yürütmeye devam edin **`__except`** .

**`__except`** İfade bir C ifadesi olarak değerlendirilir. Tek bir değer, koşullu ifade işleci veya virgül işleciyle sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.

Her uygulamanın kendi özel durum işleyicisi olabilir.

Bir ifadeye geçmek için geçerli değildir **`__try`** , ancak bunlardan birine geçmek için geçerli değildir. Özel durum işleyicisi, bir işlem bir deyimin yürütülmesi ortasında sonlandırılırsa çağrılmaz `try-except` .

Önceki sürümlerle uyumluluk için, **_try**, **_Except**ve **_leave** **`__try`** ,, **`__except`** ve **`__leave`** [< za \( dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, ve için eş anlamlılardır.

### <a name="the-__leave-keyword"></a><a name="__leave"></a>`__leave`Anahtar sözcüğü

**`__leave`** Anahtar sözcüğü, yalnızca bir deyimin korunan bölümünde geçerlidir `try-except` ve etkisi, korunan bölümün sonuna atlamanız olur. Yürütme, özel durum işleyicisinden sonra ilk deyimde devam eder.

Bir **`goto`** deyim ayrıca korunan bölümden de geçebilir ve bir **try-finally** ifadesinde olduğu gibi performansı düşürür. Bunun nedeni yığın geri sarma gerçekleşmiyor. Ancak, **`__leave`** bir deyimleri yerine anahtar sözcüğünü kullanmanızı öneririz **`goto`** . Bunun nedeni, korunan bölüm büyük veya karmaşık olduğunda bir programlama hatası yapma olasılığınız düşüktür.

### <a name="structured-exception-handling-intrinsic-functions"></a>Yapılandırılmış özel durum işleme iç işlevleri

Yapılandırılmış özel durum işleme `try-except` : [GetExceptionCode](/windows/win32/Debug/getexceptioncode) ve [GetExceptionInformation](/windows/win32/Debug/getexceptioninformation)ifadesiyle birlikte kullanılabilecek iki iç işlev sağlar.

`GetExceptionCode` özel durumun kodunu (32 bitlik bir tamsayı) döndürür.

İç işlev `GetExceptionInformation` , özel durum hakkında ek bilgi içeren [EXCEPTION_POINTERS](/windows/win32/api/winnt/ns-winnt-exception_pointers) yapısına bir işaretçi döndürür. Bu işaretçiyle, donanım özel durumu sırasında var olan makine durumuna erişebilirsiniz. Yapı aşağıdaki gibidir:

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

İşaretçi türleri `PEXCEPTION_RECORD` ve `PCONTEXT` içerme dosyasında tanımlanır ve \<winnt.h> `_EXCEPTION_RECORD` `_CONTEXT` içerme dosyasında tanımlanır \<excpt.h>

`GetExceptionCode`Özel durum işleyicisi içinde kullanabilirsiniz. Ancak, `GetExceptionInformation` yalnızca özel durum filtresi ifadesi içinde kullanabilirsiniz. İşaret ettiği bilgiler genellikle yığında olur ve denetim özel durum işleyicisine aktarıldığında artık kullanılamaz.

İç işlev olan [Abnormalsonlandırmayı](/windows/win32/Debug/abnormaltermination) sonlandırma işleyicisinde kullanılabilir. **Try-finally** ifadesinin gövdesi sıralı olarak sonlandığında 0 döndürür. Diğer tüm durumlarda, 1 döndürür.

\<excpt.h> Bu iç bilgiler için bazı alternatif adları tanımlar:

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

[Özel Durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
