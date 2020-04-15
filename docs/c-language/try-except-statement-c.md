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
ms.openlocfilehash: 2ca5299a5ab20b8985a520f25bb654ead0c25e2b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349735"
---
# <a name="try-except-statement-c"></a>try-except Deyimi (C)

**Microsoft'a Özgü**

**Deneme dışında** deyimi, normalde yürütmeyi sonlandıran olaylar oluştuğunda uygulamaların bir programın denetimini ele geçirmesini sağlayan C dilindeki Microsoft uzantısıdır. Böyle olaylara özel durumlar, özel durumlarla uğraşan mekanizmaya ise yapılandırılmış özel durum işleme adı verilir.

Özel durumlar donanım veya yazılım tabanlı olabilir. Uygulamalar donanım veya yazılım özel durumlarından tamamen kurtarılamadığında bile, yapılandırılmış özel durum işleme hata bilgilerinin görüntülenmesini ve sorunun tanılanmasına yardımcı olmak için uygulamanın iç durumunun yakalanmasını sağlar. Bu, özellikle kolayca yeniden oluşturulamayan aralıklı sorunlar için yararlıdır.

## <a name="syntax"></a>Sözdizimi

*try-except-deyimi*: **__try**  *bileşik deyimi*

**__except (***ifade***)** bileşik*deyimi*      

Maddeden `__try` sonraki bileşik ifade korunan bölümdür. `__except` yan tümcesinden sonra gelen bileşik deyim, özel durum işleyicisidir. Işleyici, korunan bölümün yürütülmesi sırasında bir özel durum yükseltilirse, yapılacak bir dizi eylem belirtir. Yürütme aşağıdaki gibi devam eder:

1. Korunan bölüm yürütülür.

1. Korunan bölümün yürütülmesi sırasında hiçbir özel durum gerçekleşmezse, yürütme işlemine `__except` yan tümcesinden sonra deyimde devam edilir.

1. Korunan bölümün yürütülmesi sırasında veya herhangi bir rutinde bir özel durum `__except` oluşursa, korumalı bölüm çağrıları, ifade değerlendirilir ve döndürülen değer özel durum nasıl işleneceğini belirler. Üç değer vardır:

   `EXCEPTION_CONTINUE_SEARCH`Özel durum tanınmıyor. Önce **deneme dışı** ifadeler, sonra sonraki en yüksek önceliğe sahip işleyiciler için bir işleyici için yığını aramaya devam edin.

   `EXCEPTION_CONTINUE_EXECUTION`Özel durum tanınır, ancak görevden alınır. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.

   `EXCEPTION_EXECUTE_HANDLER`Özel durum tanınır. `__except` Bileşik deyimi çalıştırarak özel durum işleyicisine denetim aktarın, ardından özel durum oluştuğu noktada yürütmeye devam edin.

`__except` İfade C ifadesi olarak değerlendirildiğinden, tek bir değerle, koşullu ifade işleciyle veya virgül işleciyle sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.

> [!NOTE]
> Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalarıyla çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme mekanizması, her türlü özel durumları işleyebilir, çok daha esnektir.

> [!NOTE]
> C++ programları için yapılandırılmış özel durum işleme yerine C++ özel durum işleme kullanılmalıdır. Daha fazla bilgi için *C++ Dil Başvurusu'nda* [Özel Durum Kullanımı'na](../cpp/exception-handling-in-visual-cpp.md) bakın.

Bir uygulamadaki her yordamın kendi özel durum işleyicisi olabilir. İfade `__except` `__try` gövde kapsamında yürütülür. Bu, orada bildirilen tüm yerel değişkenlere erişimi olduğu anlamına gelir.

`__leave` Anahtar kelime **deneme-hariç** deyimi bloğu içinde geçerlidir. Bunun etkisi, deneme `__leave` **hariç** bloğun sonuna atlamaktır. Yürütme, özel durum işleyicisinin bitiminden sonra devam eder. Bir `goto` deyim aynı sonucu gerçekleştirmek için kullanılabilir, ancak bir `goto` deyim yığın gevşeme neden olur. Yığın `__leave` gevşeme içermediğinden deyim daha verimlidir.

Çalışma zamanı işlevini kullanarak deneme dışı bir ifadeden çıkmak anormal sonlandırma olarak kabul edilir. **try-except** `longjmp` Bir `__try` açıklamaya atlamak yasadışı, ama birinden atlamak yasal. Bir işlem **deneme dışı** deyimi yürütmenin ortasında öldürülürse, özel durum işleyicisi çağrılmaz.

## <a name="example"></a>Örnek

Aşağıda bir özel durum işleyicisi ve sonlandırma işleyicisi bir örnektir. Sonlandırma işleyicileri hakkında daha fazla bilgi için [try-finally Bildirimi'ne](../c-language/try-finally-statement-c.md) bakın.

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

Bu, sağdaki yorumun ekaldığı örnekten elde edilen çıktıdır:

```
hello
in try              /* fall into try                     */
in try              /* fall into nested try                */
in filter           /* execute filter; returns 1 so accept  */
in finally          /* unwind nested finally                */
in except           /* transfer control to selected handler */
world               /* flow out of handler                  */
```

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[try-except Deyimi](../cpp/try-except-statement.md)
