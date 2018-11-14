---
title: 'Nasıl yapılır: Özel Durum Güvenliği Tasarımı'
ms.custom: how-to
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 19ecc5d4-297d-4c4e-b4f3-4fccab890b3d
ms.openlocfilehash: f384da3eee0c7bca80d8d6c61f8d8cf0cfaece92
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327011"
---
# <a name="how-to-design-for-exception-safety"></a>Nasıl yapılır: Özel Durum Güvenliği Tasarımı

Avantajlarından biri özel durum mekanizması birlikte özel durum hakkındaki verileri bu yürütme, catch işleme deyimi deyimden öncelikle özel durum oluşturan doğrudan atlar. İşleyici düzeyleri herhangi bir sayıda çağrı yığınında yukarı olabilir. Throw deyimi try deyimi arasında çağıran işlevler oluşturulan özel durum hakkında bir şey bilmek için gerekli değildir.  Bununla birlikte, kapsamı "beklenmedik bir şekilde dışında" gidebilirsiniz olacak şekilde tasarlanmış olması burada bir özel durum yukarı gelen aşağıda yayar ve bu nedenle kısmen oluşturulan nesnelerin arkasında çıkmadan sızmasına bellek herhangi bir noktasını veya kullanılamaz durumda olmadığından veri yapılarını sahiptirler.

## <a name="basic-techniques"></a>Temel teknikleri

Sağlam bir özel durum işleme ilkesi dikkatli düşünce gerektirir ve tasarım sürecinin bir parçası olmalıdır. Genel olarak, çoğu özel durumların algılandı ve bir yazılım modülü daha düşük katmanlardaki sırasında oluşturulur, ancak genellikle bu Katmanlar hatayı işlemek veya son kullanıcılara bir ileti kullanıma sunmak için yeterli bağlam yoktur. Orta katmanda işlevleri catch ve özel durum nesnesi incelemek sahip oldukları veya sahip oldukları için sonuç olarak özel durumu yakalar üst katman sağlamak için ek yararlı bilgiler bir özel durumu yeniden kullanabilirsiniz. Bir işlev, catch ve "yalnızca tamamen CİHAZDAN kurtarmanız mümkün ise bir özel durum swallow". Çoğu durumda, bir özel durum çağrı yığınına yayılmaya izin vermek için Orta katmanda davranış doğrudur. Bile en üst katmanında, özel durum, doğruluğu garanti edilemez durumda program ayrıldığında bir programı sonlandırmak işlenmeyen bir özel durum izin vermek uygun olabilir.

Bir işlev "özel durum açısından güvenli," sağlanmasına yardımcı olmak için bir özel durum, nasıl işlediğini ne olursa olsun, aşağıdaki temel kurallara göre tasarlanmış olması gerekir.

### <a name="keep-resource-classes-simple"></a>Kaynak sınıfları basit tutun

El ile kaynak yönetimi sınıflardaki yalıtma, her kaynak için başka bir şey yapmaz bir sınıf kullanma; Aksi takdirde, sızıntılarına yol açabilir. Kullanım [akıllı işaretçileri](../cpp/smart-pointers-modern-cpp.md) mümkün olduğunda, aşağıdaki örnekte gösterildiği gibi. Kasıtlı olarak yapay ve alıyormuş farklar vurgulamak için bu örnekte, zaman `shared_ptr` kullanılır.

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

### <a name="use-the-raii-idiom-to-manage-resources"></a>Kaynakları yönetmek için RAII deyim kullanma

Özel durum açısından güvenli olmak üzere bir işlevi kullanılarak ayrılmış sahip nesneleri emin olmanız gerekir `malloc` veya **yeni** yok edilir ve dosya tanıtıcıları gibi tüm kaynaklara kapalı veya bir özel durum olsa bile yayımladı. *Olduğu kaynak alımı başlatma* (RAII) deyimidir yönetimini otomatik değişkenler ömrü gibi kaynaklara bağlar. Bir işlev, normalde döndürerek veya bir özel durum nedeniyle kapsam dışına çıktığında tam oluşturulmuş tüm otomatik değişkenler için yok ediciler çağrılır. Akıllı bir işaretçi gibi uygun çağıran bir RAII sarmalayıcı nesne silin veya işlev yok edici kapatın. Özel durum-güvenli kod içinde her bir kaynağın sahipliğini hemen bazı tür RAII nesneyi geçirmek oldukça önemlidir. Unutmayın `vector`, `string`, `make_shared`, `fstream`, ve benzer sınıflar, için kaynağın alım.  Ancak, `unique_ptr` ve geleneksel `shared_ptr` kaynak alımının nesnenin yerine kullanıcı tarafından gerçekleştirildiği için yapılarını özel; bu nedenle, bunlar olarak say *kaynak sürüm olan yok etme* ancak RAII olarak sorgulanabilir.

## <a name="the-three-exception-guarantees"></a>Üç özel durum garantisi

Genellikle, özel durum güvenliği bir işlev sağlayan üç özel durum garantisinden açısından ele alınmıştır: *Hayır çökme garantisi*, *güçlü garanti*ve *temel garantisi* .

### <a name="no-fail-guarantee"></a>Hayır-başarısız garantisi

Hayır-başarısız (veya "fırlatmasız") garantisi, bir işlev sağlayan güçlü garanti yoktur. Bu işlev değil bir özel durum veya bir yayılmasına izin olduğunu belirtir. Ancak, (a) bu işlevi çağıran tüm işlevleri no-başarısız olduğunu bilmediği sürece bir böyle bir garanti güvenilir bir şekilde sağlayamaz veya (b), bu işlev ulaşmadan önce attığı özel durumları yakalanır bildiğiniz veya nasıl catch (c), bildiğiniz ve Bu işlev ulaşan tüm istisnalarla başa.

Hem güçlü garanti hem de temel garanti yok ediciler Hayır çökme varsayımına güvenir. Tüm kapsayıcıları ve standart kitaplık türleri, Yıkıcılar değil throw garanti. De ters gereksinim mevcuttur: Standart Kitaplığı gerektiren kullanıcı tanımlı türler, kendisine verilen — Örneğin, şablon bağımsız değişkenleri olarak — oluşturmayan Yıkıcılar olması gerekir.

### <a name="strong-guarantee"></a>Güçlü garanti

Güçlü garanti, bir işlev bir özel durum nedeniyle kapsam dışında kalırsa, onu bellek ve program sızıntı oluşturacaktır değil, durumları durum değiştirilmeyecek. Güçlü garanti sağlayan bir işlev yürütme veya geri alma semantiğe sahip işlem temelde,: ya tamamen başarılı ya da hiçbir etkisi olmaz.

### <a name="basic-guarantee"></a>Temel garantisi

Temel bir garanti üç zayıfa doğru sağlar. Ancak, güçlü garanti bellek tüketimi veya performans çok pahalı olduğunda en iyi seçenek olabilir. Temel garanti durumlar, özel bir durum oluştuğunda, bellek sızmış ve verileri değiştirilmiş olabilir olsa da hala kullanılabilir durumda nesnedir.

## <a name="exception-safe-classes"></a>Özel durum açısından güvenli sınıflar

Bir sınıf, kısmen oluşturulmuş veya kısmen yok kendisini engelleyerek güvenli olmayan işlevler tarafından bile tüketildiği kendi özel durum güvenliği sağlamaya yardımcı olabilir. Tamamlanmadan önce bir sınıfın Oluşturucusu varsa nesne hiçbir zaman oluşturulur ve yok edici asla çağrılmaz. Özel durum önce başlatılan otomatik değişkenler sahip, ancak bunların yok ediciler çağrılır, dinamik olarak ayrılan bellek veya akıllı bir işaretçi tarafından yönetilmeyen kaynakları veya benzer otomatik değişken leaked.

Hayır çökme tüm yerleşik türler ve temel garanti en az standart kitaplık türleri destekler. Özel durum açısından güvenli olmalıdır kullanıcı tanımlı türü için aşağıdaki yönergeleri izleyin:

- Akıllı işaretçiler veya diğer tür RAII sarmalayıcıları tüm kaynakları yönetmek için kullanın. Kaynak Yönetimi işlevselliği, sınıf yok edicisini kaçının, çünkü Oluşturucusu bir özel durum oluşturursa yok Edicisi çağrılır değil. Sınıfı yalnızca bir kaynak denetleyen bir adanmış Kaynak Yöneticisi, ancak ardından, yok Edicisi kaynakları yönetmek için kullanmak kabul edilebilir ise.

- Bir taban sınıfı oluşturucusunda bir özel durum türetilmiş sınıf oluşturucu rediscache anlayın. Çevirin ve türetilmiş bir oluşturucuda temel sınıfı özel durumu yeniden harekete geçirerek istiyorsanız, bir işlev try bloğu kullanın.

- Özellikle, bir sınıfın "başarısız olmasına izin başlatma." kavramı varsa, bir akıllı işaretçi içinde sarmalanmış bir veri üyesi tüm sınıf durumunu depolamak etkinleştirilip etkinleştirilmeyeceğini göz önünde bulundurun Başlatılmamış veri üyeleri için C++ olanak tanısa da başlatılmamış veya kısmen başlatılmış sınıf örneklerinin desteklemez. Bir oluşturucu başarılı başarısız veya gerekir; Oluşturucu tamamlanana kadar çalışmazsa hiçbir nesne oluşturulur.

- Bir yok ediciden kaçış özel durumların izin vermez. C++'ın temel bir axiom yok ediciler, bir özel durum çağrı yığınına yayılmaya hiçbir zaman izin vermelidir ' dir. Bir yok edici bir özel durum büyük olasılıkla işlemi gerçekleştirmesi gerekiyorsa, bu nedenle bir try catch bloğu ve gerekir swallow özel durum. Standart kitaplık bu garanti tanımladığı tüm yok ediciler üzerinde sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Nasıl yapılır: Özel Durumlu Kod ve Özel Durumlu Olmayan Kod Arasında Arabirim](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)