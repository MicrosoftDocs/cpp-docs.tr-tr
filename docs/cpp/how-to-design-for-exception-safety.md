---
title: 'Nasıl yapılır: özel durum güvenliği için tasarım'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 19ecc5d4-297d-4c4e-b4f3-4fccab890b3d
ms.openlocfilehash: 732a46166c99396c5d55a7d2acd834b58f3d2b2e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87187809"
---
# <a name="how-to-design-for-exception-safety"></a>Nasıl yapılır: özel durum güvenliği için tasarım

Özel durum mekanizmasının avantajlarından biri, yürütme, özel durum hakkındaki verilerle birlikte, özel durumu işleyen ilk catch ifadesine doğrudan atmayı atlayan deyimden atlar. İşleyici, çağrı yığınında herhangi bir sayıda düzey olabilir. TRY ve throw deyimlerinin arasına çağrılan işlevlerin, oluşturulan özel durum hakkında herhangi bir şeyi bilmeleri için gerekli değildir.  Bununla birlikte, bir özel durumun aşağıdan yayabileceği herhangi bir noktada "beklenmedik" kapsam dışına çıkabilmeleri için tasarlanmaları gerekir ve bunu yapmak, kısmen oluşturulan nesnelerin arkasında, sızdırılan belleğin veya kullanılamaz durumda olan veri yapılarının arkasına çıkmadan devam edebilirler.

## <a name="basic-techniques"></a>Temel teknikler

Sağlam bir özel durum işleme ilkesi dikkat etmeniz gerekir ve tasarım sürecinin bir parçası olmalıdır. Genel olarak, çoğu özel durum bir yazılım modülünün alt katmanlarında algılanır ve oluşturulur, ancak genellikle bu katmanların hatayı işlemek için yeterli bağlamı yoktur veya son kullanıcılara bir ileti sunabilir. Orta katmanlarda işlevler, özel durum nesnesini incelemek istediklerinde bir özel durumu yakalayabilir ve yeniden oluşturabilir veya son olarak özel durumu yakalayan üst katmana sağlamak için ek faydalı bilgiler sağlar. Bir işlev yalnızca bundan tamamen kurtarılamadığında bir özel durum yakalamalı ve "Swallow". Çoğu durumda, orta katmanlardaki doğru davranış, çağrı yığınını yaymaya özel bir durum vermek olur. En yüksek katmanda bile, özel durum programı, doğruluk garantisi garanti edilemez bir durumda bırakırsa, bir programı sonlandırma özel durumunun bir program tarafından sonlandırılmasına izin vermek uygun olabilir.

Bir işlevin özel durumu nasıl işleydiğine bakılmaksızın, "özel durum güvenli" olduğunu garantilemeye yardımcı olmak için, aşağıdaki temel kurallara göre tasarlanmalıdır.

### <a name="keep-resource-classes-simple"></a>Kaynak sınıflarını basit tut

Sınıflarda el ile kaynak yönetimini kapsüllemek istediğinizde, tek bir kaynağı Yönet dışında hiçbir şey olmayan bir sınıf kullanın. Sınıfı basit tutarak, kaynak sızıntılarını tanıtma riskini azaltabilirsiniz. Aşağıdaki örnekte gösterildiği gibi, mümkün olduğunda [akıllı işaretçiler](smart-pointers-modern-cpp.md) kullanın. Bu örnek kasıtlı olarak yapay ve uyarlaması kullanıldığında farklılıkları vurgulayacağız `shared_ptr` .

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

### <a name="use-the-raii-idiom-to-manage-resources"></a>Kaynakları yönetmek için ÇII IBU deyim kullanma

Özel durum güvenli olması için bir işlev, veya kullanılarak ayrılan nesnelerin `malloc` **`new`** yok edileceği ve dosya tutamaçları gibi tüm kaynakların kapalı veya bir özel durum oluşsa bile serbest bırakılmış olduğundan emin olmalıdır. *Kaynak alımı* , bu tür kaynakların otomatik değişkenlerin kullanım ömrü için başlatılması (rampaıı) deyimidir. Bir işlev, normal olarak veya bir özel durum nedeniyle kapsam dışına geçtiğinde, tümüyle oluşturulmuş tüm otomatik değişkenlerin yıkıcıları çağrılır. Akıllı işaretçi gibi bir KORıı sarmalayıcı nesnesi, yıkıcısında uygun DELETE veya Close işlevini çağırır. Özel durum güvenli kodunda, her bir kaynağın sahipliğini hemen bir tür rampaya da bir nesne türüne geçirmek oldukça önemlidir. ,,, `vector` `string` `make_shared` `fstream` Ve benzer sınıfların kaynağı sizin için edindiğini unutmayın.  Ancak, `unique_ptr` `shared_ptr` kaynak alımı nesne yerine Kullanıcı tarafından gerçekleştirildiğinden, ve geleneksel kurulumlarını özeldir; bu nedenle, *kaynak yayını yok SAYıLıR* ancak kii olarak şüpheli olur.

## <a name="the-three-exception-guarantees"></a>Üç özel durum garanti

Genellikle özel durum güvenliği, bir işlevin sağlayabileceğinizin üç özel durum garanti açısından ele alınmıştır: *No-Fail garantisi*, *Strong garantisi*ve *temel garanti*.

### <a name="no-fail-guarantee"></a>Başarısızlık garantisi

No-Fail (veya "no-throw") garantisi, bir işlevin sağlayabileceğinizin en güçlü garantisi. İşlevin bir özel durum oluşturmadığını veya bir tane yaymasına izin vermeyeceğini belirtir. Ancak, (a) Bu işlev çağrılarının tüm işlevlerinin aynı zamanda başarısız olduğunu veya (b), oluşturulan tüm durumların bu işleve ulaşmadan yakalanıp yakalanmadığını veya (c) bu işleve ulaşacak tüm özel durumları nasıl yakalayabileceğinizi ve doğru bir şekilde nasıl işleneceğini bildiğiniz durumlar dışında güvenilir bir şekilde garanti sağlayamazsınız.

Kesin garanti ve temel garanti, yok edicilerin başarısız olduğu varsayımına dayanır. Standart kitaplıktaki tüm kapsayıcılar ve türler, yok edicilerin throw oluşturmadığından emin. Aynı zamanda bir de aynı gereksinim vardır: standart kitaplık, kendisine verilen Kullanıcı tanımlı türlerin (örneğin, şablon bağımsız değişkenleri gibi) oluşturmasız yıkıcıları olmalıdır.

### <a name="strong-guarantee"></a>Güçlü garanti

Güçlü garanti, bir işlev bir özel durum nedeniyle kapsam dışına geçtiğinde, bellek sızıntısına neden olur ve program durumu değiştirilmez. Kesin bir garanti sağlayan bir işlev aslında işleme veya geri alma semantiğinin bulunduğu bir işlemdir: tamamen başarılı olur ya da hiçbir etkisi yoktur.

### <a name="basic-guarantee"></a>Temel garanti

Temel garanti, üçünün en zayıf güvencesini içerir. Ancak, bir güçlü garanti, bellek tüketimine veya performanstan çok pahalı olduğunda en iyi seçenek olabilir. Temel garanti, bir özel durum oluşursa, bellek sızdırılmaması ve verilerin değiştirilmiş olmasına karşın hala kullanılabilir durumda olduğunu belirtir.

## <a name="exception-safe-classes"></a>Özel durum güvenli sınıfları

Bir sınıf, kendi özel durum güvenliğine, güvenli olmayan işlevler tarafından tüketilse bile, kendi kısmen oluşturulmasını veya kısmen yok etmesini önlemeye yardımcı olabilir. Bir sınıf oluşturucusu tamamlanmadan önce çıkmadıysa, nesne hiçbir şekilde oluşturulmaz ve yok edicisi hiçbir şekilde çağrılmaz. Özel durumdan önce başlatılan otomatik değişkenlerin yok ediciler, dinamik olarak ayrılan bellek veya akıllı bir işaretçi ya da benzer bir otomatik değişken tarafından yönetilmeyen kaynaklar sızdırılacaktır.

Yerleşik türler tamamen başarısız olur ve standart kitaplık türleri en az bir temel garantisi destekler. Özel durum güvenli olması gereken kullanıcı tanımlı herhangi bir tür için bu yönergeleri izleyin:

- Tüm kaynakları yönetmek için akıllı işaretçiler veya diğer ÇII türü sarmalayıcıları kullanın. Oluşturucu bir özel durum oluşturursa yok edici çağrılmayacağından, sınıf yıkıcıdaki kaynak yönetimi işlevlerinden kaçının. Ancak, sınıfı yalnızca bir kaynağı denetleyen adanmış bir kaynak yöneticisi ise, kaynakları yönetmek için yıkıcıyı kullanmak kabul edilebilir.

- Bir temel sınıf oluşturucusunda oluşan özel durumun türetilmiş bir sınıf oluşturucusunda sallowed olduğunu anlayın. Türetilmiş bir oluşturucuda temel sınıf özel durumunu çevirmek ve yeniden oluşturmak istiyorsanız, bir işlev try bloğu kullanın.

- Özellikle bir sınıfta "başarısız olmasına izin verilen başlatma" kavramı varsa, bir akıllı işaretçiye Sarmalanan bir veri üyesinde tüm sınıf durumlarını depolayıp depolayacağınızı düşünün. C++ başlatılmamış veri üyelerine izin verse de, başlatılmamış veya kısmen başlatılmış sınıf örneklerini desteklemez. Bir oluşturucunun başarılı ya da başarısız olması gerekir; Oluşturucu tamamlanana kadar çalıştırılmadıysa hiçbir nesne oluşturulmaz.

- Herhangi bir özel durumun yıkıcıya çıkmasına izin vermeyin. Temel bir axiod C++, yok edicilerin çağrı yığınını yaymaya bir özel duruma asla izin vermemelidir. Yıkıcı bir özel durum atma işlemi gerçekleştirirse, bunu bir try catch bloğunda yapması gerekir ve özel duruma izin verin. Standart Kitaplık, tanımladığı tüm yıkıcılarda bu garantisi sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](errors-and-exception-handling-modern-cpp.md)<br/>
[Nasıl yapılır: olağanüstü ve olağanüstü olmayan kod arasında arabirim](how-to-interface-between-exceptional-and-non-exceptional-code.md)
