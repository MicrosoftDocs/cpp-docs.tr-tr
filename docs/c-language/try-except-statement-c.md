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
ms.openlocfilehash: 9940fdf983f6141c0de207509bb800533b0f1eb8
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152332"
---
# <a name="try-except-statement-c"></a>try-except Deyimi (C)

**Microsoft'a özgü**

**Deneyin-dışında** deyimi, uygulamaların normal olarak yürütülmesini sonlandıran olaylar gerçekleştiğinde bir programın denetimini sağlar C diline yönelik bir Microsoft uzantısıdır. Böyle olaylara özel durumlar, özel durumlarla uğraşan mekanizmaya ise yapılandırılmış özel durum işleme adı verilir.

Özel durumlar ya da donanım veya yazılım tabanlı olabilir. Uygulamalar donanım veya yazılım özel durumlarından tamamen kurtarılamadığında bile, yapılandırılmış özel durum işleme hata bilgilerinin görüntülenmesini ve sorunun tanılanmasına yardımcı olmak için uygulamanın iç durumunun yakalanmasını sağlar. Bu, özellikle kolayca yeniden oluşturulamayan aralıklı sorunlar için yararlıdır.

## <a name="syntax"></a>Sözdizimi

*try haricinde deyimi*: **__try** *bileşik deyim* 

**__except (** *ifade* **)** *bileşik deyim* 

Sonra gelen bileşik deyim `__try` yan tümcesi ise korunan bölümün. 
  `__except` yan tümcesinden sonra gelen bileşik deyim, özel durum işleyicisidir. İşleyici, bir dizi korunan bölümün yürütülmesi sırasında bir özel durum oluşturulursa gerçekleştirilecek eylemi belirtir. Yürütme aşağıdaki gibi çalışır:

1. Korunan bölüm yürütülür.

1. Korunan bölümün yürütülmesi sırasında hiçbir özel durum gerçekleşmezse, yürütme işlemine `__except` yan tümcesinden sonra deyimde devam edilir.

1. Özel bir durum oluştuğunda korunan bölümün yürütülmesi sırasında veya korunan bölümün çağırdığı herhangi bir yordamda `__except` ifade değerlendirilir ve döndürülen değer özel durumun nasıl işlendiğini belirler. Üç değer vardır:

   `EXCEPTION_CONTINUE_SEARCH` Özel durum tanınmıyor. Yığında bir işleyici ilk içeren için aramaya devam edin **deneyin-dışında** deyimleri, ardından sonraki en yüksek önceliğe sahip işleyicileri için.

   `EXCEPTION_CONTINUE_EXECUTION` Özel durum kabul edilen ancak kapatıldı. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.

   `EXCEPTION_EXECUTE_HANDLER` Özel durum tanınır. Yürüterek denetimi özel durum işleyicisine aktarma `__except` bileşik deyim, sonra yürütme özel durumun oluştuğu noktadan devam edin.

Çünkü `__except` ifadesi C ifadesi olarak değerlendirildiği, tek bir değer, koşullu ifade işleci veya virgül işlecinin sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.

> [!NOTE]
>  Yapılandırılmış özel durum işleme, C ve C++ kaynak dosyaları ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme mekanizmasını daha esnek, her türden özel durumları işleyebilir olmamasıdır.

> [!NOTE]
>  C++ programları için C++ özel durum işleme, yapılandırılmış özel durum işleme yerine kullanılmalıdır. Daha fazla bilgi için [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md) içinde *C++ dil başvurusu*.

Bir uygulamada her bir rutin kendi özel durum işleyicisi olabilir. `__except` Deyimi yürütür kapsamında `__try` gövdesi. Başka bir deyişle, var. bildirilen herhangi bir yerel değişkenlere erişebilir.

`__leave` Sözcüktür içinde geçerli bir **deneyin-dışında** deyim bloğu. Etkisini `__leave` sonuna başlayabiliriz **deneyin-dışında** blok. Yürütme, özel durum işleyicisi sonunda sürdürür. Ancak bir `goto` deyimi aynı sonuca ulaşmak için kullanılabilir bir `goto` deyimi, yığın geriye doğru izleme neden olur. `__leave` Deyimi olduğundan daha verimli yığın geriye doğru izleme gerektirmez.

Çıkmadan bir **deneyin-dışında** using deyimi `longjmp` çalışma zamanı işlevi olağan dışı sonlandırma olarak kabul edilir. Bloğuna atlamak için geçersiz bir `__try` deyimi, ancak yasal birinden dışarı atlanabilir. Özel durum işleyicisi bir işlem yürütülürken sonlandırılırsa sonlandırılırsa çağrılmaz bir **deneyin-dışında** deyimi.

## <a name="example"></a>Örnek

Özel durum işleyicisi ve bir sonlandırma işleyicisi örneği aşağıda verilmiştir. Bkz: [try-finally deyimi](../c-language/try-finally-statement-c.md) sonlandırma işleyicileri hakkında daha fazla bilgi.

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

Bu örnekte, sağ tarafta eklenen açıklamalar ile çıktı.

```
hello
in try              /* fall into try                     */
in try              /* fall into nested try                */
in filter           /* execute filter; returns 1 so accept  */
in finally          /* unwind nested finally                */
in except           /* transfer control to selected handler */
world               /* flow out of handler                  */
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[try-except Deyimi](../cpp/try-except-statement.md)
