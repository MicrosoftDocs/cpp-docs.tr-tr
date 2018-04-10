---
title: Nesne yaşam süresi ve kaynak yönetimi (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e2b48630fab9d27bf5db442617a5184bd26de5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="object-lifetime-and-resource-management-modern-c"></a>Nesne Yaşam Süresi ve Kaynak Yönetimi (Modern C++)
Yönetilen dilleri, C++ programı çalışırken, otomatik olarak no-uzun-kullanılan bellek kaynakları serbest bırakır, atık toplama (GC) sahip değil. C++'da, kaynak yönetimi için nesne ömrü doğrudan ilişkilidir. Bu belgede C++ nesne yaşam süresi ve yönetmek nasıl etkileyen faktörler açıklanmaktadır.  
  
 Bellek içi kaynaklar öncelikle işlemiyor çünkü C++ GC sahip değil. Yalnızca C++ de gibi belirleyici Yıkıcılar, bellek ve bellek içi kaynaklarını eşit olarak işleyebilir. GC bellek ve CPU tüketimi ve yere göre daha yüksek yükü gibi diğer sorunları da sahiptir. Ancak universality akıllı iyileştirmeler azaltılamaz temel bir sorundur.  
  
## <a name="concepts"></a>Kavramlar  
 Nesne ömrü Yönetimi'nde önemli bir şey kapsülleme. — aktaranın nesneyi kullanarak hangi nesne kaynaklarına sahip olduğu, veya bunları kurtulmak nasıl veya bile olup, herhangi bir kaynağa hiç sahip bilmek sahip değil. Nesne yok etmek yalnızca sahiptir. C++ çekirdek dil nesneler doğru zamanlarda diğer bir deyişle, yok emin olmak için tasarlanmıştır blokları, ters sırada yapımı çıkıldı gibi. Bir nesne kaldırıldığı zaman kendi tabanları ve üyeleri belirli bir sırada yok olur.  Yığın ayırma ya da yeni yerleştirme gibi özel şeyler sürece dil nesneleri, otomatik olarak bozar.  Örneğin, [akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md) gibi `unique_ptr` ve `shared_ptr`, C++ Standart Kitaplığı kapsayıcıları gibi ve `vector`, kapsülleyen `new` / `delete` ve `new[]` / `delete[]` nesneler Yıkıcılar sahip. İşte bu nedenle akıllı işaretçiler ve C++ Standart Kitaplığı kapsayıcıları kullanılacak şekilde önemlidir.  
  
 Başka bir önemli kavram ömrü Yönetimi'nde: Yıkıcılar. Yıkıcılar kaynak sürüm kapsüller.  (Yaygın olarak kullanılan anımsatıcı RRID, kaynak sürüm olan yok etme olur.)  Bir kaynak "", sistemden ve daha sonra geri vermek olan şeydir.  Bellek, en yaygın kaynak olmakla birlikte de vardır dosyaları, yuva, doku ve diğer bellek içi kaynaklar. "Kaynak sahibi olan" ihtiyacınız fakat ile tamamladığınızda serbest bırakmak de olduğunda kullanabileceğiniz anlamına gelir.  Bir nesne kaldırıldığı zaman kendi yıkıcı onu ait kaynakları serbest bırakır.  
  
 DAG (yönlendirilmiş Çevrimsiz grafik) son kavramdır.  Bir programı sahipliği yapısını DAG oluşturur. Hiçbir nesne kendisini sahip olabileceği — olmayan yalnızca imkansız ancak aynı zamanda kendiliğinden anlamsız. Ancak, iki nesne üçüncü bir nesnenin sahipliğini paylaşabilirsiniz.  Bağlantılar çeşitli türlerde DAG şöyle olabilir: A B üyesi olduğu (B sahibi A), C depoları bir `vector<D>` (C sahibi her D öğesi) E depoları bir `shared_ptr<F>` (E paylaşır F, sahipliğini büyük olasılıkla diğer nesnelerle), vb.  Hiçbir döngüleri vardır ve DAG her bir bağlantının bir nesne tarafından temsil edilen sürece yıkıcı (yerine, ham işaretçi, tanıtıcı veya başka bir mekanizma) olan sonra dil bunları engellediğinden kaynak sızıntıları olanaksız. Hemen artık, çalışan bir atık toplayıcı gerekli sonra kaynakları serbest bırakılır. İzleme ömrü yükünü serbest yığını kapsam, tabanları, üyeleri ve ilgili örnekler için ucuz için ise `shared_ptr`.  
  
### <a name="heap-based-lifetime"></a>Yığın tabanlı yaşam süresi  
 Yığın nesne ömrü için kullanmak [akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md). Kullanım `shared_ptr` ve `make_shared` varsayılan işaretçi ve ayırıcı olarak. Kullanım `weak_ptr` döngüsü sonu, önbelleğe alma yapabilir ve etkilemeden veya yaşam hakkında hiçbir şey varsayılarak olmadan nesneleri inceleyin.  
  
```cpp  
void func() {  
  
auto p = make_shared<widget>(); // no leak, and exception safe  
...  
p->draw();   
  
} // no delete required, out-of-scope triggers smart pointer destructor  
  
```  
  
 Kullanım `unique_ptr` benzersiz sahipliği için örneğin *derleme pimpl* deyim. (Bkz [derleme zamanı kapsüllemesi için Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md).) Olun bir `unique_ptr` tüm açık birincil hedefinin `new` ifadeler.  
  
```cpp  
unique_ptr<widget> p(new widget());  
```  
  
 Ham işaretçileri sahipliği olmayan ve gözlem için kullanabilirsiniz. Sahip olmayan bir işaretçi dangle, ancak sızıntısı olamaz.  
  
```cpp  
class node {  
  ...  
  vector<unique_ptr<node>> children; // node owns children  
  node* parent; // node observes parent, which is not a concern  
  ...  
};  
node::node() : parent(...) { children.emplace_back(new node(...) ); }  
  
```  
  
 Performansı en iyi duruma getirme gerekli olduğunda kullanmanız gerekebilir *iyi kapsüllenmiş* işaretçiler ve silmek için açık çağrılar yapamaz. Kendi alt düzey veri yapısı uyguladığınızda bir örnektir.  
  
### <a name="stack-based-lifetime"></a>Yığın tabanlı yaşam süresi  
 Modern C++ ' ta *yığın tabanlı kapsam* otomatik birleştirir çünkü sağlam kod yazmak için güçlü bir yoldur *yığın ömrü* ve *veri üyesi ömrü* yüksek verimlilik ile — İzleme ömrü yükünü temelde ücretsizdir. Yığın nesne ömrü dikkatli el ile yönetim gerektirir ve özellikle ham işaretçileri ile çalışırken kaynak sızıntıları ve verimsiz, kaynağı olabilir. Yığın tabanlı kapsam gösteren bu kodu göz önünde bulundurun:  
  
```cpp  
class widget {  
private:  
    gadget g;   // lifetime automatically tied to enclosing object  
public:  
    void draw();  
};  
  
void functionUsingWidget () {  
    widget w;   // lifetime automatically tied to enclosing scope  
                // constructs w, including the w.g gadget member  
    // ...
    w.draw();  
    // ...
} // automatic destruction and deallocation for w and w.g  
  // automatic exception safety,   
  // as if "finally { w.dispose(); w.g.dispose(); }"  
```  
  
 Statik ömrü tutumlu kullanın (genel statik, işlevi yerel statik) çünkü sorunlar ortaya çıkabilir. Genel nesne Oluşturucusu bir özel durum oluşturduğunda ne olur? Genellikle, uygulama hatalarının bir şekilde hata ayıklaması zor olabilir. Yapı sırası statik ömrü nesneler için sorunlu ve eşzamanlılık uyumlu değil. Yalnızca nesne oluşturması bir sorun olduğunu özellikle çok biçimlilik söz konusu olduğunda yok etme sırası karmaşık olabilir. Nesne veya değişken çok biçimli değil ve karmaşık yapım/sıralama yok etme yok olsa da yine iş parçacığı eşzamanlılık sorun yoktur. Birden çok iş parçacıklı bir uygulama, iş parçacığı yerel depolama, kaynak kilit ve diğer özel önlemler gerek kalmadan statik nesnelerdeki verilere güvenli bir şekilde değiştiremezsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)