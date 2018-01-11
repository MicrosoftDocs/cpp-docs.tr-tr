---
title: deneyin-except deyimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 240b8ad1b0cfd9c8b85b58c8d2309fb97f961573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="try-except-statement"></a>try-except Deyimi

**Microsoft özel**  
**Deneyin-dışında** ifadesi bir Microsoft uzantısı c ve destekleyen C++ dilleri yapılandırılmış özel durum işleme.  

## <a name="syntax"></a>Sözdizimi  
  
> **__try**   
> {  
>    Korumalı kod  
> }  
> **__except** ( *ifade* )  
> {  
>    özel durum işleyici kodu  
> }  

## <a name="remarks"></a>Açıklamalar

**Deneyin-dışında** ifadesi bir Microsoft uzantısı c ve edinmek için hedef uygulamalar sağlayan C++ dilleri kontrol normalde program yürütme sonlandırmak olayları olduğunda. Bu gibi olaylar adlı *özel durumları*, ve istisnalar ilgilenir mekanizması olarak adlandırılan *yapılandırılmış özel durum işleme* (SEH).

İlgili bilgi için bkz: [try-finally deyimi](../cpp/try-finally-statement.md).

Özel durumlar, donanım tabanlı veya yazılım tabanlı olabilir. Uygulamalar donanım veya yazılım özel durumlarından tamamen kurtarılamadığında bile, yapılandırılmış özel durum işleme hata bilgilerinin görüntülenmesini ve sorunun tanılanmasına yardımcı olmak için uygulamanın iç durumunun yakalanmasını sağlar. Bu, özellikle kolayca yeniden oluşturulamayan aralıklı sorunlar için yararlıdır.

> [!NOTE]
> Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. C++ programları için C++ özel durum işleme mekanizmasını kullanmanız önerilir ([throw deneyin ve catch](../cpp/try-throw-and-catch-statements-cpp.md) deyimleri).

`__try` yan tümcesinden sonra gelen bileşik deyim gövdedir veya korunan bölümdür. `__except` yan tümcesinden sonra gelen bileşik deyim, özel durum işleyicisidir. İşleyici, korunan bölümün gövdesi yürütülürken bir özel durum oluşturulursa yapılacak işlemleri belirtir. Yürütme gibi çalışır:

1. Korunan bölüm yürütülür.

2. Korunan bölümün yürütülmesi sırasında hiçbir özel durum gerçekleşmezse, yürütme işlemine `__except` yan tümcesinden sonra deyimde devam edilir.  

3. Korumalı Bölüm yürütülmesi sırasında bir özel durum oluşur veya korumalı bölüm içindeki herhangi bir yordamı çağıran `__except` *ifade* (adlı *filtre* ifade) değerlendirilir ve değerin özel durumun nasıl işleneceğini belirler. Üç değer vardır:

   **Exceptıon_contınue_executıon (-1)** özel durum kapatılır. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.

   **Exceptıon_contınue_search (0)** özel durumu tanınmıyor. Bir işleyici yığını yukarı ilk içeren için aramaya devam **deneyin-dışında** deyimlerini sonra işleyicileri sonraki en yüksek önceliğe sahip.

   **Exceptıon_execute_handler (1)** özel durum tanınmıyor. `__except` bileşik deyimini yürüterek denetimi özel durum işleyicisine aktarın ve ardından `__except` bloğundan sonra yürütmeye devam edin.

Çünkü `__except` ifadenin C ifade olarak, tek bir değer, koşullu ifade işleci veya virgül işleci sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.

Her uygulamanın kendi özel durum işleyicisi olabilir.

`__try` deyiminin içine atlanamaz, ancak herhangi birinden dışarı atlanabilir. Bir işlem yürütülürken ortasında sonlandırıldıysa özel durum işleyici çağrılmaz bir **deneyin-dışında** deyimi.  
  
Daha fazla bilgi için bkz. Bilgi Bankası makalesi Q315937 : NASIL YAPILIR: Visual C++ Uygulamasında Yığın Taşmasını Yakalama.  
  
## <a name="the-leave-keyword"></a>__leave Anahtar Sözcüğü

`__leave` Anahtar sözcüğü yalnızca korumalı bölümünü içinde geçerli bir **deneyin-dışında** deyimi ve etkisi olan korumalı bölümün sonuna atlamak için. Yürütme, özel durum işleyicisinden sonra ilk deyimde devam eder.

A `goto` deyimi de dışında korumalı bölüm atlayın ve gibi onu performansının düşmesine neden olmayan bir **try-finally** deyimi yığını geriye doğru izleme oluşmaz çünkü. Ancak, korumalı alan büyükse veya karmaşıksa programlama hatası yapma olasılığınız azalacağı için `__leave` deyimi yerine `goto` anahtar sözcüğünü kullanmanızı öneririz.

### <a name="structured-exception-handling-intrinsic-functions"></a>Yapılandırılmış Özel Durum İşleme İç İşlevleri

Yapılandırılmış özel durum işleme ile kullanılabilecek iki iç işlevler sağlar **deneyin-dışında** deyimi: `GetExceptionCode` ve `GetExceptionInformation`.

`GetExceptionCode`özel durum kodunu (32 bit tamsayı) döndürür.

İç işlev `GetExceptionInformation` özel durum hakkında ek bilgi içeren bir yapı için bir işaretçi döndürür. Bu işaretçiyle, donanım özel durumu sırasında var olan makine durumuna erişebilirsiniz. Yapı aşağıdaki gibidir:

```cpp  
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS; 
```  

İşaretçi türleri `PEXCEPTION_RECORD` ve `PCONTEXT` içerme dosyası WINNT tanımlanır. H ve `_EXCEPTION_RECORD` ve `_CONTEXT` içerme dosyası EXCPT tanımlanır. H

Kullanabileceğiniz `GetExceptionCode` özel durum işleyici içinde. Ancak, kullanabileceğiniz `GetExceptionInformation` yalnızca özel durum filtre ifadesi içinde. İşaret ettiği bilgiler, genellikle yığındadır ve denetim özel durum işleyicisine aktarıldığında kullanılamaz.

İç işlev `AbnormalTermination` sonlandırma işleyicisi içinde kullanılabilir. İse 0 döndürür gövdesini **try-finally** açıklamayı sonlandıran sıralı olarak. Diğer tüm durumlarda, 1 döndürür.

EXCPT.H, bu iç öğeler için bazı alternatif adlar tanımlar:

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
  
## <a name="output"></a>Çıkış  
  
```  
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

**SON Microsoft özel**  

## <a name="see-also"></a>Ayrıca Bkz.

[Bir özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)   
[Yapılandırılmış özel durum işleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
