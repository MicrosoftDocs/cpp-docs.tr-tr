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
ms.openlocfilehash: ea792bde6e50f0e4149f802a5c852192def0fefa
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948047"
---
# <a name="try-finally-statement"></a>try-finally Deyimi
**Microsoft'a özgü**  
  
 Aşağıdaki söz dizimini açıklar `try-finally` deyimi:  
  
```cpp 
__try {  
   // guarded code  
}  
__finally {  
   // termination code  
}  
```  
  
## <a name="grammar"></a>Dilbilgisi  
 *try-finally deyimi*:  
 **__try** *bileşik deyim*  
  
 **__finally** *bileşik deyim*  
  
 `try-finally` Hedef uygulamaların kod bloğunun yürütülmesi kesintiye uğradığında temizleme kodu yürütme garanti sağlayan bir Microsoft uzantısı C ve C++ dilleri için bir ifadedir. Temizleme gibi görevleri belleğini, dosyaları kapatma ve dosya tanıtıcıları bırakarak oluşur. `try-finally` Sahip olduğu bir onay yapılır neden olabilecek bir hata için erken çeşitli yerlerde yordamlarını yordamından döndürmek için deyimi özellikle yararlıdır.  
  
 İlgili bilgiler ve bir kod örneği için bkz: [deneyin-except deyimi](../cpp/try-except-statement.md). Yapılandırılmış özel durum işleme genel hakkında daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md). Yönetilen uygulamaların özel durumları işleme hakkında daha fazla bilgi için bkz: [/CLR altında özel durum işleme](../windows/exception-handling-cpp-component-extensions.md).  
  
> [!NOTE]
>  Yapılandırılmış özel durum işlemi, hem C hem de C++ kaynak dosyaları için Win32 ile çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme her türden özel durumu işleyebildiği için daha esnektir. C++ programları için C++ özel durum işleme mekanizmasını kullanmanız önerilir ([try, catch ve throw](../cpp/try-throw-and-catch-statements-cpp.md) deyimleri).  
  
 Sonra gelen bileşik deyim **__try** yan tümcesi ise korunan bölümün. Sonra gelen bileşik deyim **__finally** yan tümcesi ise sonlandırma işleyicisi. İşleyici, bir dizi korunan bölümün bir özel durum (olağan dışı sonlandırma) veya standart fall (normal sonlandırması) aracılığıyla çıkıldı bağımsız olarak korunan bölümün çıkılıncaya olduğunda yürütülen bir eylemi belirtir.  
  
 Denetim ulaştığında bir **__try** deyimi tarafından basit sıralı yürütme (fall aracılığıyla). Denetim girdiğinde **__try**, kendi ilişkili işleyicisi etkin hale gelir. Denetim akışı try bloğunun sonuna ulaşırsa, yürütme aşağıdaki gibi çalışır:  
  
1.  Sonlandırma işleyicisi çağrılır.  
  
2.  Sonlandırma işleyicisi tamamlandığında sonra yürütülmesine devam **__finally** deyimi. Bağımsız olarak nasıl korunan bölüm sona erer (örneğin, aracılığıyla bir **Git** korumalı gövdenin dışında veya bir **dönüş** deyimi), sonlandırma işleyicisi yürütülür *önce* denetim akışı korumalı bölümün dışına gider.  
  
     A **__finally** deyimi uygun bir özel durum işleyicisi için arama engellemez.  
  
 Bir özel durum oluşursa **__try** blok, işletim sistemi için özel bir işleyici bulmalıdır veya program başarısız olur. İşleyici, tüm bulunursa **__finally** blokları yürütülür ve yürütme işleyicisinde sürdürür.  
  
 Örneğin, aşağıdaki resimde gösterildiği gibi bir dizi işlev çağrısının D, işlev için bağlantılar işlevi bir varsayalım. Her işlev bir sonlandırma işleyicisi sahiptir. Bir özel durum oluşturulduğunda D işlevinde ve A işlendiğinde, sistem yığın geriye doğru izler gibi sonlandırma işleyicileri bu sırayla çağrılır: D, C, B.  
  
 ![Sonlandırma sırası&#45;işleyici yürütme](../cpp/media/vc38cx1.gif "vc38CX1")  
Sonlandırma işleyicisi yürütme sırası  
  
> [!NOTE]
>  Try-finally davranışını kullanımını destekleyen bazı diğer dillerden farklı **son**, C# gibi.  Tek bir **__try** ya da, her ikisi birden biri olabilir **__finally** ve **__except**.  Her ikisi de birlikte kullanılmak üzere olduğunda, bir dış deneyin-dışında deyimi iç try-finally deyimi almalısınız.  Her blok yürütüldüğünde belirten kuralları da farklıdır.  
  
## <a name="the-leave-keyword"></a>__leave Anahtar Sözcüğü  
 **__Leave** anahtar sözcüğü yalnızca korunan bölümünde geçerlidir bir `try-finally` deyimi ve etkisi korunan bölümün sonuna atlama etmektir. Yürütme, sonlandırma işleyicisi içindeki ilk deyimde devam eder.  
  
 A **goto** deyimi korumalı bölümün dışına da atlayabilir ve yığın geriye doğru izleme çağırdığından performansı düşürür. **__Leave** deyimi olduğundan daha verimli yığın geriye doğru izleme çıkarmaz.  
  
## <a name="abnormal-termination"></a>Olağan dışı sonlandırma  
 Çıkmadan bir `try-finally` using deyimi [longjmp](../c-runtime-library/reference/longjmp.md) çalışma zamanı işlevi olağan dışı sonlandırma olarak kabul edilir. Bloğuna atlamak için geçersiz bir **__try** deyimi, ancak yasal birinden dışarı atlanabilir. Tüm **__finally** kalkış noktası arasında etkin olan deyimleri (normal sonlandırılması **__try** bloğu) ve hedef ( **__except** , engelle özel durum işleme) çalıştırmanız gerekir. Bu, yerel geriye doğru izleme adı verilir.  
  
 Varsa bir **deneyin** blok blok dışında bir atlama dahil olmak üzere herhangi bir nedenle erken sonlandırılır, sistem ilişkili yürütür **son** yığın geriye doğru izleme, blok işleminin bir parçası olarak. Bu gibi durumlarda [AbnormalTermination](http://msdn.microsoft.com/library/windows/desktop/ms679265) işlevinin döndürdükleriyle **true** içinden çağrılırsa **son** engelle; Aksi halde **false**.  
  
 Sonlandırma işleyicisi yürütülürken sonlandırılırsa bir işlem sonlandırılırsa çağrılmaz bir `try-finally` deyimi.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)   
 [Yapılandırılmış özel durum işleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Sonlandırma işleyicisi söz dizimi](http://msdn.microsoft.com/library/windows/desktop/ms681393)