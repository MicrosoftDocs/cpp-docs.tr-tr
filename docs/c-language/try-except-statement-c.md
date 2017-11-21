---
title: "deneyin-dışındaki Statement (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- try-except keyword [C]
- structured exception handling, try-except
- try-catch keyword [C]
- __try keyword [C]
- __except keyword [C]
- __except keyword [C], in try-except
- try-catch keyword [C], try-except keyword [C]
ms.assetid: f76db9d1-fc78-417f-b71f-18e545fc01c3
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea7526648d5879a224c3bc1ffd6c76dfc986c0c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="try-except-statement-c"></a>try-except Deyimi (C)
**Microsoft özel**  
  
 **Deneyin-dışında** normalde yürütme sonlandırmak olaylar oluştuğunda bir programın denetim kazanmak uygulamalar sağlayan C dili için bir Microsoft uzantısı bir ifadedir. Böyle olaylara özel durumlar, özel durumlarla uğraşan mekanizmaya ise yapılandırılmış özel durum işleme adı verilir.  
  
 Özel durumlar ya da donanım veya yazılım tabanlı olabilir. Uygulamalar donanım veya yazılım özel durumlarından tamamen kurtarılamadığında bile, yapılandırılmış özel durum işleme hata bilgilerinin görüntülenmesini ve sorunun tanılanmasına yardımcı olmak için uygulamanın iç durumunun yakalanmasını sağlar. Bu, özellikle kolayca yeniden oluşturulamayan aralıklı sorunlar için yararlıdır.  
  
## <a name="syntax"></a>Sözdizimi  
 *try dışında deyimi*:  
 **__try***bileşik deyim*   
  
 **__except (***ifade***)***bileşik deyim*   
  
 Bileşik deyim sonra `__try` yan tümcesi olan korumalı bölüm. `__except` yan tümcesinden sonra gelen bileşik deyim, özel durum işleyicisidir. İşleyici korumalı bölüm yürütülmesi sırasında bir özel durum oluşursa gerçekleştirilecek eylemleri kümesini belirtir. Yürütme gibi çalışır:  
  
1.  Korunan bölüm yürütülür.  
  
2.  Korunan bölümün yürütülmesi sırasında hiçbir özel durum gerçekleşmezse, yürütme işlemine `__except` yan tümcesinden sonra deyimde devam edilir.  
  
3.  Korumalı Bölüm yürütülmesi sırasında bir özel durum oluşur veya korumalı bölüm içindeki herhangi bir yordamı çağıran `__except` ifadenin değerlendirileceği ve döndürülen değer, özel durumun nasıl işlendiğini belirler. Üç değer vardır:  
  
     `EXCEPTION_CONTINUE_SEARCH`Özel durum tanınmıyor. Bir işleyici yığını yukarı ilk içeren için aramaya devam **deneyin-dışında** deyimlerini sonra işleyicileri sonraki en yüksek önceliğe sahip.  
  
     `EXCEPTION_CONTINUE_EXECUTION`Özel durum tanınan ancak kapatılır. Yürütmeye, özel durumun gerçekleştiği noktadan devam edin.  
  
     `EXCEPTION_EXECUTE_HANDLER`Özel durum tanınır. Denetim yürüterek özel durum işleyici aktarım `__except` bileşik deyim sonra yürütme özel durumu oluştuğu noktadan devam edin.  
  
 Çünkü `__except` ifadenin C ifade olarak, tek bir değer, koşullu ifade işleci veya virgül işleci sınırlıdır. Daha kapsamlı bir işlem gerekliyse, ifade yukarıda listelenen üç değerden birini döndüren bir yordam çağırabilir.  
  
> [!NOTE]
>  Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalar üzerinde çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum mekanizması işleme çok daha esnek ve herhangi bir tür özel durumlar işleyebilir olmamasıdır.  
  
> [!NOTE]
>  C++ programları için C++ özel durum işleme yapılandırılmış özel durum işleme yerine kullanılmalıdır. Daha fazla bilgi için bkz: [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md) içinde *C++ dil başvurusu*.  
  
 Her bir uygulama yordamında, kendi özel durum işleyici olabilir. `__except` İfade yürütür kapsamında `__try` gövdesi. Bu var. bildirilen herhangi bir yerel değişkenleri erişimi olduğu anlamına gelir.  
  
 `__leave` Sözcüktür içinde geçerli bir **deneyin-dışında** deyimi bloğu. Etkisini `__leave` sonuna atlamak için **deneyin-dışında** bloğu. Yürütme, özel durum işleyici sonunda sürdürür. Ancak bir `goto` deyimi, aynı sonucu gerçekleştirmek için kullanılabilir bir `goto` deyimi neden yığını geriye doğru izleme. `__leave` Deyimi olduğundan daha verimli yığını geriye doğru izleme gerektirmez.  
  
 Çıkma bir **deneyin-dışında** deyimiyle `longjmp` çalışma zamanı işlevi anormal sonlandırma olarak kabul edilir. İçine atlamak için geçersiz bir `__try` deyimi, ancak bir dışı atlamak için yasal. Bir işlem yürütülürken ortasında sonlandırılırsa özel durum işleyici çağrılmaz bir **deneyin-dışında** deyimi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki özel durum işleyicisi ve sonlandırma işleyicisi örneğidir. Bkz: [try-finally deyimi](../c-language/try-finally-statement-c.md) sonlandırma işleyicileri hakkında daha fazla bilgi.  
  
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
  
 Bu örnekle sağ tarafta eklenen yorumlar çıkışı.  
  
```  
hello  
in try              /* fall into try                     */  
in try              /* fall into nested try                */  
in filter           /* execute filter; returns 1 so accept  */  
in finally          /* unwind nested finally                */  
in except           /* transfer control to selected handler */  
world               /* flow out of handler                  */  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deneyin-except deyimi](../cpp/try-except-statement.md)