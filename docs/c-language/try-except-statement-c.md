---
title: try-except deyimi (C)
description: Microsoft C/C++, bir try-except deyimin dil uzantısı kullanarak yapılandırılmış özel durum Işleme (SEH) uygular.
ms.date: 08/24/2020
helpviewer_keywords:
- try-except keyword [C]
- structured exception handling, try-except
- try-catch keyword [C]
- __try keyword [C]
- __except keyword [C]
- __except keyword [C], in try-except
- try-catch keyword [C], try-except keyword [C]
ms.assetid: f76db9d1-fc78-417f-b71f-18e545fc01c3
ms.openlocfilehash: e327150431fef3384f2b98940939444b2e6d96ea
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898720"
---
# <a name="try-except-statement-c"></a>try-except deyimi (C)

**Microsoft'a özgü**

Bu `try-except` ifade, uygulamaların normalde yürütmeyi sonlandıran olaylar gerçekleştiğinde bir programın denetimini ele geçirmesine olanak tanıyan C diline yönelik bir Microsoft uzantısıdır. Böyle olaylara özel durumlar, özel durumlarla uğraşan mekanizmaya ise yapılandırılmış özel durum işleme adı verilir.

Özel durumlar donanım ya da yazılım tabanlı olabilir. Uygulamalar, donanım veya yazılım özel durumlarından tamamen kurtarılamadığında bile, yapılandırılmış özel durum işleme hata bilgilerini günlüğe kaydetme ve görüntüleme olanağı sağlar. Sorunu tanılamanıza yardımcı olması için uygulamanın iç durumunu yakalamak yararlıdır. Özellikle, yeniden oluşturulması kolay olmayan aralıklı sorunlar için yararlıdır.

## <a name="syntax"></a>Syntax

> *`try-except-statement`*:\
> &emsp;**`__try`** *`compound-statement`* **`__except (`**  *`expression`*  **`)`** *`compound-statement`*

Yan tümcesinden sonraki bileşik ifade, **`__try`** *korunan bölümdür*. Yan tümcesinden sonraki bileşik ifade **`__except`** *özel durum işleyicisidir*. İşleyici, korunan bölümün yürütülmesi sırasında bir özel durum ortaya çıktığında gerçekleştirilecek bir eylem kümesi belirtir. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Korunan bölümün yürütülmesi sırasında hiçbir özel durum oluşursa, yürütme yan tümcesinden sonraki deyimden sonra devam eder **`__except`** .

1. Korunan bölümün yürütülmesi sırasında veya korunan bölümün çağırdığı herhangi bir yordamında bir özel durum oluşursa, **`__except`** ifade değerlendirilir. Döndürülen değer, özel durumun nasıl işlendiğini belirler. Üç olası değer vardır:

   - `EXCEPTION_CONTINUE_SEARCH`: Özel durum tanınmıyor. Bir işleyicinin yığın için, önce kapsayan `try-except` deyimler için, sonra da sonraki en yüksek önceliğe sahip işleyiciler için arama yapmaya devam edin.

   - `EXCEPTION_CONTINUE_EXECUTION`: Özel durum tanınır ancak kapatılır. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.

   - `EXCEPTION_EXECUTE_HANDLER` Özel durum tanınır. Bileşik ifadeyi yürüterek denetimi özel durum işleyicisine aktarın **`__except`** , sonra özel durumun oluştuğu noktada yürütmeye devam edin.

**`__except`** İfade bir C ifadesi olarak değerlendirildiğinden, tek bir değer, koşullu ifade işleci veya virgül işleci ile sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.

> [!NOTE]
> Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalarıyla birlikte çalışmaktadır. Ancak, özellikle C++ için tasarlanmamıştır. Taşınabilir C++ programları için, yapılandırılmış özel durum işleme yerine C++ özel durum işleme kullanılmalıdır. Ayrıca, C++ özel durum işleme mekanizması, herhangi bir türdeki özel durumları işleyebilmek için çok daha esnektir. Daha fazla bilgi için bkz. *C++ dil başvurusunda* [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md) .

Bir uygulamadaki her bir yordam kendi özel durum işleyicisine sahip olabilir. **`__except`** İfade, **`__try`** gövdenin kapsamında yürütülür. Burada belirtilen yerel değişkenlere erişim sağlar.

**`__leave`** Anahtar sözcüğü bir `try-except` Ekstre bloğunda geçerlidir. Öğesinin etkisi, **`__leave`** bloğun sonuna atlamanız `try-except` . Yürütme, özel durum işleyicisinin sonundan sonra devam eder. **`goto`** Aynı sonucu elde etmek için bir ifade kullanılabilse de, bir **`goto`** ifade yığın geri sarma oluşmasına neden olur. **`__leave`** İfade, yığın geri sarma içermediğinden daha etkilidir.

`try-except`Çalışma zamanı işlevini kullanarak bir deyimden çıkmak `longjmp` olağan dışı sonlandırma olarak değerlendirilir. Bir deyime geçmek yasal değildir **`__try`** , ancak bir ifadeye geçmek yasal değildir. Özel durum işleyicisi, bir işlem bir deyimin yürütülmesi ortasında sonlandırılabilecek şekilde çağrılmaz `try-except` .

## <a name="example"></a>Örnek

Bir özel durum işleyicisine ve sonlandırma işleyicisine bir örnek aşağıda verilmiştir. Sonlandırma işleyicileri hakkında daha fazla bilgi için bkz. [ `try-finally` (C)](../c-language/try-finally-statement-c.md).

```C
.
.
.
puts("hello");
__try {
   puts("in try");
   __try {
      puts("in try");
      RAISE_AN_EXCEPTION();
   } __finally {
      puts("in finally");
   }
} __except( puts("in filter"), EXCEPTION_EXECUTE_HANDLER ) {
   puts("in except");
}
puts("world");
```

Aşağıda, doğru yorum eklenerek, örneğin çıktısı aşağıda verilmiştir:

```Output
hello
in try              /* fall into try                        */
in try              /* fall into nested try                 */
in filter           /* execute filter; returns 1 so accept  */
in finally          /* unwind nested finally                */
in except           /* transfer control to selected handler */
world               /* flow out of handler                  */
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`try-except` ifade (C++)](../cpp/try-except-statement.md)
