---
title: try-except Deyimi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- try-except keyword [C]
- structured exception handling, try-except
- try-catch keyword [C]
- __try keyword [C]
- __except keyword [C]
- __except keyword [C], in try-except
- try-catch keyword [C], try-except keyword [C]
ms.assetid: f76db9d1-fc78-417f-b71f-18e545fc01c3
ms.openlocfilehash: 77b6bea8c7793522f5e1fa47e09a9b4a7e5c0f10
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218786"
---
# <a name="try-except-statement-c"></a>try-except Deyimi (C)

**Microsoft'a Özgü**

**Try-except** deyimleri, uygulamaların normalde yürütmeyi sonlandıran olaylar gerçekleştiğinde bir programın denetimini elde etmesine olanak tanıyan C diline yönelik bir Microsoft uzantısıdır. Böyle olaylara özel durumlar, özel durumlarla uğraşan mekanizmaya ise yapılandırılmış özel durum işleme adı verilir.

Özel durumlar donanım ya da yazılım tabanlı olabilir. Uygulamalar donanım veya yazılım özel durumlarından tamamen kurtarılamadığında bile, yapılandırılmış özel durum işleme hata bilgilerinin görüntülenmesini ve sorunun tanılanmasına yardımcı olmak için uygulamanın iç durumunun yakalanmasını sağlar. Bu, özellikle kolayca yeniden oluşturulamayan aralıklı sorunlar için yararlıdır.

## <a name="syntax"></a>Sözdizimi

*try-except-deyimin*: **__try**  *bileşik ifade*

**__except (**  *ifade*  **)**  *bileşik deyim*

Yan tümcesinden sonraki bileşik ifade, `__try` korunan bölümdür. Yan tümcesinden sonraki bileşik ifade **`__except`** özel durum işleyicisidir. İşleyici, korunan bölümün yürütülmesi sırasında bir özel durum ortaya çıktığında gerçekleştirilecek bir eylem kümesi belirtir. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Korunan bölümün yürütülmesi sırasında hiçbir özel durum oluşursa, yürütme yan tümcesinden sonraki deyimden sonra devam eder **`__except`** .

1. Korunan bölümün yürütülmesi sırasında veya korunan bölüm çağrısı sırasında bir özel durum oluşursa, **`__except`** ifade değerlendirilir ve döndürülen değer özel durumun işlenme şeklini belirler. Üç değer vardır:

   `EXCEPTION_CONTINUE_SEARCH`Özel durum tanınmıyor. İlk olarak **try-except** deyimlerini içeren işleyiciler için bir işleyici için yığın aramaya devam edin, ardından bir sonraki en yüksek önceliğe sahip işleyiciler için.

   `EXCEPTION_CONTINUE_EXECUTION`Özel durum tanınmıyor ancak kapatıldı. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.

   `EXCEPTION_EXECUTE_HANDLER`Özel durum tanınmıyor. Bileşik ifadeyi yürüterek denetimi özel durum işleyicisine aktarın **`__except`** , sonra özel durumun oluştuğu noktada yürütmeye devam edin.

**`__except`** İfade bir C ifadesi olarak değerlendirildiğinden, tek bir değer, koşullu ifade işleci veya virgül işleci ile sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.

> [!NOTE]
> Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalarıyla birlikte çalışmaktadır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme mekanizması, herhangi bir türdeki özel durumları işleyebilmek için çok daha esnektir.

> [!NOTE]
> C++ programları için, yapılandırılmış özel durum işleme yerine C++ özel durum işleme kullanılmalıdır. Daha fazla bilgi için bkz. *C++ dil başvurusunda* [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md) .

Bir uygulamadaki her bir yordam kendi özel durum işleyicisine sahip olabilir. **`__except`** İfade, `__try` gövdenin kapsamında yürütülür. Bu, burada belirtilen yerel değişkenlere erişim olduğu anlamına gelir.

** `__leave** keyword is valid within a **try-except** statement block. The effect of **` __Leave** **try-except** bloğunun sonuna atlayamıyor. Yürütme, özel durum işleyicisinin sonundan sonra devam eder. **`goto`** Aynı sonucu elde etmek için bir ifade kullanılabilse de, bir **`goto`** ifade yığın geri sarma oluşmasına neden olur. Yığın geri sarma içermediğinden **' __leave** deyimin daha etkilidir.

Çalışma zamanı işlevini kullanarak bir **try-except** ifadesinden çıkmak `longjmp` olağan dışı sonlandırma olarak değerlendirilir. Bir ifadeye geçmek geçersizdir `__try` , ancak bunlardan biri atlanmak için geçerli değildir. Özel durum işleyicisi, bir işlem bir **try-except** ifadesinin ortasında sonlandırılabilmesi çağrılmaz.

## <a name="example"></a>Örnek

Aşağıda bir özel durum işleyicisine ve sonlandırma işleyicisine bir örnek verilmiştir. Sonlandırma işleyicileri hakkında daha fazla bilgi için [try-finally bildirimine](../c-language/try-finally-statement-c.md) bakın.

```
.
.
.
puts("hello");
__try{
   puts("in try");
   __try{
      puts("in try");
      RAISE_AN_EXCEPTION();
   }__finally{
      puts("in finally");
   }
}__except( puts("in filter"), EXCEPTION_EXECUTE_HANDLER ){
   puts("in except");
}
puts("world");
```

Bu, doğru yorum eklendikten sonra, örneğin çıktıdır:

```
hello
in try              /* fall into try                     */
in try              /* fall into nested try                */
in filter           /* execute filter; returns 1 so accept  */
in finally          /* unwind nested finally                */
in except           /* transfer control to selected handler */
world               /* flow out of handler                  */
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[try-except ekstresi](../cpp/try-except-statement.md)
