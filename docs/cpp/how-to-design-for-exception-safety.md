---
title: "Nasıl yapılır: özel durum güvenliği tasarımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 19ecc5d4-297d-4c4e-b4f3-4fccab890b3d
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7d15df2f810848bb9349bc98c722ac02ff8cda17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-design-for-exception-safety"></a>Nasıl yapılır: Özel Durum Güvenliği Tasarımı
Özel durum mekanizması avantajlarından biri özel durumla ilgili verileri birlikte bu yürütme, catch, işleme deyimi doğrudan ilk özel durum oluşturur deyimden atlar. İşleyici düzeyleri herhangi bir sayıda çağrı yığınında yukarı olabilir. Try deyimi ve throw deyimine arasında adlı işlevleri oluşturulan özel durumla ilgili herhangi bir şey bilmeniz gerekli değildir.  Ancak, böylece kapsam "beklenmedik bir şekilde dışında" gidebilirsiniz tasarlanmalıdır burada bir özel durum yukarı öğesinden aşağıda yayılması ve böylece kısmen oluşturulmuş nesnelerin arkasında ayrılmadan sızmasını bellek herhangi bir noktasını veya kullanılamaz durumda veri yapılarını sahip oldukları.  
  
## <a name="basic-techniques"></a>Temel teknikleri  
 Güçlü bir özel durum işleme ilkesi dikkatle düşünürken gerektirir ve tasarım sürecinin bir parçası olması gerekir. Genel olarak, çoğu özel durum algıladı ve yazılım modülü alt katmanlar sırasında oluşturulur, ancak genellikle bu Katmanlar hatayı işleyebilir ya da son kullanıcılara bir ileti kullanıma sunmak için yeterli bağlama sahip değildir. Orta katmanda işlevleri yakalamak ve özel durum nesnesi incelemek sahip oldukları ya da sonuçta özel yakalayan bir üst katman sağlamak için başka yararlı bilgiler sahip bir özel durum yeniden oluşturma. Bir işlev yakalamak ve "yalnızca tamamen ondan kurtarabilmek için ise bir özel durum swallow". Çoğu durumda, bir özel durum çağrı yığınına yayılmasına izin vermek için Orta katmanda davranış doğrudur. Hatta en üst katmanında, özel durum, doğruluğu garanti edilemez bir durumda program bırakırsa bir programı sonlandırmak işlenmeyen bir özel durum izin vermek uygun olabilir.  
  
 Bir işlev "özel durum-güvenli," sağlanmasına yardımcı olmak için bir özel durum işleme biçimini olsun, aşağıdaki temel kurallara göre tasarlanmalıdır.  
  
### <a name="keep-resource-classes-simple"></a>Kaynak sınıfları basit tutun  
 El ile kaynak yönetimi sınıflardaki kapsülleyen, her bir kaynağın yönetmek için başka bir şey yapan bir sınıf kullanın; Aksi takdirde sızıntıları getirebilir. Kullanım [akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md) mümkün olduğunda, aşağıdaki örnekte gösterildiği gibi. Bu örnekte bilerek yapay ve simplistic farkları vurgulamak için zaman `shared_ptr` kullanılır.  
  
```cpp  
// old-style new/delete version  
class NDResourceClass {  
private:  
    int*   m_p;  
    float* m_q;  
public:  
    NDResourceClass() : m_p(0), m_q(0) {  
        m_p = new int;  
        m_q = new float;  
    }  
  
    ~NDResourceClass() {  
        delete m_p;  
        delete m_q;  
    }  
    // Potential leak! When a constructor emits an exception,   
    // the destructor will not be invoked.     
};  
  
// shared_ptr version  
#include <memory>  
  
using namespace std;  
  
class SPResourceClass {  
private:  
    shared_ptr<int> m_p;  
    shared_ptr<float> m_q;  
public:  
    SPResourceClass() : m_p(new int), m_q(new float) { }  
    // Implicitly defined dtor is OK for these members,   
    // shared_ptr will clean up and avoid leaks regardless.  
};  
  
// A more powerful case for shared_ptr  
  
class Shape {  
    // ...  
};  
  
class Circle : public Shape {  
    // ...  
};  
  
class Triangle : public Shape {  
    // ...  
};  
  
class SPShapeResourceClass {  
private:  
    shared_ptr<Shape> m_p;  
    shared_ptr<Shape> m_q;  
public:  
    SPShapeResourceClass() : m_p(new Circle), m_q(new Triangle) { }  
};  
  
```  
  
### <a name="use-the-raii-idiom-to-manage-resources"></a>RAII deyim kaynakları yönetmek için kullanın  
 Özel durum güvenli olması için bir işlev nesneleri kullanarak ayrılmış sahip olmanız gerekir `malloc` veya `new` yok olur ve dosya tanıtıcıları gibi tüm kaynakları kapalı veya bir özel durum bile, serbest. *Kaynak edinme olan başlatma* (RAII) deyim otomatik değişkenler Sysprep'in gibi kaynaklara yönetimini bağlar. Bir işlev, normalde döndürerek veya bir özel durum nedeniyle kapsamının dışına çıktığında tam olarak oluşturulan tüm otomatik değişkenler için Yıkıcılar çağrılır. Akıllı bir işaretçi gibi uygun çağırır RAII sarmalayıcı nesneyi silmek ya da kendi yıkıcı işlevinde kapatın. Özel durum güvenli kod içinde her bir kaynağın sahipliğini RAII nesnesi bir tür için hemen geçirmek oldukça önemlidir. Unutmayın `vector`, `string`, `make_shared`, `fstream`, ve benzer sınıflarını idare, kaynağın edinme.  Ancak, `unique_ptr` ve geleneksel `shared_ptr` kaynak edinme nesnenin yerine kullanıcı tarafından gerçekleştirildiğinden kurulumlarını özel; bu nedenle, bunlar olarak say *kaynak sürüm olan yok etme* ancak RAII olarak sorgulanabilir.  
  
## <a name="the-three-exception-guarantees"></a>Üç özel durum garanti  
 Genellikle, özel durum güvenliği işlevi sağlayan üç özel durum garanti bakımından ele alınmıştır: *Hayır çökme garantisi*, *güçlü garanti*ve *temel garantisi* .  
  
### <a name="no-fail-guarantee"></a>Hayır çökme garantisi  
 Hayır çökme (veya "no-throw") garantisi işlevi sağlayan güçlü garantisi yoktur. İşlevi değil bir özel durum ya da bir yayılmasına izin olduğunu belirtir. Ancak, (a), bu işlev çağrılarını tüm işlevleri de Hayır çökme bilmiyorsanız bu tür bir garanti güvenilir bir şekilde sağlayamaz (b), bu işlev düşmeden önce oluşturulan herhangi bir özel durum yakalandı bildiğiniz veya (c) yakalamak nasıl bildiğiniz ve düzgün bir şekilde bu işlev ulaşmak tüm özel durumları işler.  
  
 Güçlü garanti ve temel garantisi Yıkıcılar Hayır çökme varsayımına dayanır. Tüm kapsayıcıları ve standart kitaplığı türlerinde kendi Yıkıcılar değil throw garanti. Ayrıca Ters gereksinimi vardır: standart kitaplığı gerektirir kullanıcı tanımlı türlerinden, kendisine verilen — Örneğin, şablon bağımsız değişken olarak — atma olmayan Yıkıcılar olması gerekir.  
  
### <a name="strong-guarantee"></a>Güçlü garanti  
 Bir işlev bir özel durum nedeniyle kapsam dışında kalırsa, bu bellek ve program sızıntısı değil, güçlü garanti durumları durumu değiştirilmeyecek. Temelde COMMIT veya rollback semantiklerine sahip bir işlem güçlü garanti sağlayan bir işlev değil: tamamen başarılı ya da herhangi bir etkisi olmaz.  
  
### <a name="basic-guarantee"></a>Temel garantisi  
 Temel garanti zayıf üç sağlar. Ancak, güçlü bir garanti bellek tüketimi veya performans çok pahalı olduğunda en iyi seçim olabilir. Temel garanti durumları, bir özel durum oluştu, hiçbir bellek sızmasını veri değiştirilmiş olabilir olsa bile nesnesi hala kullanılabilir durumda ise.  
  
## <a name="exception-safe-classes"></a>Özel durum açısından güvenli sınıflar  
 Bir sınıf bile, güvenli olmayan işlevleri tarafından kısmen oluşturulmuş veya kısmen yok kendisinden engelleyerek kullanıldığında, kendi özel durum güvenliği sağlamaya yardımcı olabilir. Bir sınıf oluşturucu tamamlanmadan önce bulunup bulunmadığını nesne hiçbir zaman oluşturulur ve kendi yıkıcı hiçbir zaman çağrılır. Özel durum önce başlatılmış otomatik değişkenler sahip olsa da kendi Yıkıcılar çağrılır, dinamik olarak ayrılan belleği veya akıllı bir işaretçi tarafından yönetilmeyen kaynakları veya benzer otomatik değişkeni sızmasını.  
  
 Hayır başarısız yerleşik türleri ve en az bir temel garanti standart kitaplığı türlerini destekler. Özel durum güvenli olması kullanıcı tanımlı tür için aşağıdaki yönergeleri izleyin:  
  
-   Akıllı işaretçiler veya diğer RAII türü sarmalayıcıları tüm kaynakları yönetmek için kullanın. Kaynak Yönetimi işlevleri, sınıf yıkıcı kaçının, çünkü Oluşturucusu bir özel durum oluşturursa yıkıcı çağrılan değil. Sınıfı yalnızca bir kaynak denetimleri ayrılmış Kaynak Yöneticisi, ancak, sonra onu yıkıcı kaynakları yönetmek için kullanmayı kabul edilebilir ise.  
  
-   Bir temel sınıf oluşturucu oluşturulan bir özel bir türetilmiş sınıf oluşturucu swallowed anlayın. Temel sınıfı özel durumu türetilmiş bir oluşturucu yeniden başlatıldıysa ve Çevir istiyorsanız, bir işlev try bloğu kullanın.   
  
-   Kullanılıp özellikle bir sınıfın "başarısız olmasına izin başlatma." kavramı varsa, akıllı bir işaretçi kaydırılan bir veri üyesi tüm sınıf durumunu depolamak göz önünde bulundurun Başlatılmamış veri üyeleri için C++ olanak tanısa da başlatılmamış veya kısmen başlatılmış sınıf örneklerini desteklemez. Bir oluşturucu başarılı başarısız veya gerekir; Oluşturucusu tamamlanıncaya kadar çalışmazsa hiçbir nesnesi oluşturulur.  
  
-   Bir yıkıcı kaçınmak özel durumlar izin vermez. C++, temel axiom yıkıcı bir özel durum çağrı yığınına yayılmaya hiçbir zaman izin vermelidir ' dir. Bir yıkıcı bir olası özel durum atma işlemi gerçekleştirmeniz gerekirse, bu nedenle bir try catch bloğu ve gerekir özel durum swallow. Standart Kitaplığı, bu garantisi tanımladığı tüm Yıkıcılar üzerinde sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Nasıl yapılır: Özel Durumlu Kod ve Özel Durumlu Olmayan Kod Arasında Arabirim](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)