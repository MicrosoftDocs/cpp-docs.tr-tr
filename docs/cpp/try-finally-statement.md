---
title: try-finally deyimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
dev_langs:
- C++
helpviewer_keywords:
- __try keyword [C++]
- __finally keyword [C++]
- __leave keyword [C++]
- try-catch keyword [C++], try-finally keyword
- try-finally keyword [C++]
- __finally keyword [C++], try-finally statement syntax
- __leave keyword [C++], try-finally statement
- structured exception handling [C++], try-finally
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a6457e92b7f4b57c7c181705e369e8582fb54f9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="try-finally-statement"></a>try-finally Deyimi
**Microsoft özel**  
  
 Aşağıdaki söz dizimi açıklanmıştır `try-finally` deyimi:  
  
```  
__try {  
   // guarded code  
}  
__finally {  
   // termination code  
}  
```  
  
## <a name="grammar"></a>Dilbilgisi  
 *try-finally-ifadesi*:  
 `__try` *Bileşik deyim*  
  
 `__finally` *Bileşik deyim*  
  
 `try-finally` Kod bloğunu yürütülmesi kesintiye uğradığında oluşan temizleme kodu yürütme güvence altına almak hedef uygulamaları sağlayan bir Microsoft uzantısı C ve C++ dilleri için bir ifadedir. Bellek ayırmayı kaldırma, dosyaları kapatma ve dosya işleyicilerini serbest gibi görevler temizleme oluşur. `try-finally` Burada bir denetimi yapılır neden olabilecek bir hata için erken çeşitli yerlerde sahip yordamları yordamından dönmek için deyimi özellikle yararlı.  
  
 İlgili bilgiler ve bir kod örneği için bkz: [deneyin-except deyimi](../cpp/try-except-statement.md). Yapılandırılmış özel durum Genel olarak işleme hakkında daha fazla bilgi için bkz: [yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md). Yönetilen uygulamalarda özel durum işleme ile ilgili daha fazla bilgi için bkz: [/CLR altında özel durum işleme](../windows/exception-handling-cpp-component-extensions.md).  
  
> [!NOTE]
>  Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. C++ programları için C++ özel durum işleme mekanizmasını kullanmanız önerilir ([throw deneyin ve catch](../cpp/try-throw-and-catch-statements-cpp.md) deyimleri).  
  
 Bileşik deyim sonra `__try` yan tümcesi olan korumalı bölüm. Bileşik deyim sonra `__finally` yan tümcesi olan sonlandırma işleyicisi. İşleyici korumalı bölüm çıkılır, korumalı bölüm bir özel durum (anormal sonlandırma) veya (normal sonlandırma) aracılığıyla standart sonbaharda çıkıldı bağımsız olarak yükleyen yürütün eylemleri kümesini belirtir.  
  
 Denetim ulaştığında bir `__try` ifadesinin basit sıralı yürütme (sonbaharda aracılığıyla). Denetim girdiğinde `__try`, ilişkili işleyicisi etkin hale gelir. Denetim akışı try bloğunun sonuna ulaşırsa, yürütme gibi çalışır:  
  
1.  Sonlandırma işleyicisi çağrılır.  
  
2.  Sonlandırma işleyicisi tamamlandığında sonra yürütülmeye `__finally` deyimi. Bağımsız olarak nasıl bölüm uçları korumalı (örneğin, aracılığıyla bir `goto` korunmuş gövde dışında veya bir `return` deyimi), sonlandırma işleyicisi yürütülen `before` denetim akışını dışında korunmuş bölümü taşır.  
  
     A **__finally** deyimi için uygun özel durum işleyicisi arama engellemez.  
  
 Bir özel durum oluşması halinde `__try` bloğu, işletim sistemi için özel durum işleyici bulmalıdır veya program başarısız olur. İşleyici, tüm bulunursa `__finally` blokları yürütülme ve yürütme işleyicisinde sürdürür.  
  
 Örneğin, bir dizi işlev çağrısı aşağıdaki resimde gösterildiği gibi D, çalışması için bağlantılar işlevi A varsayalım. Her işlevi bir sonlandırma işleyicisi sahiptir. Bir özel durum işlevi D oluşturulur ve A işlenmiş, Sistem yığını unwinds gibi sonlandırma işleyicileri bu sırada çağrılır: D, C b  
  
 ![Sonlandırma sırasını&#45;işleyici yürütme](../cpp/media/vc38cx1.gif "vc38CX1")  
Sonlandırma işleyicisi yürütme sırasını  
  
> [!NOTE]
>  Try-finally davranışını kullanımını destekleyen bazı diğer dillerden farklı **son**, C# gibi.  Tek bir `__try` ya da, her ikisi birden biri olabilir `__finally` ve `__except`.  Her ikisi de birlikte kullanılmak üzere olduğunda, bir dış deneyin-deyimi iç try-finally deyimi almalısınız dışında.  Her bloğu yürüttüğünde belirten kuralları da farklıdır.  
  
## <a name="the-leave-keyword"></a>__leave Anahtar Sözcüğü  
 `__leave` anahtar sözcüğü, yalnızca bir `try-finally` deyiminin korunan bölümünde geçerlidir ve etkisi korunan bölümün sonuna atlamaktır. Sonlandırma işleyicisi işlemindeki ilk deyim adresindeki yürütme devam eder.  
  
 A `goto` deyimi de dışında korumalı bölüm atlamak ancak yığını geriye doğru izleme çağırdığından performansı düşürür. `__leave` Deyimi olduğundan daha verimli yığını geriye doğru izleme çıkarmaz.  
  
## <a name="abnormal-termination"></a>Olağan dışı sonlandırma  
 Çıkma bir `try-finally` deyimiyle [longjmp](../c-runtime-library/reference/longjmp.md) çalışma zamanı işlevi anormal sonlandırma olarak kabul edilir. İçine atlamak için geçersiz bir `__try` deyimi, ancak bir dışı atlamak için yasal. Tüm `__finally` ayrılma noktası arasında etkin deyimleri (normal sonlandırılması `__try` blok) ve hedef ( `__except` özel durumu işler blok) çalıştırmanız gerekir. Bu, yerel bir geriye doğru izleme adı verilir.  
  
 Varsa bir **deneyin** blok blok dışında bir atlama dahil olmak üzere herhangi bir nedenle sonlandırıldı zamanından önce sistem ilişkili yürütür **son** yığını geriye doğru izleme bir blok işleminin bir parçası olarak. Böyle durumlarda, [AbnormalTermination](http://msdn.microsoft.com/library/windows/desktop/ms679265) işlevi içinden çağrıldıklarında TRUE döndürür **son** engelle; Aksi takdirde FALSE değerini döndürür.  
  
 Bir işlem yürütülürken ortasında sonlandırılırsa sonlandırma işleyicisi çağrılmaz bir `try-finally` deyimi.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)   
 [Yapılandırılmış özel durum işleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Sonlandırma işleyicisi sözdizimi](http://msdn.microsoft.com/library/windows/desktop/ms681393)