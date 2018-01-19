---
title: "Yeniden Hoş Geldiniz C++ (Modern C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e45c48671a0df62103a58a89d0c351209c71ed2
ms.sourcegitcommit: ff9bf140b6874bc08718674c07312ecb5f996463
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="welcome-back-to-c-modern-c"></a>C++'a (Modern C++) Tekrar Hoş Geldiniz
C++ dünyanın en yaygın olarak kullanılan programlama dillerinde biridir. İyi yazılmış C++ programları hızlı ve verimlidir. Diğer diller çok çeşitli uygulamaları oluşturmak için kullandığı için dil daha esnektir — eğlenceli ve aygıt sürücüleri, katıştırılmış programları ve Windows istemci uygulamaları için yüksek performanslı bilimsel yazılım heyecan verici oyunlar. 20 yıldan fazla, C++, bunlar ve diğer birçok gibi sorunları çözmek için kullanılmış. Ne değil bilirsiniz C++ programcıları artan sayıda dün dowdy C stili programlama yukarı Katlanmış ve modern C++ yerine donned olmasıdır.  
  
 C++ için özgün gereksinimlerden biri C dil ile geriye dönük uyumluluk oluştu. O zamandan bu yana C++ birkaç yineleme gelişmiştir — sınıflar, sonra özgün C++ dil belirtimi ve ardından sonraki birçok iyileştirme ile C. Bu miras nedeniyle C++ genellikle çok kip programlama dili olarak adlandırılır. C++'da, ham işaretçileri, dizileri, null olarak sonlandırılan bir karakter dizeleri, özel veri yapılarını ve harika performans sağlayabilir, ancak hatalar ve karmaşıklığını da oluşturabilir diğer özellikleri içerir tamamen yordam C tarzı programlama yapabilirsiniz.  C tarzı programlama fraught bu gibi perils sahip olduğundan, kuruluş hedeflerinden c++ programları hem tür kullanımı uyumlu hem de yazma, genişletme ve sürdürmek daha kolay yapmak için oluştu. Erken bir açık, C++ programlama modellerine nesne odaklı programlama gibi embraced. Yıllar içinde veri yapılarını algoritmaları ve standart kitaplıkları yüksek oranda test birlikte dili özellikleri eklenmiştir. Modern C++ stili olası yapmış olduğunuz Bu eklemeleri olur.  
  
 Modern C++ vurgular:  
  
-   Yığın tabanlı kapsamı yığın veya statik genel kapsam yerine.  
  
-   Açık tür adları yerine otomatik tür çıkarımı.  
  
-   Akıllı işaretçiler ham işaretçileri yerine.  
  
-   `std::string`ve `std::wstring` türleri (bkz [ \<dize >](../standard-library/string.md)) ham yerine `char[]` dizileri.  
  
-   [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-header-files.md) kapsayıcıları ister `vector`, `list`, ve `map` ham dizileri veya özel kapsayıcılar yerine. Bkz: [ \<vektör >](../standard-library/vector.md), [ \<listesi >](../standard-library/list.md), ve [ \<harita >](../standard-library/map.md).  
  
-   C++ Standart Kitaplığı [algoritmaları](../standard-library/algorithm.md) yerine el ile olanları kodlanmış.  
  
-   Özel durumlar, rapor ve tanıtıcı hata koşulları için.  
  
-   Kilidi serbest C++ Standart Kitaplığı kullanılarak arası iş parçacığı iletişim `std::atomic<>` (bkz [ \<atomik >](../standard-library/atomic.md)) diğer arası iş parçacığı iletişim mekanizmasını yerine.  
  
-   Satır içi [lambda işlevleri](../cpp/lambda-expressions-in-cpp.md) ayrı olarak uygulanan küçük işlevler yerine.  
  
-   Aralık tabanlı diziler, C++ Standart Kitaplığı kapsayıcıları ve Windows çalışma zamanı koleksiyonları biçiminde çalışma daha sağlam döngüler yazmak döngüler için `for ( for-range-declaration : expression )`. Bu, çekirdek dil desteği parçasıdır. Daha fazla bilgi için bkz: [aralık tabanlı için deyimi (C++)](../cpp/range-based-for-statement-cpp.md).  
  
 C++ dili de gelişmiştir. Aşağıdaki kod parçacıkları karşılaştırın. Bu bir şeyler c++'ta olması için nasıl kullanılacağını gösterir:  
  
```cpp  

#include <vector>

void f()
{
    // Assume circle and shape are user-defined types  
    circle* p = new circle( 42 );   
    vector<shape*> v = load_shapes();  

    for( vector<circle*>::iterator i = v.begin(); i != v.end(); ++i ) {  
        if( *i && **i == *p )  
            cout << **i << " is a match\n";  
    }  

    // CAUTION: If v's pointers own the objects, then you
    // must delete them all before v goes out of scope.
    // If v's pointers do not own the objects, and you delete
    // them here, any code that tries to dereference copies
    // of the pointers will cause null pointer exceptions.
    for( vector<circle*>::iterator i = v.begin();  
            i != v.end(); ++i ) {  
        delete *i; // not exception safe  
    }  

    // Don't forget to delete this, too.  
    delete p;  
} // end f()
```

 Aynı şey modern C++'da nasıl yapıldığını aşağıda verilmiştir:  
  
```cpp

#include <memory>  
#include <vector>  

void f()
{
    // ...  
    auto p = make_shared<circle>( 42 );  
    vector<shared_ptr<shape>> v = load_shapes();  

    for( auto& s : v ) 
    {  
        if( s && *s == *p )
        {
            cout << *s << " is a match\n";
        }
    }
}

```

 Modern C++'da yeni/silme veya açık özel durum akıllı işaretçileri bunun yerine kullandığından işleme kullanmanız gerekmez. Kullandığınızda `auto` kesintisi yazın ve [lambda işlevi](../cpp/lambda-expressions-in-cpp.md), daha hızlı, kod yazabilirsiniz onu artırmak ve daha iyi anlamak. Ve aralık tabanlı `for` döngü temizleyici kullanmayı daha kolay ve hata potansiyeli daha az istenmeyen C-style'den `for` döngü. Uygulamanızı yazmak için Demirbaş kod en küçük satırları ile birlikte kullanabilirsiniz. Ve bu kodu özel durum güvenli ve bellek güvenli hale getirmek ve uğraşmanız hiçbir ayırma/kaldırma veya hata kodları sahip.  
  
 Çok biçimlilik iki tür Modern C++ içerir: şablonlarıyla derleme zamanında ve devralma ve sanallaştırma aracılığıyla çalışma zamanında. Çok biçimlilik harika etkili olması için iki tür karıştırabilirsiniz. C++ Standart kitaplığı şablonu `shared_ptr` görünüşe göre zahmetsiz türü silinme gerçekleştirmek için iç sanal yöntemlerini kullanır. Ancak bir şablon daha iyi bir seçimdir sanallaştırma çok biçimlilik için aşırı kullanma. Şablonları çok güçlü olabilir.  
  
 Başvuru türleri çoğu türleri ve çok az sayıda değer türleri olan özellikle bir yönetilen dilden başka bir dil için C++ geldiği, C++ sınıfları varsayılan değer türleri olduğunu bildirir. Ancak, nesne odaklı programlama destekleyen çok biçimli davranışını etkinleştirmek için başvuru türleri belirtebilirsiniz. Yararlı bir perspektif: değer türleri olan temel sınıflar ve çok biçimlilik desteklemek için sanal işlevler hakkında daha fazla bellek ve düzen denetimi, başvuru türleri hakkında daha fazla. Varsayılan olarak, değer türleri copyable — sahip oldukları her bir kopya oluşturucu ve kopya atama işleci. Bir başvuru türü belirttiğinizde, sınıfı copyable olmayan kılar — kopya oluşturucu ve kopya atama işleci devre dışı — ve çok biçimlilik destekleyen bir sanal yıkıcı kullanın. Değer türleri ayrıca kopyalanırlar, bağlandığınızda, ayrı ayrı değiştirebilirsiniz iki bağımsız değerleri verin içeriği değildir. Ancak başvuru türleri hakkında kimlik — ne tür nesne olan — ve bu nedenle çok biçimli türleri olarak da adlandırılır.  
  
 Güç yeniden iyisidir çünkü C++ bir Rönesans yaşıyor. Java ve C# gibi diller Programcı üretkenlik önemlidir, ancak güç ve performansı en önemli olduğunda bunlar sınırlamalarını göstermek iyidir. Yüksek verimlilik ve özellikle, donanım, sınırlı cihazlara gücüyle için hiçbir şey modern C++ vuruş.  
  
 Yalnızca dili modern, geliştirme, çok araçlardır. [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]Geliştirme döngüsü tüm parçalarını sağlam ve verimli hale getirir. Uygulama Yaşam Döngüsü Yönetimi (ALM) araçları, IntelliSense gibi IDE geliştirmeleri, aracı kolay mekanizmaları XAML ve hata ayıklama, oluşturma gibi içerir ve diğer birçok araçlar.  
  
 Bu bölümü belgelerin makalelerinde üst düzey kılavuzları ve en önemli özellikleri için en iyi uygulamaları ve modern C++ programları yazmak için teknikleri sağlar.  
  
-   [C++ tür sistemi](../cpp/cpp-type-system-modern-cpp.md)  
  
-   [Tek Düzen Başlatma ve Oluşturucuları Temsilci Olarak Görevlendirme](../cpp/uniform-initialization-and-delegating-constructors.md)  
  
-   [Nesne yaşam süresi ve kaynak yönetimi](../cpp/object-lifetime-and-resource-management-modern-cpp.md)  
  
-   [Nesnelerin Kaynakları (RAII)](../cpp/objects-own-resources-raii.md)  
  
-   [Akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md)  
  
-   [Derleme zamanı kapsüllemesi için Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)  
  
-   [Kapsayıcılar](../cpp/containers-modern-cpp.md)  
  
-   [Algoritmalar](../cpp/algorithms-modern-cpp.md)  
  
-   [Dize ve g/ç biçimlendirme (Modern C++)](../cpp/string-and-i-o-formatting-modern-cpp.md)  
  
-   [Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)  
  
-   [ABI sınırlarında taşınabilirlik](../cpp/portability-at-abi-boundaries-modern-cpp.md)  
  
 Daha fazla bilgi için StackOverflow makalesine bakın [hangi C++ deyimleri C ++ 11'de kullanım dışı bırakılmıştır](http://go.microsoft.com/fwlink/p/?linkid=402836)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)  
 [Visual C++ dili uyumluluğu](../visual-cpp-language-conformance.md)  
