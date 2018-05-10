---
title: Görev Parallelliği (eşzamanlılık çalışma zamanı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- structured task groups [Concurrency Runtime]
- structured tasks [Concurrency Runtime]
- task groups [Concurrency Runtime]
- task parallelism
- tasks [Concurrency Runtime]
ms.assetid: 42f05ac3-2098-494a-ba84-737fcdcad077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4f2a1f1a5bd0b4a8ca68f3aa47f6890a11efa11
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="task-parallelism-concurrency-runtime"></a>Görev Parallelliği (Eşzamanlılık Çalışma Zamanı)
Eşzamanlılık Çalışma zamanında bir *görev* belirli bir iş gerçekleştirir ve genellikle diğer görevlerle Paralel çalışan iş birimidir. Bir görev halinde düzenlenmiştir ek, daha ayrıntılı görevleri ayrılmış bir *görev grubu*.  
  
 Zaman uyumsuz kod yazmak ve zaman uyumsuz işlemi tamamlandıktan sonra gerçekleştirildiği için başka bir işlem istediğinizde görevleri kullanın. Örneğin, zaman uyumsuz olarak bir dosyadan okunan ve ardından başka bir görev için bir görev kullanabilirsiniz — bir *devamlılık görevi*, bu belgenin sonraki bölümlerinde açıklanan — kullanılabilir hale geldikten sonra verileri işlemek için. Buna karşılık, daha küçük parçalara paralel iş parçalayın için görevleri gruplarını kullanabilirsiniz. Örneğin, iki bölüme kalan çalışma ayıran bir özyinelemeli algoritması olduğunu varsayalım. Bu bölümler aynı anda çalıştırmak ve tamamlamak bölünmüş iş için bekleyin için Görev gruplarını kullanabilirsiniz.  
  
> [!TIP]

>  Paralel bir koleksiyonda her öğeye aynı yordamını uygulamak istediğinizde, bir paralel algoritması gibi kullanın [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for), bir görevi veya görev grubu yerine. Paralel algoritmalar hakkında daha fazla bilgi için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  

  
## <a name="key-points"></a>Önemli Noktalar  
  
-   Başvuruya göre bir lambda ifadesi değişkenleri geçirdiğinizde, görevi tamamlanana kadar bu değişken ömrü devam güvence altına almalıdır.  
  
-   Görevleri kullanın ( [concurrency::task](../../parallel/concrt/reference/task-class.md) sınıfı) zaman uyumsuz kod yazma zaman. Task sınıfı Windows iş parçacığı havuzu, Zamanlayıcı değil eşzamanlılık çalışma zamanı kullanır.  
  
-   Görev grupları kullanın ( [concurrency::task_group](reference/task-group-class.md) sınıfı veya [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması) isterseniz daha küçük parçalara paralel iş parçalayın ve bu küçük bekleyin tamamlamak için parça.  
  
-   Kullanım [CONCURRENCY::Task:: then](reference/task-class.md#then) devamlılıklar oluşturmak için yöntemi. A *devamlılık* başka bir görev tamamlandıktan sonra çalıştırılan zaman uyumsuz olarak bir görevdir. Zaman uyumsuz iş zinciri oluşturmak için devamlılıklar herhangi bir sayıda bağlanabilir.  
  
-   Öncül görev tamamlandığında, hatta zaman öncül görev iptal edildi veya bir özel durum oluşturur görev tabanlı bir devamlılık her zaman çalıştırılmak üzere zamanlandı.  
  
-   Kullanım [concurrency::when_all](reference/concurrency-namespace-functions.md#when_all) her üye bir dizi görevi tamamlandıktan sonra tamamlanan bir görev oluşturmak için. Kullanım [concurrency::when_any](reference/concurrency-namespace-functions.md#when_any) bir üyesi bir dizi görevi tamamlandıktan sonra tamamlanan bir görev oluşturmak için.  

  
-   Paralel Desen kitaplığı (PPL) iptal mekanizma, görevler ve görev grupları katılabilirsiniz. Daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md).  
  
-   Çalışma zamanı görevleri ve görev grupları tarafından oluşturulan özel durumları nasıl işler öğrenmek için bkz: [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="in-this-document"></a>Bu Belgede  
  
- [Lambda ifadeleri kullanma](#lambdas)  
  
- [Görev sınıfı](#task-class)  
  
- [Devamlılık görevlerini](#continuations)  
  
- [Değer tabanlı görev tabanlı devamlılıklar karşılaştırması](#value-versus-task)  
  
- [Görevler oluşturma](#composing-tasks)  
  
    - [When_all işlevi](#when-all)  
  
    - [When_any işlevi](#when-any)  
  
- [Gecikmeli görev yürütme](#delayed-tasks)  
  
- [Görev grupları](#task-groups)  
  
- [Structured_task_group task_group karşılaştırma](#comparing-groups)  
  
- [Örnek](#example)  
  
- [Güçlü programlama](#robust)  
  
##  <a name="lambdas"></a> Lambda ifadeleri kullanma  
 Bunların kısa sözdizimi nedeniyle lambda ifadeleri görevleri ve görev grupları tarafından gerçekleştirilen işi tanımlamak için ortak bir yol sağlar. Bazı kullanım ipuçları şunlardır:  
  
-   Görevler genellikle arka plan iş parçacığı üzerinde çalıştığından, lambda ifadeleri değişkenlerde yakalama zaman nesne ömrü farkında olması. Bir değişken değerle yakaladığınızda, bu değişken bir kopyasını lambda gövdesinde yapılır. Başvuruya göre yakaladığınızda, bir kopya bırakılmaz. Bu nedenle, başvuruya göre yakalama herhangi bir değişken ömrü kullandığı görev outlives emin olun.  
  
-   Lambda ifadesi bir göreve geçirdiğinizde Yakala başvuruya göre yığında ayrılan değişkenleri yok.  
  
-   Ne, değer başvuruya göre yakalayarak belirleyebilir lambda ifadeleri yakalama değişkenleri hakkında açık olabilir. Bu nedenle öneririz, kullanmayın `[=]` veya `[&]` lambda ifadeleri için Seçenekler.  
  
 Genel bir desen devamlılık zincirde bir görev bir değişkene atar ve başka bir görev bu değişken okur durumdur. Her devamlılık görevi değişkeni farklı bir kopyasını tutan çünkü değeriyle yakalama yapılamaz. Yığın ayırma değişkenleri değişkeni artık geçerli olabileceğinden başvuruya göre de yakalayamazsınız.  
  
 Bu sorunu çözmek için akıllı bir işaretçi gibi kullandığınız [std::shared_ptr](../../standard-library/shared-ptr-class.md), değişkeni kaydırma ve akıllı işaretçi değeri geçirin. Bu şekilde nesnesini atanabilir ve okuma ve onu kullanan görevleri outlive. Değişken bir işaretçi veya bir başvuru sayılan tanıtıcı olsa bile bu tekniği kullanın (`^`) Windows çalışma zamanı nesne. Temel bir örnek aşağıda verilmiştir:  
  
 [!code-cpp[concrt-lambda-task-lifetime#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_1.cpp)]  
  
 Lambda ifadeleri hakkında daha fazla bilgi için bkz: [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).  
  
##  <a name="task-class"></a> Görev sınıfı  
 Kullanabileceğiniz [concurrency::task](../../parallel/concrt/reference/task-class.md) görevleri bağımlı işlemler kümesine oluşturmak için sınıfı. Bu birleşim model kavramı tarafından desteklenen *devamlılıklar*. Ne zaman yürütülecek bir devamlılık etkinleştirir kod önceki, veya *antecedent*, görev tamamlar. Öncül görev sonucu, bir veya daha fazla devamlılık görevlerini girdisi olarak geçirilir. Öncül bir görev tamamlandığında üzerinde bekleyen herhangi bir devamlılık görevi çalıştırılmak üzere zamanlanmış. Her devamlılık görevi öncül görev sonucunu bir kopyasını alır. Buna karşılık, bu devamlılık görevlerini böylece görevleri zinciri oluşturma diğer devamlılıklar öncül görevlerde de olabilir. Devamlılıklar aralarında belirli bağımlılıkları olan görevler, rastgele uzunlukta zincirleri oluşturmanıza yardımcı olur. Ayrıca, çalışırken bir görevi iptal etme ya da bir görevleri önce başlatır veya İşbirlikçi bir şekilde katılabilir. Bu iptal modeli hakkında daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md).  
  
 `task` bir şablon sınıfıdır. Tür parametresi `T` görev tarafından üretilen sonuç türü. Bu tür olabilir `void` görev bir değer döndürmezse. `T` kullanamazsınız `const` değiştiricisi.  
  
 Bir görev oluşturduğunuzda, sağladığınız bir *iş işlevi* görev gövde gerçekleştirir. Bu çalışma işlevi bir lambda işlev, işlev işaretçisi veya işlev nesnesi biçiminde gelir. Bir görevi sonucu elde etmeden tamamlamak için beklemek için çağrı [concurrency::task::wait](reference/task-class.md#wait) yöntemi. `task::wait` Yöntemi döndürür bir [concurrency::task_status](reference/concurrency-namespace-enums.md#task_group_status) görev tamamlandı veya iptal edildiğini tanımlayan değer. Görev sonucu almak için arama [CONCURRENCY::Task](reference/task-class.md#get) yöntemi. Bu yöntemi çağırır `task::wait` bitiş ve bu nedenle blokları yürütme geçerli iş parçacığının görevi için sonuç kullanılabilir olana kadar beklenecek.  
  
 Aşağıdaki örnek, bir görev oluşturmak için sonucu bekleyin ve değerini görüntülemek gösterilmektedir. Daha kısa bir söz dizimi sağladıkları için bu belgedeki örneklerde lambda işlevlerini kullanın. Ancak, görevleri kullandığınızda da işlev işaretçileri ve işlev nesneleri kullanabilirsiniz.  
  
 [!code-cpp[concrt-basic-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_2.cpp)]  
  

 Kullandığınızda [concurrency::create_task](reference/concurrency-namespace-functions.md#create_task) kullanabileceğiniz işlevi, `auto` türünü bildirme yerine anahtar sözcük. Örneğin, oluşturur ve bu kimlik matris yazdırır bu kodu göz önünde bulundurun:  

  
 [!code-cpp[concrt-create-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_3.cpp)]  
  
 Kullanabileceğiniz `create_task` eşdeğer işlemi oluşturmak için işlevi.  
  
 [!code-cpp[concrt-create-task#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_4.cpp)]  
  
 Görevin yürütülmesi sırasında bir özel durum, çalışma zamanı bu özel durum sonraki çağrısında sıralar `task::get` veya `task::wait`, veya bir görev tabanlı devamlılık. Görev özel durum işleme mekanizması hakkında daha fazla bilgi için bkz: [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Kullanan bir örnek `task`, [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), iptal, bkz: [izlenecek yol: bağlanma kullanarak görevleri ve XML HTTP isteklerini](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md). ( `task_completion_event` Sınıfı bu belgenin sonraki bölümlerinde açıklanan.)  
  
> [!TIP]
>  UWP uygulamalarında görevlere özgü daha ayrıntılı bilgi için bkz: [c++ zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) ve [oluşturma zaman uyumsuz işlemleri c++ UWP uygulamalar için](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).  
  
##  <a name="continuations"></a> Devamlılık görevlerini  
 Zaman uyumsuz programlama, ikinci bir işlem çağırma ve veri iletmektir tamamlandığında, bir zaman uyumsuz işlemi çok yaygın bir sorundur. Geleneksel olarak, bu geri çağırma yöntemlerini kullanarak gerçekleştirilir. Eşzamanlılık Çalışma Zamanı'nda aynı işlevselliği tarafından sağlanan *devamlılık görevlerini*. (Yalnızca devamlılığı olarak da bilinir) bir devamlılık görevi olarak bilinen başka bir görev tarafından çağrılan bir zaman uyumsuz bir görevdir *antecedent*, antecedent tamamlandığında. Devamlılıklar kullanarak şunları yapabilirsiniz:  
  
-   Verileri antecedent devamlılık geçirir.  
  
-   Altında devamlılık çağrılan veya çağrılamaz kesin koşulları belirtin.  
  
-   Bir devamlılık başlatılmadan önce ya da işbirliği ile çalışırken iptal edin.  
  
-   Devamlılık nasıl zamanlanmalıdır hakkında ipuçları sağlar. (Yalnızca evrensel Windows Platformu (UWP) uygulamaları için geçerlidir. Daha fazla bilgi için bkz: [oluşturma zaman uyumsuz işlemleri c++ UWP uygulamalar için](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).)  
  
-   Aynı antecedent gelen birden çok devamlılıklar çağırır.  
  
-   Tüm bir veya birden çok antecedents hiçbirini tamamladığınızda, bir devamlılık çağırır.  
  
-   Devamlılıklar birbiri ardından herhangi bir uzunlukta zincir.  
  
-   Antecedent tarafından oluşturulan özel durumları işlemek için bir devamlılık kullanır.  
  
 Bu özellikler, ilk görevi tamamlandığında, bir veya daha fazla görev yürütmek etkinleştirin. Örneğin, isteğe bağlı olarak ilk görev diskten okuduktan sonra bir dosyayı sıkıştırır bir devamlılık oluşturabilirsiniz.  
  


 Aşağıdaki örnek kullanmak için önceki birini değiştirir [CONCURRENCY::Task:: then](reference/task-class.md#then) kullanılabilir olduğunda, öncül görev değerini yazdıran bir devamlılık zamanlamak için yöntem.  


  
 [!code-cpp[concrt-basic-continuation#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_5.cpp)]  
  
 Zincir ve herhangi bir uzunlukta görevlere iç içe. Bir görev ayrıca birden çok devamlılıklar olabilir. Aşağıdaki örnek, önceki görev değerini üç kez artırır bir temel devamlılık zinciri gösterilmektedir.  
  
 [!code-cpp[concrt-continuation-chain#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_6.cpp)]  
  
 Bir devamlılık de başka bir görev döndürebilir. Hiçbir iptal varsa, bu görevi sonraki devamlılık önce yürütülür. Bu teknik olarak bilinen *zaman uyumsuz açmak*. Zaman uyumsuz açmak ek iş arka planda gerçekleştirmek istiyorsanız, ancak geçerli iş parçacığının engellemek için geçerli görev istemediğiniz durumlarda faydalıdır. (Burada devamlılıklar kullanıcı Arabirimi iş parçacığı üzerinde çalıştırabilirsiniz UWP uygulamalarında ortak budur). Aşağıdaki örnekte, üç görevler gösterilmektedir. İlk görev önce devamlılık görevi çalıştırma başka bir görev döndürür.  
  
 [!code-cpp[concrt-async-unwrapping#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_7.cpp)]  
  
> [!IMPORTANT]
>  Bir görev devamlılığı türünde iç içe geçmiş bir görevi döndüğünde `N`, sonuçta elde edilen görev türüne sahip `N`değil `task<N>`ve iç içe geçmiş görev tamamlandığında tamamlar. Diğer bir deyişle, devamlılık açmak iç içe geçmiş görevi gerçekleştirir.  
  
##  <a name="value-versus-task"></a> Değer tabanlı görev tabanlı devamlılıklar karşılaştırması  
 Verilen bir `task` dönüş türü olan nesne `T`, türünde bir değer sağlayabilir `T` veya `task<T>` devamlılık görevlerinin için. Türü sürer devamı `T` olarak bilinen bir *değeri tabanlı devamlılık*. Öncül görev hatasız tamamlayıp iptal değeri tabanlı devamlılık çalıştırılmak üzere zamanlandı. Türü sürer devamı `task<T>` onun parametresi olarak bilinen bir *görev tabanlı devamlılık*. Öncül görev tamamlandığında, hatta zaman öncül görev iptal edildi veya bir özel durum oluşturur görev tabanlı bir devamlılık her zaman çalıştırılmak üzere zamanlandı. Ardından çağırabilirsiniz `task::get` öncül görev sonucu elde etmek için. Öncül görevi iptal edildiğinden, `task::get` oluşturur [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md). Öncül görev bir özel durum oluşturduysa `task::get` bu özel durumu yeniden oluşturur. Görev tabanlı bir devamlılık öncül görevini iptal edildiğinde İptal olarak işaretlenmemiş.  
  
##  <a name="composing-tasks"></a> Görevler oluşturma  
 Bu bölümde açıklanmıştır [concurrency::when_all](reference/concurrency-namespace-functions.md#when_all) ve [concurrency::when_any](reference/concurrency-namespace-functions.md#when_all) yardımcı olan İşlevler, ortak desenler uygulamak için birden çok görev oluşturun.  

  
###  <a name="when-all"></a> When_all işlevi  
 `when_all` İşlevi bir dizi görevi tamamlandıktan sonra tamamlanan bir görev oluşturur. Bu işlev bir std döndürür::[vektör](../../standard-library/vector-class.md) kümesindeki her görev sonucunu içeren nesne. Aşağıdaki temel örnek kullanır `when_all` üç diğer görevlerin temsil eden bir görev oluşturmak için.  
  
 [!code-cpp[concrt-join-tasks#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_8.cpp)]  
  
> [!NOTE]
>  Geçişi için görevler `when_all` Tekdüzen olması gerekir. Diğer bir deyişle, bunların tümü aynı türde döndürmesi gerekir.  
  
 Aynı zamanda `&&` bir dizi görevi tamamladıktan sonra aşağıdaki örnekte gösterildiği gibi tamamlanan bir görev oluşturmak için sözdizimi.  
  
 `auto t = t1 && t2; // same as when_all`  
  
 Devamlılık ile birlikte kullanmak için ortak olan `when_all` bir dizi görevi tamamlandıktan sonra bir eylemi gerçekleştirmek için. Aşağıdaki örnek üç görev toplamını yazdırmak için önceki bir değiştirir her oluşturduğunun bir `int` sonucu.  
  
 [!code-cpp[concrt-join-tasks#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_9.cpp)]  
  
 Bu örnekte, ayrıca belirtebilirsiniz `task<vector<int>>` görev tabanlı bir devamlılık üretmek için.  
  
 Bir dizi görevi herhangi bir görev iptal edildi veya bir özel durum oluşturur `when_all` hemen tamamlar ve diğer görevlerin sonlanmasını beklemez. Bir özel durum, çağırdığınızda çalışma zamanı özel durumu yeniden oluşturur `task::get` veya `task::wait` görevi nesne `when_all` döndürür. Birden fazla görev oluşturursa çalışma zamanı bunlardan birini seçer. Bu nedenle, tüm görevleri tamamladıktan sonra tüm özel durumları izlemek emin olun; bir görev işlenmeyen özel durum sonlandırmak uygulama neden olur.  
  
 Programınızı tüm özel durumları gözlemleyen emin olmak için kullanabileceğiniz bir yardımcı programı işlevi aşağıda verilmiştir. Sağlanan aralıktaki her görev için `observe_all_exceptions` işlenemezse için gerçekleşen özel durumları tetikler ve bu özel durum yuttuğu.  
  
 [!code-cpp[concrt-eh-when_all#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_10.cpp)]  
  
 C++ ve XAML kullanır ve bu dosyaları diske yazan bir UWP uygulaması göz önünde bulundurun. Aşağıdaki örnekte nasıl kullanılacağını gösterir `when_all` ve `observe_all_exceptions` program tüm özel durumları gözlemleyen emin olmak için.  
  
 [!code-cpp[concrt-eh-when_all#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_11.cpp)]  
  
##### <a name="to-run-this-example"></a>Bu örneği çalıştırmak için  
  
1.  MainPage.xaml içinde eklemek bir `Button` denetim.  
  
 [!code-xml[concrt-eh-when_all#3](../../parallel/concrt/codesnippet/xaml/task-parallelism-concurrency-runtime_12.xaml)]  
  
2.  MainPage.xaml.h içinde bu iletme bildirimleri ekleme `private` bölümünü `MainPage` sınıf bildiriminin.  
  
 [!code-cpp[concrt-eh-when_all#4](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_13.h)]  
  
3.  MainPage.xaml.cpp içinde uygulamak `Button_Click` olay işleyicisi.  
  
 [!code-cpp[concrt-eh-when_all#5](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_14.cpp)]  
  
4.  MainPage.xaml.cpp içinde uygulamak `WriteFilesAsync` örnekte gösterildiği gibi.  
  
> [!TIP]

> `when_all` üreten engelleyici olmayan bir işlev bir `task` sonuç olarak. Farklı [task::wait](reference/task-class.md#wait), ASTA (uygulama STA) iş parçacığı üzerinde bir UWP uygulamasında bu işlevi çağırmak güvenlidir.  

  
###  <a name="when-any"></a> When_any işlevi  
 `when_any` İşlevi bir dizi görevi ilk görevde tamamlandığında tamamlanan bir görev oluşturur. Bu işlev döndüren bir [std::pair](../../standard-library/pair-structure.md) Tamamlanan görevin sonucu ve bu görev kümedeki dizinini içeren nesne.  
  
 `when_any` İşlevi özellikle aşağıdaki senaryolarda kullanışlıdır:  
  
-   Yedekli işlemler. Birçok şekilde gerçekleştirilen bir algoritma veya işlem düşünün. Kullanabileceğiniz `when_any` işlevi ilk bittikten işlemi seçin ve kalan işlemleri iptal edin.  
  
-   Dönüşümlü işlemler. Birden çok işlemi başlatmak için tüm son kullanın ve gerekir, `when_any` işlevi her işlemi bitirdiğinde sonuçları işleyemedi. Bir işlem tamamlandıktan sonra bir veya daha fazla ek görev başlatabilirsiniz.  
  
-   Daraltılmış işlemler. Kullanabileceğiniz `when_any` eşzamanlı işlem sayısını sınırlayarak önceki senaryoda genişletmek için işlevi.  
  
-   Süresi dolan işlemler. Kullanabileceğiniz `when_any` işlevi bir veya daha fazla görev ve belirli bir süre sonra tamamlandıktan bir görev arasında seçin.  
  
 İle `when_all`, sahip bir devamlılık kullanmak için ortak olan `when_any` bir dizi görevi ilk bitirdikten sonra eylemi gerçekleştirmek için. Aşağıdaki temel örnek kullanır `when_any` ilk üç diğer görevlerin tamamlandığında tamamlanan bir görev oluşturmak için.  
  
 [!code-cpp[concrt-select-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_15.cpp)]  
  
 Bu örnekte, ayrıca belirtebilirsiniz `task<pair<int, size_t>>` görev tabanlı bir devamlılık üretmek için.  
  
> [!NOTE]
>  İle `when_all`, geçişi için görevler `when_any` tümü aynı türde döndürmesi gerekir.  
  
 Aynı zamanda `||` ilk görevde bir dizi görevi tamamlandıktan sonra aşağıdaki örnekte gösterildiği gibi tamamlanan bir görev oluşturmak için sözdizimi.  
  
 `auto t = t1 || t2; // same as when_any`  
  
> [!TIP]
>  İle `when_all`, `when_any` engellemeyen ve ASTA iş parçacığı üzerinde bir UWP uygulamasında çağrılması güvenlidir.  
  
##  <a name="delayed-tasks"></a> Gecikmeli görev yürütme  
 Bazen, bir koşul sağlanırsa kadar bir görevi yürütme gecikme ya da dış bir olaya yanıt olarak bir görevi başlatmak için gerekli değildir. Örneğin, zaman uyumsuz programlama içinde bir g/ç tamamlama olaya yanıt olarak bir görevi başlatmak gerekebilir.  
  
 Bunu yapmanın iki yolu, bir devamlılık kullanın veya bir görevi başlatmak ve görevin çalışma işlevi içinde bir olayı beklemesi üzeresiniz. Ancak, durumlar vardır, bu teknikler birini kullanmak mümkün değil. Örneğin, bir devamlılık oluşturmak için öncül görev olması gerekir. Ancak, öncül görev yoksa oluşturabileceğiniz bir *görev tamamlama olayı* ve daha sonra kullanılabilir hale geldiğinde öncül görev tamamlama olayı zincirine bağlı. Ayrıca, bir bekletme görevi de bir iş parçacığı engellediğinden, görev tamamlama olaylarının zaman uyumsuz bir işlem tamamlandığında iş gerçekleştirmek için kullanın ve böylece bir iş parçacığı boş.  
  
 [Concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) sınıfı, bu tür birleşim görevleri basitleştirmek yardımcı olur. Gibi `task` sınıfı, tür parametresi `T` görev tarafından üretilen sonuç türü. Bu tür olabilir `void` görev bir değer döndürmezse. `T` kullanamazsınız `const` değiştiricisi. Genellikle, bir `task_completion_event` nesnesi, bir iş parçacığı ya da bu değeri kullanılabilir olduğunda, sinyal görev için sağlanır. Aynı anda bir veya daha fazla görev olay dinleyicileri olarak ayarlanır. Olay ayarladığınızda, dinleyicisi görevleri tamamlamak ve bunların devamlılıklar çalışacak şekilde zamanlanır.  
  
 Kullanan bir örnek `task_completion_event` bir gecikmeden sonra tamamlanan bir görev uygulamak için bkz: [nasıl yapılır: bir görev bu tamamlandıktan sonra bir gecikme oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md).  
  
##  <a name="task-groups"></a> Görev grupları  
 A *görev grubu* görevleri koleksiyonu düzenler. Görev grupları görevleri iş çalarak bir sıra açın iletin. Zamanlayıcı görevleri bu kuyruktan kaldırır ve kullanılabilir bilgi işlem kaynaklarına yürütür. Görevler bir görev grubuna ekledikten sonra son ya da henüz başlatılmamış görevleri iptal etmek tüm görevler için bekleyebilirsiniz.  
  
 PPL'de kullanan [concurrency::task_group](reference/task-group-class.md) ve [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) görev grupları temsil eden sınıfları ve [concurrency::task_handle](../../parallel/concrt/reference/task-handle-class.md) sınıfı Bu gruplar halinde çalışan görevleri göstermek için. `task_handle` Sınıfı çalışma gerçekleştirir kod yalıtır. Gibi `task` sınıfı, iş işlevi lambda işlevi, işlev işaretçisi ya da işlev nesnesi biçiminde gelir. Genellikle çalışmak gerekmez `task_handle` nesnelerini doğrudan. Bunun yerine, bir görev grubuna iş işlevleri geçirdiğiniz ve görev grubu oluşturur ve yönetir `task_handle` nesneleri.  
  
 PPL'de görev grupları bu iki kategoride böler: *yapılandırılmamış görev grupları* ve *yapılandırılmış görev grupları*. PPL'de kullanan `task_group` yapılandırılmamış görev grupları temsil etmek için sınıf ve `structured_task_group` yapılandırılmış görev grupları temsil eden sınıf.  
  
> [!IMPORTANT]

>  PPL'de ayrıca tanımlar [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) kullanan algoritmasını `structured_task_group` paralel olarak bir dizi görevi yürütmek için sınıf. Çünkü `parallel_invoke` algoritmasına sahip daha kısa bir söz dizimi, bunun yerine kullanmanızı öneririz `structured_task_group` sınıf yapabilecekleriniz olduğunda. Konu [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md) açıklar `parallel_invoke` daha ayrıntılı.  
  
 Kullanım `parallel_invoke` zaman, aynı anda çalıştırmak istediğiniz bağımsız birkaç görev vardır ve devam etmeden önce tüm görevin bitmesini bekleyin. Bu yöntem, genellikle olarak adlandırılır *çatalı ve birleştirme* paralellik. Kullanım `task_group` zaman, aynı anda çalıştırmak istediğiniz birkaç bağımsız görevleri sahip, ancak daha sonra tamamlamak görevler için beklemek istiyor. Örneğin, görevler ekleyebilirsiniz bir `task_group` nesne ve görevleri başka bir işlevi veya başka bir iş parçacığından tamamlanması için bekleyin.  
  
 Görev grupları iptal kavramını destekler. İptal etme ve genel işlemi iptal etmek istediğiniz tüm etkin görevleri için sinyal sağlar. İptal henüz başlatılmasını başlamadı görevleri de önler. İptal etme hakkında daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md).  
  
 Çalışma zamanı görevden bir özel durum ve tamamlamak ilişkili görev grubu için bekleyin, bu özel durum işleme olanak tanıyan bir özel durum işleme modeli de sağlar. Bu özel durum işleme modeli hakkında daha fazla bilgi için bkz: [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
##  <a name="comparing-groups"></a> Structured_task_group task_group karşılaştırma  
 Kullanmanızı öneririz, ancak `task_group` veya `parallel_invoke` yerine `structured_task_group` sınıfı, kullanmak istediğiniz durumlarda `structured_task_group`, örneğin, ne zaman yazdığınız değişken bir dizi görevi gerçekleştirir veya gerektiren bir paralel algoritması iptal etme desteği. Bu bölümde arasındaki farklar açıklanmaktadır `task_group` ve `structured_task_group` sınıfları.  
  
 `task_group` İş parçacığı bir sınıftır. Bu nedenle, görevlere ekleyebilirsiniz bir `task_group` nesne birden çok iş parçacığından ve beklemesi veya iptal bir `task_group` birden çok iş parçacığı nesnesinden. Oluşturma ve yok etme bir `structured_task_group` nesnesi aynı sözcük kapsam içinde gerçekleşmesi gerekir. Buna ek olarak, tüm işlemler bir `structured_task_group` nesnesi aynı iş parçacığı üzerinde gerçekleşmesi gerekir. Bu kural için özel durum [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) ve [concurrency::structured_task_group::is_canceling](reference/structured-task-group-class.md#is_canceling) yöntemleri. Alt görevin üst görev grubu iptal edin veya herhangi bir zamanda iptali denetlemek için bu yöntemleri çağırabilirsiniz.  
  
 Ek görevleri çalıştırmak bir `task_group` , çağrısından sonra nesne [concurrency::task_group::wait](reference/task-group-class.md#wait) veya [concurrency::task_group::run_and_wait](reference/task-group-class.md#run_and_wait) yöntemi. Buna karşılık, ek görevleri çalıştırırsanız, bir `structured_task_group` , çağrısından sonra nesne [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait) veya [concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait) yöntemleri , davranış tanımsızdır sonra.  
  
 Çünkü `structured_task_group` sınıfı, iş parçacıkları arasında eşitleme değil, ek yükü daha az yürütme sahip `task_group` sınıfı. Bu nedenle, sorununuzu, gerektirmiyorsa birden çok iş parçacığından iş zamanlama ve kullanamazsınız `parallel_invoke` algoritmasını `structured_task_group` sınıfı daha iyi gerçekleştirme kod yazmanıza yardımcı olabilir.  
  
 Birini kullanırsanız `structured_task_group` iç nesne `structured_task_group` nesnesi, iç nesneyi bitmesi gerekir ve dış nesne tamamlanmadan önce yok. `task_group` Sınıfı dış Grup tamamlanmadan önce tamamlanması için iç içe geçmiş görev grupları gerektirmez.  
  
 Yapılandırılmamış görev grupları ve yapılandırılmış görev grupları görev tanıtıcıları ile farklı şekillerde çalışır. İş işlevleri doğrudan geçirebilirsiniz bir `task_group` nesne; `task_group` nesnesi oluşturur ve görev tanıtıcı yönettiğiniz. `structured_task_group` Sınıf gerektirir, yönetmek bir `task_handle` her görev için nesne. Her `task_handle` nesne devam etmelidir, ilişkili yaşam süresi geçerli `structured_task_group` nesnesi. Kullanım [concurrency::make_task](reference/concurrency-namespace-functions.md#make_task) işlevi oluşturmak için bir `task_handle` temel aşağıdaki örnekte gösterildiği gibi nesnesi:  
  
 [!code-cpp[concrt-make-task-structure#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_16.cpp)]  
  
 Görev tanıtıcıları değişken birkaç görev olduğu durumlarda yönetmek için bir yığın ayırma yordam gibi kullanın [_malloca](../../c-runtime-library/reference/malloca.md) veya std gibi bir kapsayıcı sınıfını::[vektör](../../standard-library/vector-class.md).  
  
 Her ikisi de `task_group` ve `structured_task_group` iptal destekler. İptal etme hakkında daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md).  
  
##  <a name="example"></a> Örnek  
 Aşağıdaki temel örnek görev gruplarıyla çalışma gösterilmektedir. Bu örnekte `parallel_invoke` iki gerçekleştirmek için algoritma görevler eşzamanlı olarak. Her görev için alt görevler ekler bir `task_group` nesnesi. Unutmayın `task_group` sınıfı görevler eşzamanlı olarak eklemek birden çok görev için izin verir.  
  
 [!code-cpp[concrt-using-task-groups#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_17.cpp)]  
  
 Bu örnek için örnek çıktı verilmiştir:  
  
```Output  
Message from task: Hello  
Message from task: 3.14  
Message from task: 42  
```  
  
 Çünkü `parallel_invoke` algoritması görevler eşzamanlı olarak çalışır ve çıktı iletilerin sırasını farklılık gösterir.  
  
 Nasıl kullanılacağını gösteren tam örnekleri için `parallel_invoke` algoritması bkz [nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) ve [nasıl yapılır: paralel işlemleri yürütmekiçinparallel_invokekullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md). Kullanan tam bir örnek için `task_group` sınıfı zaman uyumsuz vadeli uygulamak için bkz: [izlenecek yol: vadeli uygulama](../../parallel/concrt/walkthrough-implementing-futures.md).  
  
##  <a name="robust"></a> Güçlü programlama  
 Rolü iptali ve görevler, görev grupları ve paralel algoritmalar kullandığınızda özel durum işleme anladığınızdan emin olun. Örneğin, paralel iş ağacında iptal bir görev alt görevler çalışmasını engeller. Alt görevler birini uygulamanıza bir kaynak boşaltma gibi önemli bir işlem gerçekleştirdiğinde bu sorunlara neden olabilir. Ayrıca, alt görevin bir özel durum oluşturursa, başka bir özel durum nesnesi yıkıcı yayar ve uygulamanızda tanımsız davranışlara neden. Bu noktalarını gösteren örnek için bkz: [anlayın nasıl iptali ve özel durum işleme etkileyen nesne yok etme](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) en iyi uygulamaları paralel Desen kitaplığı belgedeki bölümünde. Özel durum işleme modeli ppl'de ve iptal etme hakkında daha fazla bilgi için bkz: [iptal](../../parallel/concrt/cancellation-in-the-ppl.md) ve [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Nasıl kullanılacağını gösterir `parallel_invoke` bitonic Sıralama algoritması performansını artırmak için algoritması.|  
|[Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Nasıl kullanılacağını gösterir `parallel_invoke` bir paylaşılan veri kaynağı üzerinde birden çok işlemler gerçekleştiren bir program performansını artırmak için algoritması.|  
|[Nasıl yapılır: Bir Gecikmeden Sonra Tamamlanan bir Görev Oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|Nasıl kullanılacağını gösterir `task`, `cancellation_token_source`, `cancellation_token`, ve `task_completion_event` bir gecikmeden sonra tamamlanan bir görev oluşturmak için sınıflar.|  
|[İzlenecek Yol: Vadeli İşlemleri Uygulama](../../parallel/concrt/walkthrough-implementing-futures.md)|Daha fazla yapan varolan işlevsellikte eşzamanlılık çalışma zamanı bir şey halinde birleştirmek gösterilmiştir.|  
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Eş zamanlı uygulamaları geliştirmek için kesinlik temelli bir programlama modeli sağlar PPL açıklar.|  
  
## <a name="reference"></a>Başvuru  
 [task Sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)  
  
 [task_completion_event Sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)  

 [when_all işlevi](reference/concurrency-namespace-functions.md#when_all)  
  
 [when_any işlevi](reference/concurrency-namespace-functions.md#when_any)  
  
 [task_group sınıfı](reference/task-group-class.md)  
  
 [parallel_invoke işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)  
  
 [structured_task_group Sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)
