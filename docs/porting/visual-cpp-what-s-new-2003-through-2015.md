---
title: Visual C++ Ne&#39;2003'ten 2015'e kadar
ms.date: 07/02/2019
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
ms.openlocfilehash: 48b812bf43918d7fbc37d20d0ef1b02348759544
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332091"
---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Visual C++ Ne&#39;2003'ten 2015'e kadar

Bu sayfa Visual Studio 2015'ten 2003'e kadar Visual C++'ın tüm sürümleri için "What's New" sayfalarını bir araya getirmiştir. Bu bilgiler, Visual Studio'nun önceki sürümlerinden yükseltme yaparken yararlı olabilir diye bir kolaylık olarak sağlanır.

> [!NOTE]
> Visual Studio'nun geçerli sürümü hakkında bilgi için Visual [Studio'da Visual C++ için yenilikler](../overview/what-s-new-for-visual-cpp-in-visual-studio.md) ve [Visual Studio'da Visual C++'da Uyumluluk Geliştirmeleri](../overview/cpp-conformance-improvements.md)bölümüne bakın.

## <a name="whats-new-for-c-in-visual-studio-2015"></a>Visual Studio 2015'te C++ Için Yenilikler

Visual Studio 2015 ve sonraki alanlarda, derleyici uygunluğuiçin devam eden iyileştirmeler bazen derleyicinin varolan kaynak kodunuzu nasıl anladığını değiştirebilir. Bu durumda, yapınız sırasında yeni veya farklı hatalarla, hatta daha önce oluşturulmuş ve doğru şekilde çalışan koddaki davranış farklılıklarıyla karşılaşabilirsiniz.

Neyse ki, bu farklılıkların kaynak kodlarınızın çoğu üzerinde çok az veya hiç etkisi yoktur ve bu farklılıkları gidermek için kaynak kodu veya diğer değişiklikler gerektiğinde, düzeltmeler genellikle küçük ve doğrudan ileri ye dir. Daha önce değiştirilmesi gereken *(önce)* ve düzeltmelerin *düzeltilmesi (sonra)* birçok örnek ekledik.

Bu farklılıklar kaynak kodunuzu veya diğer yapı yapılarını etkilese de, Visual C++ sürümlerinde yapılan güncelleştirmeler arasındaki ikili uyumluluğu etkilemez. Daha ciddi bir değişiklik türü, *kırılma değişikliği* ikili uyumluluğu etkileyebilir, ancak bu tür ikili uyumluluk molaları yalnızca Visual C++'ın ana sürümleri arasında gerçekleşir. Örneğin, Visual C++ 2013 ve Visual C++ 2015 arasında. Visual C++ 2013 ile Visual C++ 2015 arasında gerçekleşen son dakika değişiklikleri hakkında bilgi için [Visual C++ change history 2003 - 2015'e](../porting/visual-cpp-change-history-2003-2015.md)bakın.

- [Visual Studio 2015'te Uygunluk Geliştirmeleri](#VS_RTM)

- [Visual Studio 2015 Güncelleme 1'de Uygunluk Geliştirmeleri](#VS_Update1)

- [Visual Studio 2015 Güncelleme 2'de Uygunluk Geliştirmeleri](#VS_Update2)

- [Visual Studio 2015 Güncelleme 3'te Uygunluk Geliştirmeleri](#VS_Update3)

### <a name="conformance-improvements-in-visual-studio-2015"></a><a name="VS_RTM"></a>Visual Studio 2015'te Uygunluk Geliştirmeleri

- **/Zc:forScope- seçeneği**

   Derleyici seçeneği `/Zc:forScope-` amortismana alınır ve ileride sürülecek şekilde kaldırılır.

   ```output
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release
   ```

   Bu seçenek genellikle, standart göre kapsam dışına çıkmaları gereken noktadan sonra döngü değişkenlerini kullanan standart dışı koda izin vermek için kullanılmıştır. Bu yalnızca `/Za` seçenekle derlediğinizde gerekliydi, `/Za`çünkü döngü nün bitiminden sonra for döngüsü değişkeni kullanmak her zaman izin verilir. Standartlara uygunluğu önemsemiyorsanız (örneğin, kodunuz diğer derleyicilere taşınabilir değilse), `/Za` seçeneği kapatabilir (veya Devre Dışı BırakDil Uzantıları özelliğini **No**olarak **ayarlayabilirsiniz).** Taşınabilir, standartlara uygun kod yazmayı önemsiyorsanız, bu tür değişkenlerin bildirimini döngü dışında bir noktaya taşıyarak kodunuzu standarda uygun olacak şekilde yeniden yazmalısınız.

   ```cpp
    // zc_forScope.cpp
    // compile with: /Zc:forScope- /Za
    // C2065 expected
    int main() {
       // Uncomment the following line to resolve.
       // int i;
       for (int i =0; i < 1; i++)
          ;
       i = 20;   // i has already gone out of scope under /Za
    }
   ```

- **Zg derleyici seçeneği.**

   `/Zg` Derleyici seçeneği (İşlev Prototipleri Oluştur) artık kullanılamıyor. Bu derleyici seçeneği daha önce küçümsüldü.

- C++/CLI ile birim testlerini artık mstest.exe ile komut satırından çalıştıramazsınız. Bunun yerine, vstest.console.exe kullanın

- **mutable anahtar kelime.**

   Daha önce hatasız derlendiği yerlerde **değişken** depolama sınıfı belirteci artık izin verilmez. Şimdi, derleyici hata C2071 (yasadışı depolama sınıfı) verir. Standarda göre, mutable belirteç yalnızca sınıf veri üyelerinin adlarına uygulanabilir ve const veya statik olarak bildirilen adlara uygulanamaz ve başvuru üyelerine uygulanamaz.

   Örneğin, aşağıdaki kodu göz önünde bulundurun:

   ```cpp
    struct S {
        mutable int &r;
    };
   ```

   Microsoft C++ derleyicisinin önceki sürümleri bunu kabul etti, ancak şimdi derleyici aşağıdaki hatayı veriyor:

   ```Output
    error C2071: 'S::r': illegal storage class
   ```

   Hatayı gidermek için, gereksiz **mutable** anahtar sözcüğünü kaldırmanız yeterlidir.

- **char_16_t ve char32_t**

   Bu türler artık `char16_t` `char32_t` yerleşik olarak kabul edilir, çünkü artık bir typedef'te başka bir ad olarak kullanamazsınız. Kullanıcıların `char16_t` ve kitaplık yazarlarının `char32_t` `uint16_t` `uint32_t`sırasıyla diğer adları ve diğer adları tanımlaması yaygındı.

   ```cpp
    #include <cstdint>

    typedef uint16_t char16_t; //C2628
    typedef uint32_t char32_t; //C2628

    int main(int argc, char* argv[])
    {
    uint16_t x = 1; uint32_t y = 2;
    char16_t a = x;
    char32_t b = y;
    return 0;
    }
   ```

   Kodunuzu güncelleştirmek için **typedef** bildirimlerini kaldırın ve bu adlarla çarpışan diğer tanımlayıcıları yeniden adlandırın.

- **Türü olmayan şablon parametreleri**

   Tür dışı şablon parametrelerini içeren belirli kod, açık şablon bağımsız değişkenleri sağladığınızda tür uyumluluğu için doğru şekilde denetlenir. Örneğin, Visual C++'ın önceki sürümlerinde hatasız olarak derlenen aşağıdaki kod.

   ```cpp
    struct S1
    {
        void f(int);
        void f(int, int);
    };

    struct S2
    {
        template <class C, void (C::*Function)(int) const> void f() {}
    };

    void f()
    {
        S2 s2;
        s2.f<S1, &S1::f>();
    }
   ```

   Şablon parametre türü şablon bağımsız değişkeniyle eşleşmediği için geçerli derleyici doğru bir hata verir (parametre const üyeiçin bir işaretçidir, ancak f işlevi const değildir):

   ```Output
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'
   ```

   Kodunuzdaki bu hatayı gidermek için, kullandığınız şablon bağımsız değişkeninin türünün bildirilen şablon parametre türüyle eşleştiğinden emin olun.

- **__declspec(hizala)**

   Derleyici artık işlevleri `__declspec(align)` kabul etmez. Bu her zaman yoksayılır, ancak şimdi bir derleyici hatası üretir.

   ```cpp
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations
   ```

   Bu sorunu gidermek `__declspec(align)` için işlev bildiriminden kaldırın. Hiçbir etkisi olmadığı için, kaldırmak hiçbir şeyi değiştirmez.

- **Özel durum işleme**

   Özel durum işlemede birkaç değişiklik vardır. İlk olarak, özel durum nesnelerinin kopyalanabilir veya taşınabilir olması gerekir. Visual Studio 2013'te derlenen ancak Visual Studio 2015'te derlenen aşağıdaki kod:

   ```cpp
    struct S {
    public:
        S();
    private:
        S(const S &);
    };

    int main()
    {
        throw S(); // error
    }
   ```

   Sorun, kopya oluşturucu nun özel olmasıdır, bu nedenle nesne bir özel durumu işleme normal seyrinde olduğu gibi kopyalanamaz. Aynı durum, kopya oluşturucu **açık**olarak beyan edildiğinde de geçerlidir.

   ```cpp
    struct S {
        S();
        explicit S(const S &);
    };

    int main()
    {
        throw S(); // error
    }
   ```

   Kodunuzu güncelleştirmek için, özel durum nesnenizin kopya oluşturucusu ortak olduğundan ve **açık**olarak işaretlenmemiş olduğundan emin olun.

   Bir özel durum değerine göre yakalamak da özel durum nesnesinin kopyalanabilir olmasını gerektirir. Visual Studio 2013'te derlenen ancak Visual Studio 2015'te derlenen aşağıdaki kod:

   ```cpp
    struct B {
    public:
        B();
    private:
        B(const B &);
    };

    struct D : public B {
    };

    int main()
    {
        try
        {
        }
        catch (D d) // error
        {
        }
    }
   ```

   **Catch** için parametre türünü bir başvuruyla değiştirerek bu sorunu giderebilirsiniz.

   ```cpp
    catch(D& d)
    {
    }
   ```

- **Dizeleri literals makrolar tarafından takip**

   Derleyici artık kullanıcı tanımlı literalleri destekler. Sonuç olarak, herhangi bir müdahale beyaz boşluk olmadan makrolar tarafından takip string literals hatalar veya beklenmeyen sonuçlar üretebilir kullanıcı tanımlı literals olarak yorumlanır. Örneğin, önceki derleyicilerde aşağıdaki kod başarıyla derlenmiştir:

   ```cpp
    #define _x "there"
    char* func() {
        return "hello"_x;
    }
    int main()
    {
        char * p = func();
        return 0;
    }
   ```

   Derleyici bunu bir dize olarak yorumladı "merhaba" ve ardından "orada" genişletilen bir makro, ve sonra iki dize literals bir araya getirilmiştir. Visual Studio 2015'te derleyici bunu kullanıcı tanımlı bir edebi olarak yorumluyor, ancak kullanıcı tanımlı _x tanımlı bir eşleşme olmadığından hata verir.

   ```cpp
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found
    note: Did you forget a space between the string literal and the prefix of the following string literal?

   ```

   Bu sorunu gidermek için, dize literal ve makro arasında bir boşluk ekleyin.

- **Bitişik dize literals**

   Öncekine benzer şekilde, dize ayrıştırma ile ilgili değişiklikler nedeniyle, herhangi bir boşluk olmadan bitişik dize literals (ya geniş veya dar karakter dize literals) Visaul C++'ın önceki sürümlerinde tek bir concatenated dize olarak yorumlandı. Visual Studio 2015'te, artık iki dize arasına boşluk eklemeniz gerekir. Örneğin, aşağıdaki kodun değiştirilmesi gerekir:

   ```cpp
    char * str = "abc""def";
   ```

   Sadece iki dizeleri arasında bir boşluk ekleyin.

   ```cpp
    char * str = "abc" "def";
   ```

- **Yeni yerleştirme ve silme**

   C++14 standardına uygun hale getirmek için **silme** işlecinde bir değişiklik yapıldı. Standart değişikliğinin ayrıntıları [C++ Boyutlu Deallocation'da](https://isocpp.org/files/papers/n3778.html)bulunabilir. Değişiklikler, boyut **parametresi** alan genel silme işlecinin bir biçimini ekler. Kesme değişikliği, daha önce aynı imzayla bir operatör **silme** kullanıyorsanız **(yeni bir yerleşim** operatörüyle karşılık gelmek üzere), derleyicinin uygun eşleşen bir **silme** işlecini tanımlamaya çalıştığı koddaki konum olduğundan, yeni **yerleşimin** kullanıldığı noktada oluşan bir derleyici hatası (C2956) alırsınız.

   İşlev, `void operator delete(void *, size_t)` C++11'deki yerleşim `void * operator new(size_t, size_t)` **yeni** işlevine karşılık gelen bir yerleşim **silme** işleciydi. C++14 boyutlu deallocation ile bu **silme** işlevi artık olağan bir *ayırma işlevidir* (global **delete** işleci). Standart, bir **yerleşim yeni** kullanımı karşılık gelen bir **silme** işlevi arar ve her zamanki bir deallocation işlevi bulursa, program kötü biçimlendirilmiş olması gerektirir.

   Örneğin, kodunuzun hem yeni bir **yerleşim** hem de **bir yerleşim silme**tanımladığını varsayalım:

   ```cpp
    void * operator new(std::size_t, std::size_t);
    void operator delete(void*, std::size_t) noexcept;
   ```

   Sorun, tanımladığınız bir **yerleşim silme** işleci ile yeni genel boyutlu **silme** işleci arasındaki işlev imzalarında eşleşme nedeniyle oluşur. Herhangi bir **yerleşim yeni** ve `size_t` **silme** işleçleri için farklı bir tür kullanabilirsiniz olup olmadığını düşünün.  `size_t` **Typedef** türünün derleyiciye bağlı olduğunu unutmayın; Visual **C++'da imzasız int** için bir **typedef'tir.** İyi bir çözüm, şu gibi numaralandırılmış bir tür kullanmaktır:

   ```cpp
    enum class my_type : size_t {};
   ```

   Daha sonra, **yeni** yerleşim tanımınızı değiştirin ve bu tür `size_t`yerine ikinci bağımsız değişken olarak kullanmak için **sil.** Ayrıca, yeni türü geçmek için **yeni yerleşim** çağrılarını güncelleştirmeniz (örneğin, tamsayı değerinden dönüştürmeyi kullanarak) `static_cast<my_type>` ve tamsayı türüne geri döküm yapmak için **yeni** ve **silme** tanımını güncelleştirmeniz gerekir. Bunun için **enum** kullanmanızgerekmez; bir üye ile `size_t` bir sınıf türü de çalışacak.

   Alternatif bir çözüm, **yerleşim yeni** tamamen ortadan kaldırmak mümkün olabilir. Kodunuz, yerleşim bağımsız değişkeninin ayrılan veya silinen nesnenin boyutu olduğu bir bellek havuzu uygulamak için **yeni yerleşim** kullanıyorsa, boyutlandırma özelliği kendi özel bellek havuzu kodunuzu değiştirmek için uygun olabilir ve yerleşim işlevlerinden kurtulabilir ve yerleşim işlevleri yerine kendi iki bağımsız değişken **silme** işlecinizi kullanabilirsiniz.

   Kodunuzu hemen güncelleştirmek istemiyorsanız, derleyici seçeneğini `/Zc:sizedDealloc-`kullanarak eski davranışa geri dönebilirsiniz. Bu seçeneği kullanırsanız, iki bağımsız değişken **silme** işlevleri yok ve **yerleşim silme** operatörünüzle bir çakışma neden olmaz.

- **Birlik veri üyeleri**

   Birliş veri üyeleri artık başvuru türlerine sahip olamaz. Aşağıdaki kod Visual Studio 2013'te başarıyla derlenmiştir, ancak Visual Studio 2015'te bir hata üretir.

   ```cpp
    union U1 {
        const int i;
    };
    union U2 {
       int &i;
    };
    union U3 {
        struct {int &i;};
    };
   ```

   Önceki kod aşağıdaki hataları üretir:

   ```Output
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type
   ```

   Bu sorunu gidermek için başvuru türlerini bir işaretçi veya değer olarak değiştirin. Türü işaretçiye değiştirmek, birleşim alanını kullanan kodda değişiklikler gerektirir. Kodu bir değere değiştirmek, birleşim türlerindeki alanlar aynı belleği paylaştığından diğer alanları etkileyen birleşimde depolanan verileri değiştirir. Değerin boyutuna bağlı olarak, birlikteliğin boyutunu da değiştirebilir.

- **Anonim sendikalar**

   artık standarda daha uygun. Derleyicinin önceki sürümleri, anonim sendikalar için açık bir yapıcı ve yıkıcı oluşturucu oluşturucu oluşturucu oluşturucu oluşturucu oluşturucu oluşturucu yut. Bunlar Visual Studio 2015'te silinir.

   ```cpp
   struct S {
      S();
   };

   union {
      struct {
         S s;
      };
   } u; // C2280
   ```

   Önceki kod Visual Studio 2015'te aşağıdaki hatayı oluşturur:

   ```cpp
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here
   ```

   Bu sorunu çözmek için, yapıcı ve / veya yıkıcı kendi tanımlarını sağlayın.

   ```cpp
    struct S {
       // Provide a default constructor by adding an empty function body.
       S() {}
    };

    union {
       struct {
          S s;
       };
    } u;
   ```

- **Anonim yapılı sendikalar**

   Standarda uymak için, sendikalardaki anonim yapıların üyeleri için çalışma zamanı davranışı değişti. Bir sendikadaki anonim yapı üyelerinin oluşturucusu, böyle bir birlik oluşturulduğunda artık örtülü olarak çağrılmaz. Ayrıca, bir sendikadaki anonim yapı üyelerinin imha edicisi, sendika kapsam dışına çıktığında artık örtülü olarak çağrılmaz. Bir birlik U'nun, yıkıcısı olan s adlı bir yapı olan bir üye içeren anonim bir yapı içerdiği aşağıdaki kodu göz önünde bulundurun.

   ```cpp
    #include <stdio.h>
    struct S {
        S() { printf("Creating S\n"); }
        ~S(){ printf("Destroying S\n"); }
    };
    union U {
        struct {
        S s;
    };
        U() {}
        ~U(){}
    };

    void f()
    {
        U u;
        // Destructor implicitly called here.
    }

    int main()
    {
        f();

        char s[1024];
        printf("Press any key.\n");
        gets_s(s);
        return 0;
    }
   ```

   Visual Studio 2013'te, birliktelik oluşturulduğunda S'nin oluşturucusu çağrılır ve işlev f yığını temizlendiğinde S için yıkıcı çağrılır. Ancak Visual Studio 2015'te yapıcı ve yıkıcı denmez. Derleyici bu davranış değişikliği hakkında bir uyarı verir.

   ```Output
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called
   ```

   Özgün davranışı geri yüklemek için anonim yapıya bir ad verin. Anonim olmayan yapıların çalışma zamanı davranışı, derleyici sürümünden bağımsız olarak aynıdır.

   ```cpp
    #include <stdio.h>

    struct S {
        S() { printf("Creating S.\n"); }
        ~S() { printf("Destroying S\n"); }
    };
    union U {
        struct {
            S s;
        } namedStruct;
        U() {}
        ~U() {}
    };

    void f()
    {
        U u;
    }

    int main()
    {
        f();

        char s[1024];
        printf("Press any key.\n");
        gets_s(s);
        return 0;
    }
   ```

   Alternatif olarak, oluşturucu ve yıkıcı kodu yeni işlevlere taşımayı deneyin ve bu işlevlere birleşim için oluşturucu ve yıkıcıdan çağrılar ekleyin.

   ```cpp
    #include <stdio.h>

    struct S {
        void Create() { printf("Creating S.\n"); }
        void Destroy() { printf("Destroying S\n"); }
    };
    union U {
        struct {
            S s;
        };
        U() { s.Create();  }
        ~U() { s.Destroy(); }
    };

    void f()
    {
        U u;
    }

    int main()
    {
        f();

    char s[1024];
    printf("Press any key.\n");
    gets_s(s);
    return 0;
    }
   ```

- **Şablon çözünürlüğü**

   Şablonlar için ad çözümlemesi için değişiklikler yapıldı. C++'da, bir ismin çözümü için adayları değerlendirirken, olası eşleşmeler olarak düşünülen bir veya daha fazla ad geçersiz bir şablon anlık oluşturma sağlar. Bu geçersiz anlık hatalar normalde derleyici hatalarına neden olmaz, SFINAE (Değiştirme Hatası Hata Değildir) olarak bilinen bir ilkedir.

   Şimdi, SFINAE derleyicinin bir sınıf şablonunun uzmanlığını anında ani hale getirilmesini gerektiriyorsa, bu işlem sırasında oluşan hatalar derleyici hatalarıdır. Önceki sürümlerde, derleyici bu tür hataları yoksardı. Örneğin, aşağıdaki kodu göz önünde bulundurun:

   ```cpp
    #include <type_traits>

    template<typename T>
    struct S
    {
    S() = default;
    S(const S&);
    S(S&&);

    template<typename U, typename = typename std::enable_if<std::is_base_of<T, U>::value>::type>
    S(S<U>&&);
    };

    struct D;

    void f1()
    {
    S<D> s1;
        S<D> s2(s1);
    }

    struct B
    {
    };

    struct D : public B
    {
    };

    void f2()
    {
    S<D> s1;
        S<D> s2(s1);
    }
   ```

   Geçerli derleyiciyle derlerseniz, aşağıdaki hatayı alırsınız:

   ```Output
    type_traits(1110): error C2139: 'D': an undefined class is not allowed as an argument to compiler intrinsic type trait '__is_base_of'
    ..\t331.cpp(14): note: see declaration of 'D'
    ..\t331.cpp(10): note: see reference to class template instantiation 'std::is_base_of<T,U>' being compiled
            with
            [
                T=D,
                U=D
            ]
   ```

   Bunun nedeni, is_base_of'in ilk çağrılması noktasında 'D' sınıfının henüz tanımlanmamış olmasıdır.

   Bu durumda, düzeltme sınıf tanımlanana kadar bu tür özellikleri kullanmak değildir. B ve D tanımlarını kod dosyasının başına taşırsanız, hata çözülür. Tanımlar üstbilgi dosyalarındaysa, sorunlu şablonlar kullanılmadan önce sınıf tanımlarının derlenmiş olduğundan emin olmak için üstbilgi dosyalarıiçin ekstrelerin sırasını denetleyin.

- **Kopya yapıcılar**

   Hem Visual Studio 2013 hem de Visual Studio 2015'te derleyici, bu sınıfın kullanıcı tanımlı bir hareket oluşturucusu varsa ancak kullanıcı tanımlı kopya oluşturucusu yoksa bir sınıf için bir kopya oluşturucu oluşturur. Dev14'te, bu örtülü olarak oluşturulan kopya oluşturucusu da "= delete" olarak işaretlenir.

### <a name="conformance-improvements-in-visual-studio-2015-update-1"></a><a name="VS_Update1"></a>Visual Studio 2015 Güncelleme 1'de Uygunluk Geliştirmeleri

- **Özel sanal temel sınıflar ve dolaylı kalıtım**

   Derleyicinin önceki sürümleri, türetilmiş bir sınıfın dolaylı olarak türetilmiş taban sınıflarının üye işlevlerini aramasına izin *veremiş.* `private virtual` Bu eski davranış yanlıştı ve C++ standardına uymuyor. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve sonuç olarak derleyici hatası C2280'i sorun.

   ```Output
    error C2280: 'void *S3::__delDtor(unsigned int)': attempting to reference a deleted function
   ```

   Örnek (daha önce)

   ```cpp
    class base
    {
    protected:
        base();
        ~base();
    };

    class middle: private virtual base {};class top: public virtual middle {};

    void destroy(top *p)
    {
        delete p;  //
    }
   ```

   Örnek (sonra)

   ```cpp
    class base;  // as above

    class middle: protected virtual base {};
    class top: public virtual middle {};

    void destroy(top *p)
    {
        delete p;
    }
   ```

  \-veya-

   ```cpp
    class base;  // as above

    class middle: private virtual base {};
    class top: public virtual middle, private virtual bottom {};

    void destroy(top *p)
    {
        delete p;
    }
   ```

- **Aşırı yüklenmiş operatör yeni ve operatör silme**

   Derleyicinin önceki sürümleri, üye olmayan **operatör silmenin** statik olarak bildirilmesine ve genel ad alanı dışındaki ad alanlarında beyan edilmesine olanak sağladı. **operator delete**  Bu eski davranış, programın programcının amaçladığı **yeni** veya silme operatör uygulamasını aramaması veya **silmemesi** riski oluşturarak sessiz kötü çalışma zamanı davranışına neden oldu. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve bunun yerine derleyici hatası C2323 sorunları.

   ```Output
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace.
   ```

   Örnek (daha önce)

   ```cpp
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323
   ```

   Örnek (sonra)

   ```cpp
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'
   ```

   Ayrıca, derleyici belirli bir tanı vermese de, satır içi işleç yeni kötü biçimli olarak kabul edilir.

- **Derleyicinin sınıf dışı türlerde 'işleç *türü*()' (kullanıcı tanımlı dönüştürme) çağrısı,** 'operatör türü ()' olarak adlandırılmasına izin verirken, sessizce yok sayılması yla 'işleç *türü*()' çağrılmasına izin verilmiştir. Bu eski davranış, öngörülemeyen çalışma zamanı davranışıile sonuçlanan sessiz kötü kod oluşturma riski yarattı. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve bunun yerine derleyici hatası C2228 sorunları.

   ```Output
    error C2228: left of '.operator type' must have class/struct/union
   ```

   Örnek (daha önce)

   ```cpp
    typedef int index_t;

    void bounds_check(index_t index);

    void login(int column)
    {
        bounds_check(column.operator index_t());  // error C2228
    }
   ```

   Örnek (sonra)

   ```cpp
    typedef int index_t;

    void bounds_check(index_t index);

    void login(int column)
    {
         bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'
    }
   ```

- **Ayrıntılı tür belirteciler içinde gereksiz yazı adı**  Derleyicinin önceki sürümleri ayrıntılı bir tür belirteci **nde yazı adı** izin verdi; bu şekilde yazılan kod anlamsal olarak yanlıştır. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve bunun yerine derleyici hatası C3406'yı sorun.

   ```Output
    error C3406: 'typename' cannot be used in an elaborated type specifier
   ```

   Örnek (daha önce)

   ```cpp
    template <typename class T>
    class container;
   ```

   Örnek (sonra)

   ```cpp
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case
    class container;
   ```

- **Bir baş harf listesinden dizilerin dizilerin tümdengelimi yazma**  Derleyicinin önceki sürümleri, bir baş harf listesinden dizilerin tür tümdengelimini desteklemedi. Derleyici şimdi bu tür tümdengelimi biçimini destekler ve sonuç olarak, baş harflistelerini kullanarak işlev şablonlarına yapılan çağrılar artık belirsiz olabilir veya derleyicinin önceki sürümlerinden farklı bir aşırı yükleme seçilebilir. Bu sorunları gidermek için, programın artık programcının amaçladığı aşırı yükü açıkça belirtmesi gerekir.

   Bu yeni davranış, aşırı yük çözümlemesi, tarihi aday kadar iyi olan ek bir adayı dikkate almaya neden olduğunda, çağrı belirsizhale gelir ve derleyici sorunları derleme hatası C2668 sonucu olarak.

   ```Output
    error C2668: 'function' : ambiguous call to overloaded function.
   ```

   Örnek 1: Aşırı yüklü işleve belirsiz çağrı (önce)

   ```cpp
    // In previous versions of the compiler, code written in this way would unambiguously call f(int, Args...)
    template <typename... Args>
    void f(int, Args...);  //

    template <int N, typename... Args>
    void f(const int (&)[N], Args...);

    int main()
    {
        // The compiler now considers this call ambiguous, and issues a compiler error
        f({3});  error C2668: 'f' ambiguous call to overloaded function
    }
   ```

   Örnek 1: aşırı yüklü işleve belirsiz çağrı (sonra)

   ```cpp
    template <typename... Args>
    void f(int, Args...);  //

    template <int N, typename... Args>
    void f(const int (&)[N], Args...);

    int main()
    {
        // To call f(int, Args...) when there is just one expression in the initializer list, remove the braces from it.
        f(3);
    }
   ```

   Bu yeni davranış, aşırı yükleme çözümlemesi, tarihi adaydan daha iyi eşleşen ek bir adayı dikkate almaya neden olduğunda, çağrı yeni adaya açık bir şekilde çözümlenir ve programcının amaçladığından büyük olasılıkla farklı olan program davranışında bir değişikliğe neden olur.

   Örnek 2: aşırı yük çözünürlüğünde değişiklik (önce)

   ```cpp
    // In previous versions of the compiler, code written in this way would unambiguously call f(S, Args...)
    struct S
    {
        int i;
        int j;
    };

    template <typename... Args>
    void f(S, Args...);

    template <int N, typename... Args>
    void f(const int *&)[N], Args...);

    int main()
    {
        // The compiler now resolves this call to f(const int (&)[N], Args...) instead
        f({1, 2});
    }
   ```

   Örnek 2: aşırı yük çözünürlüğünde değişiklik (sonra)

   ```cpp
    struct S;  // as before

    template <typename... Args>
    void f(S, Args...);

    template <int N, typename... Args>
    void f(const int *&)[N], Args...);

    int main()
    {
        // To call f(S, Args...), perform an explicit cast to S on the initializer list.
        f(S{1, 2});
    }
   ```

- **Anahtar bildirimi uyarılarının restorasyonu**

   Derleyicinin önceki **sürümü, anahtar** ifadeleriyle ilgili daha önce varolan uyarıları kaldırmış; bu uyarılar artık geri yüklendi. Derleyici artık geri yüklenen uyarıları yayınlar ve belirli servis talepleriyle ilgili uyarılar (varsayılan durum dahil) artık anahtar deyiminin son satırıyerine kusurlu örneği içeren satırda verilir. Bu uyarıların geçmişteolduğundan farklı satırlarda verilmesisonucunda, daha önce kullanılarak `#pragma warning(disable:####)` bastırılan uyarılar artık beklendiği gibi bastırılamayabilir. Bu uyarıları beklendiği gibi bastırmak için, yönergeyi `#pragma warning(disable:####)` ilk olası kusurlu durumun üzerinde bir satıra taşımak gerekebilir. Geri yüklenen uyarılar aşağıda veda edileb'dir.

   ```Output
    warning C4060: switch statement contains no 'case' or 'default' labels
   ```

   ```Output
    warning C4061: enumerator 'bit1' in switch of enum 'flags' is not explicitly handled by a case label
   ```

   ```Output
    warning C4062: enumerator 'bit1' in switch of enum 'flags' is not handled
   ```

   ```Output
    warning C4063: case 'bit32' is not a valid value for switch of enum 'flags'
   ```

   ```Output
    warning C4064: switch of incomplete enum 'flags'
   ```

   ```Output
    warning C4065: switch statement contains 'default' but no 'case' labels
   ```

   ```Output
    warning C4808: case 'value' is not a valid value for switch condition of type 'bool'
   ```

   ```Output
    Warning C4809: switch statement has redundant 'default' label; all possible 'case' labels are given
   ```

   C4063 örneği (daha önce)

   ```cpp
    class settings
    {
    public:
        enum flags
        {
            bit0 = 0x1,
            bit1 = 0x2,
            ...
        };
        ...
    };

    int main()
    {
        auto val = settings::bit1;

        switch (val)
        {
        case settings::bit0:
            break;

        case settings::bit1:
            break;

        case settings::bit0 | settings::bit1:  // warning C4063
            break;
        }
    };
   ```

   C4063 örneği (sonra)

   ```cpp
    class settings {...};  // as above

    int main()
    {
        // since C++11, use std::underlying_type to determine the underlying type of an enum
        typedef std::underlying_type<settings::flags>::type flags_t;

        auto val = settings::bit1;

        switch (static_cast<flags_t>(val))
        {
        case settings::bit0:
            break;

        case settings::bit1:
            break;

        case settings::bit0 | settings::bit1:  // ok
            break;
        }
    };
   ```

   Geri yüklenen diğer uyarılara örnekler belgelerinde verilmiştir.

- **#include: yol adında '..' üst dizin belirtici** nin `/Wall` `/WX`kullanımı (yalnızca etkiler)

   Derleyicinin önceki sürümlerinde üst dizin belirtici '..' kullanımını algılamadı. direktiflerin `#include` yol adında. Bu şekilde yazılan kod genellikle proje göreli yolları yanlış kullanarak proje dışında var olan üstbilgi eklemek için tasarlanmıştır. Bu eski davranış, programın programcının amaçladığından farklı bir kaynak dosyası ekleyerek derlenebileceği veya bu göreli yolların diğer yapı ortamlarına taşınabilir olmaması riski oluşturmıştır. Derleyici şimdi bu şekilde yazılmış kodun programcısını algılar ve uyarır ve etkinleştirilirse isteğe bağlı derleyici uyarısı C4464'ü yayınlar.

   ```Output
    warning C4464: relative include path contains '..'
   ```

   Örnek (daha önce)

   ```cpp
    #include "..\headers\C4426.h"  // emits warning C4464
   ```

   Örnek (sonra)

   ```cpp
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories
   ```

   Ayrıca, derleyici belirli bir tanılama vermese de, projenizin dahil dizinlerini belirtmek için üst dizin belirtici ".." notun kullanılmasını da öneririz.

- **#pragma en iyi duruma getirme() üstbilgi dosyasının son ucunu genişletir** (yalnızca etkiler) `/Wall` `/WX`

   Derleyicinin önceki sürümlerinde, çeviri birimi içinde bulunan bir üstbilgi dosyasından kaçan en iyi duruma getirilmesi bayrak ayarlarında yapılan değişiklikler algılanmadı. Derleyici şimdi bu şekilde yazılmış kodun programcısını algılar ve uyarır ve `#include`etkinse, rahatsız ın bulunduğu yerde isteğe bağlı bir derleyici uyarısı C4426 yayınlar. Bu uyarı, yalnızca değişiklikler derlemeye komut satırı bağımsız değişkenleri tarafından ayarlanan en iyi duruma getirilmesi bayraklarıyla çakışacaksa verilir.

   ```Output
    warning C4426: optimization flags changed after including header, may be due to #pragma optimize()
   ```

   Örnek (daha önce)

   ```cpp
    // C4426.h
    #pragma optimize("g", off)
    ...
    // C4426.h ends

    // C4426.cpp
    #include "C4426.h"  // warning C4426
   ```

   Örnek (sonra)

   ```cpp
    // C4426.h
    #pragma optimize("g", off)
    ...
    #pragma optimize("", on)  // restores optimization flags set via command-line arguments
    // C4426.h ends

    // C4426.cpp
    #include "C4426.h"
   ```

- **Uyumsuz #pragma uyarı(itme)** ve **#pragma uyarı(pop)** (yalnızca etkiler) `/Wall` `/WX`

   Derleyicinin önceki sürümleri, `#pragma warning(push)` nadiren amaçlanan `#pragma warning(pop)` farklı bir kaynak dosyadaki durum değişiklikleriyle eşleştirilmiş durum değişikliklerini algılamadı. Bu eski davranış, programın programcının amaçladığından farklı bir uyarı kümesiyle derlenme riski oluşturarak, büyük olasılıkla sessiz kötü çalışma zamanı davranışıyla sonuçlanmıştır. Derleyici şimdi bu şekilde yazılmış kodun programcısını algılar ve uyarır ve etkinse, eşleşen `#pragma warning(pop)`konumda isteğe bağlı derleyici uyarısı C5031'i yayınlar. Bu uyarı, ilgili `#pragma warning(push)`konumuna atıfta bulunan bir not içerir.

   ```Output
    warning C5031: #pragma warning(pop): likely mismatch, popping warning state pushed in different file
   ```

   Örnek (daha önce)

   ```cpp
    // C5031_part1.h
    #pragma warning(push)
    #pragma warning(disable:####)
    ...
    // C5031_part1.h ends without #pragma warning(pop)

    // C5031_part2.h
    ...
    #pragma warning(pop)  // pops a warning state not pushed in this source file
    ...
    // C5031_part1.h ends

    // C5031.cpp
    #include "C5031_part1.h" // leaves #pragma warning(push) 'dangling'
    ...
    #include "C5031_part2.h" // matches 'dangling' #pragma warning(push), resulting in warning C5031
    ...
   ```

   Örnek (sonra)

   ```cpp
    // C5031_part1.h
    #pragma warning(push)
    #pragma warning(disable:####)
    ...
    #pragma warning(pop)  // pops the warning state pushed in this source file
    // C5031_part1.h ends without #pragma warning(pop)

    // C5031_part2.h
    #pragma warning(push)  // pushes the warning state pushed in this source file
    #pragma warning(disable:####)
    ...
    #pragma warning(pop)
    // C5031_part1.h ends

    // C5031.cpp
    #include "C5031_part1.h" // #pragma warning state changes are self-contained and independent of other source files or their #include order.
    ...
    #include "C5031_part2.h"
    ...
   ```

   Nadir olsa da, bu şekilde yazılmış kod bazen kasıtlı. Bu şekilde yazılan kod, sıralı `#include` değişikliklere karşı hassastır; mümkün olduğunda, kaynak kod dosyalarının uyarı durumunu bağımsız bir şekilde yönetmesini öneririz.

- **Eşleşmemiş #pragma uyarı(push)** (yalnızca etkiler) `/Wall` `/WX`

   Derleyicinin önceki sürümleri, çeviri biriminin sonunda eşleşmemiş `#pragma warning(push)` durum değişikliklerini algılamadı. Derleyici şimdi bu şekilde yazılmış kodun programcısını algılar ve uyarır ve etkinleştirilirse, eşleşmeyen `#pragma warning(push)`konumda isteğe bağlı bir derleyici uyarısı C5032 yayınlar. Bu uyarı yalnızca çeviri biriminde derleme hatası yoksa verilir.

   ```Output
    warning C5032: detected #pragma warning(push) with no corresponding #pragma warning(pop)
   ```

   Örnek (daha önce)

   ```cpp
    // C5032.h
    #pragma warning(push)
    #pragma warning(disable:####)
    ...
    // C5032.h ends without #pragma warning(pop)

    // C5032.cpp
    #include "C5032.h"
    ...
    // C5032.cpp ends -- the translation unit is completed without #pragma warning(pop), resulting in warning C5032 on line 1 of C5032.h
   ```

   Örnek (sonra)

   ```cpp
    // C5032.h
    #pragma warning(push)
    #pragma warning(disable:####)
    ...
    #pragma warning(pop) // matches #pragma warning (push) on line 1
    // C5032.h ends

    // C5032.cpp
    #include "C5032.h"
    ...
    // C5032.cpp ends -- the translation unit is completed without unmatched #pragma warning(push)
   ```

- **Geliştirilmiş #pragma uyarı durumu izleme sonucunda ek uyarılar verilebilir**

   Derleyicinin önceki sürümleri, `#pragma warning` istenen tüm uyarıları vermek için yeterli şekilde iyi bir şekilde yapılan durum değişiklikleridir. Bu davranış, programcının amaçladığından farklı durumlarda belirli uyarıların etkili bir şekilde bastırılması riski oluşturmıştır. Derleyici artık `#pragma warning` durumu daha sağlam bir `#pragma warning` şekilde izler - özellikle şablonların içindeki durum değişiklikleriyle ilgilidir - ve isteğe bağlı olarak programcının `#pragma warning(push)` istenmeyen kullanımları bulmasına yardımcı olmak amacıyla C5031 ve C5032'ye yeni uyarılar `#pragma warning(pop)`yayınlar.

   Durum değişikliği izlemenin iyileştirilmesi `#pragma warning` sonucunda, eskiden yanlış bastırılmış uyarılar veya daha önce yanlış tanı konulan sorunlarla ilgili uyarılar şimdi verilebilir.

- **Erişilemeyen kodun geliştirilmiş tanımlaması**

   C++ Standart Kitaplığı değişiklikleri ve derleyicinin önceki sürümlerinde işlev çağrılarının satır arayla yükseltilebilmesi, derleyicinin belirli kodun artık erişilemez olduğunu kanıtlamasına olanak sağlayabilir. Bu yeni davranış, c4720 uyarı yeni ve daha sık verilen örnekleri neden olabilir.

   ```Output
    warning C4720: unreachable code
   ```

   Çoğu durumda, bu uyarı yalnızca etkin leştirilmiş en iyi duruma getirimle derlendiğinde verilebilir, çünkü optimizasyonlar daha fazla işlev çağrısı nı sıralayabilir, gereksiz kodu ortadan kaldırabilir veya belirli kodun erişilemez olduğunu belirlemeyi mümkün kılabilir. C4720'nin yeni uyarı örneklerinin özellikle std kullanımı ile ilgili olarak **try/catch** bloklarında sık sık meydana geldiğini [gözlemledik::bul](../standard-library/algorithm-functions.md#find).

   Örnek (daha önce)

   ```cpp
    try
    {
        auto iter = std::find(v.begin(), v.end(), 5);
    }
    catch(...)
    {
        do_something();  // ok
    }
   ```

   Örnek (sonra)

   ```cpp
    try
    {
        auto iter = std::find(v.begin(), v.end(), 5);
    }
    catch(...)
    {
        do_something();  // warning C4702: unreachable code
    }
   ```

### <a name="conformance-improvements-in-visual-studio-2015-update-2"></a><a name="VS_Update2"></a>Visual Studio 2015 Güncelleme 2'de Uygunluk Geliştirmeleri

- **Ek uyarılar ve hatalar ifade SFINAE için kısmi destek sonucu verilebilir**

   Derleyicinin önceki sürümleri, SFINAE ifadesi için destek olmaması nedeniyle **decltype** belirteçleri içindeki belirli türde ifadeleri ayrışturmadı. Bu eski davranış yanlıştı ve C++ standardına uymuyor. Derleyici şimdi bu ifadeleri ayrıştırır ve devam eden uygunluk iyileştirmeleri nedeniyle SFINAE ifadesi için kısmi destek vardır. Sonuç olarak, derleyici şimdi derleyicinin önceki sürümleriayrıştur olmadığını ifadelerde bulunan uyarılar ve hatalar sorunları.

   Bu yeni davranış, henüz bildirilmemiş bir tür içeren bir **decltype** ifadesini ayrışturduğunda, derleyici hatasını bir sonucu olarak C2039 olarak dağır.

   ```Output
    error C2039: 'type': is not a member of '`global namespace''
   ```

   Örnek 1: bildirilmemiş bir tür (daha önce) kullanımı

   ```cpp
    struct s1
    {
      template <typename T>
      auto f() -> decltype(s2<T>::type::f());  // error C2039

      template<typename>
      struct s2 {};
    }
   ```

   Örnek 1 (sonra)

   ```cpp
    struct s1
    {
      template <typename>  // forward declare s2struct s2;

      template <typename T>
      auto f() -> decltype(s2<T>::type::f());

      template<typename>
      struct s2 {};
    }
   ```

   Bu yeni davranış, bağımlı bir ad bir tür olduğunu belirtmek için **daktiladı** anahtar sözcüğünün gerekli bir kullanımı eksik bir **decltype** ifade parsese, derleyici uyarı C4346 derleyici hatası C2923 ile birlikte sorunları.

   ```Output
    warning C4346: 'S2<T>::Type': dependent name is not a type
   ```

   ```Output
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'
   ```

   Örnek 2: bağımlı ad bir tür değildir (önce)

   ```cpp
    template <typename T>
    struct s1
    {
      typedef T type;
    };

    template <typename T>
    struct s2
    {
      typedef T type;
    };

    template <typename T>
    T declval();

    struct s
    {
      template <typename T>
      auto f(T t) -> decltype(t(declval<S1<S2<T>::type>::type>()));  // warning C4346, error C2923
    };
   ```

   Örnek 2 (sonra)

   ```cpp
    template <typename T> struct s1 {...};  // as above
    template <typename T> struct s2 {...};  // as above

    template <typename T>
    T declval();

    struct s
    {
      template <typename T>
      auto f(T t) -> decltype(t(declval<S1<typename S2<T>::type>::type>()));
    };
   ```

- `volatile`**üye değişkenler örtülü olarak tanımlanmış yapıcıları ve atama işleçlerini önler** Derleyicinin önceki sürümleri, **geçici** üye değişkenleri olan bir sınıfın varsayılan kopya/taşıma oluşturucularına ve varsayılan kopyalama/taşıma atama işleçlerinin otomatik olarak oluşturulmasına izin verdi. Bu eski davranış yanlıştı ve C++ standardına uymuyor. Derleyici artık geçici üye değişkenleri olan bir sınıfı, bu işleçlerin varsayılan uygulamalarının otomatik olarak oluşturulmasını engelleyen önemsiz olmayan yapı ve atama işleçleri olmasını dikkate alır. Böyle bir sınıf bir birliğin (veya sınıfın içindeki anonim bir birliğin) üyesi olduğunda, birleşimin kopyalanması/taşınması ve kopyalama/taşıma atama işleçleri (veya unonymous birliği içeren sınıf) dolaylı olarak silinmiş olarak tanımlanır. Açıkça tanımlamadan birleşim (veya anonim birliği içeren sınıf) oluşturmaya veya kopyalamaya çalışmak bir hatadır ve derleyici hatası C2280'i bir sonucu olarak sorun.

   ```Output
    error C2280: 'B::B(const B &)': attempting to reference a deleted function
   ```

   Örnek (daha önce)

   ```cpp
    struct A
    {
      volatile int i;
      volatile int j;
    };

    extern A* pa;

    struct B
    {
      union
      {
        A a;
        int i;
      };
    };

    B b1 {*pa};
    B b2 (b1);  // error C2280
   ```

   Örnek (sonra)

   ```cpp
    struct A
    {
      int i;int j;
    };

    extern volatile A* pa;

    A getA()  // returns an A instance copied from contents of pa
    {
      A a;
      a.i = pa->i;
      a.j = pa->j;
      return a;
    }

    struct B;  // as above

    B b1 {GetA()};
    B b2 (b1);  // error C2280
   ```

- **Statik üye işlevler cv-qualifiers desteklemez.**

   Visual C++ 2015'in önceki sürümleristatik üye işlevlerin cv elemelerine sahip olmasını sağladı. Bu davranış, Visual C++ 2015 ve Visual C++ 2015 Update 1'deki bir gerilemeden kaynaklanmaktadır; Visual C++ 2013 ve Visual C++'ın önceki sürümleri bu şekilde yazılmış kodu reddeder. Visual C++ 2015 ve Visual C++ 2015 Update 1'in davranışı yanlıştır ve C++ standardına uymuyor.  Visual Studio 2015 Update 2 bu şekilde yazılmış kodu reddeder ve bunun yerine derleyici hatası C2511 sorunları.

   ```Output
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'
   ```

   Örnek (daha önce)

   ```cpp
    struct A
    {
      static void func();
    };

    void A::func() const {}  // C2511
   ```

   Örnek (sonra)

   ```cpp
    struct A
    {
      static void func();
    };

    void A::func() {}  // removed const
   ```

- **WinRT kodunda enum'un forward bildirimine izin verilmez** (yalnızca etkiler) `/ZW`

   Windows Runtime (WinRT) için derlenen kod, `/clr` derleyici anahtarı nı kullanarak .Net Framework için yönetilen C++ kodunun derlendiğinde olduğu gibi, **enum** türlerinin iledilmesine izin vermez. Bu davranış, numaralandırmaboyutunun her zaman bilinmesini ve WinRT türü sistemine doğru şekilde yansıtılmasını sağlar. Derleyici bu şekilde yazılmış kodu reddeder ve derleyici hatası C2599'u derleyici hatası C3197 ile birlikte soruna neden eder.

   ```Output
    error C2599: 'CustomEnum': the forward declaration of a WinRT enum is not allowed
   ```

   ```Output
    error C3197: 'public': can only be used in definitions
   ```

   Örnek (daha önce)

   ```cpp
    namespace A {
      public enum class CustomEnum: int32;  // forward declaration; error C2599, error C3197
    }

    namespace A {
      public enum class CustomEnum: int32
      {
        Value1
      };
    }

    public ref class Component sealed
    {
    public:
      CustomEnum f()
      {
        return CustomEnum::Value1;
      }
    };
   ```

   Örnek (sonra)

   ```cpp
              // forward declaration of CustomEnum removed
    namespace A {
      public enum class CustomEnum: int32
      {
        Value1
      };
    }

    public ref class Component sealed
    {
    public:
      CustomEnum f()
      {
        return CustomEnum::Value1;
      }
    };
   ```

- **Aşırı yüklenen üye olmayan operatör yeni ve operatör silme satır içi olarak ilan edilemez** (Düzey 1 (`/W1`) on-by-default)

   Derleyicinin önceki sürümleri, üye olmayan operatör **yeni** ve **operatör silme** işlevleri satır içi olarak beyan edildiğinde bir uyarı yayınlamaz. Bu şekilde yazılan kod kötü biçimlendirilmiştir (tanı lama gerektirmez) ve uyumsuz yeni ve silme işleçlerinden kaynaklanan bellek sorunlarına neden olabilir (özellikle boyutlandırmayla birlikte kullanıldığında) tanılanması zor olabilir. Derleyici şimdi derleyici uyarı C4595 bu şekilde yazılmış kodu belirlemeye yardımcı olmak için sorunları.

   ```Output
    warning C4595: 'operator new': non-member operator new or delete functions may not be declared inline
   ```

   Örnek (daha önce)

   ```cpp
    inline void* operator new(size_t sz)  // warning C4595
    {
      ...
    }
   ```

   Örnek (sonra)

   ```cpp
    void* operator new(size_t sz)  // removed inline
    {
      ...
    }
   ```

   Bu şekilde yazılmış kodun düzeltilmesi, işleç tanımlarının üstbilgi dosyasından ve ilgili kaynak dosyasına taşınmasını gerektirebilir.

### <a name="conformance-improvements-in-visual-studio-2015-update-3"></a><a name="VS_Update3"></a>Visual Studio 2015 Güncelleme 3'te Uygunluk Geliştirmeleri

- **std::is_convertable şimdi kendi kendine atama** algılar (standart `std::is_convertable` kitaplık) Tür-özellik önceki sürümleri doğru kopya oluşturucu veya özel bir sınıf türü kendi kendine atama algılamadı. Şimdi, `std::is_convertable<>::value` silinmiş veya özel kopya oluşturucu ile bir sınıf türüne **uygulandığında** doğru false olarak ayarlanır.

   Bu değişiklikle ilişkili derleyici tanılama yoktur.

   Örnek

   ```cpp
    #include <type_traits>

    class X1
    {
    public:
        X1(const X1&) = delete;
    };

    class X2
    {
    private:
        X2(const X2&);
    };

    static_assert(std::is_convertible<X1&, X1>::value, "BOOM");static_assert(std::is_convertible<X2&, X2>::value, "BOOM");
   ```

   Visual C++'ın önceki sürümlerinde, bu örneğin altındaki statik `std::is_convertable<>::value` bağımsız lamalar yanlış **olarak doğru**olarak ayarlandığı için geçer. Şimdi, `std::is_convertable<>::value` doğru **yanlış**olarak ayarlanır , statik iddiaları başarısız neden.

- **Varsayılan veya silinmiş önemsiz kopyalama ve taşıma oluşturucular erişim belirticilerine saygı**

   Derleyicinin önceki sürümleri, varsayılan veya silinen önemsiz kopyanın erişim belirteçlerini denetlemedi ve çağrılmasını izin vermeden önce oluşturucuları taşıdı. Bu eski davranış yanlıştı ve C++ standardına uymuyor. Bazı durumlarda, bu eski davranış sessiz kötü kod oluşturma riski yaratarak öngörülemeyen çalışma zamanı davranışıyla sonuçlanır. Derleyici şimdi varsayılan veya silinen önemsiz kopyanın erişim belirticini denetler ve çağrılan ve değilse, sonuç olarak derleyici uyarısı C2248'i sorunlayıp çözemeyeceğini belirlemek için oluşturucuları taşır.

   ```Output
    error C2248: 'S::S' cannot access private member declared in class 'S'
   ```

   Örnek (daha önce)

   ```cpp
    class S {
    public:
       S() = default;
    private:
        S(const S&) = default;
    };

    void f(S);  // pass S by value

    int main()
    {
        S s;
        f(s);  // error C2248, can't invoke private copy constructor
    }
   ```

   Örnek (sonra)

   ```cpp
    class S {
    public:
       S() = default;
    private:
        S(const S&) = default;
    };

    void f(const S&);  // pass S by reference

    int main()
    {
        S s;
        f(s);
    }
   ```

- **Atfedilen ATL kod desteğinin amortismanı** (Düzey 1 (`/W1`) varsayılan olarak)

   Derleyicinin önceki sürümleri desteklenen ATL kodu atfedilen. [Visual C++ 2008'de başlayan](#whats-new-for-c-in-visual-studio-2008)atfedilen ATL kodu için desteği kaldırmanın bir sonraki aşaması olarak, ATL kodu amortismana kaldırıldı. Derleyici şimdi derleyici uyarı C4467 bu tür amortismanlı kodu belirlemeye yardımcı olmak için sorunları.

   ```Output
    warning C4467: Usage of ATL attributes is deprecated
   ```

   Destek derleyiciden kaldırılana kadar atfedilen ATL kodunu kullanmaya devam etmek istiyorsanız, `/Wv:18` derleyiciye veya `/wd4467` komut satırı bağımsız `#pragma warning(disable:4467)` değişkenlerini geçirerek veya kaynak kodunuza ekleyerek bu uyarıyı devre dışı kullanabilirsiniz.

   Örnek 1 (önce)

   ```cpp
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
    class A {};
   ```

   Örnek 1 (sonra)

   ```cpp
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};
   ```

   Bazen aşağıdaki örnek kodda olduğu gibi, amortismana nalan ATL özniteliklerinin kullanılmasını önlemek için bir IDL dosyasına ihtiyaç duyabilir veya oluşturmak isteyebilirsiniz

   Örnek 2 (önce)

   ```cpp
    [emitidl];
    [module(name="Foo")];

    [object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
    __interface ICustom {
        HRESULT Custom([in] long l, [out, retval] long *pLong);
        [local] HRESULT CustomLocal([in] long l, [out, retval] long *pLong);
    };

    [coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
    class CFoo : public ICustom
    {
        // ...
    };
   ```

   İlk olarak, *.idl dosyasını oluşturun; vc140.idl oluşturulan dosya arayüzleri ve \*ek açıklamaları içeren bir .idl dosyası elde etmek için kullanılabilir.

   Ardından, C++ arabirim tanımlarının oluşturulduğundan emin olmak için yapınıza bir MIDL adımı ekleyin.

   Örnek 2 IDL (sonra)

   ```cpp
    import "docobj.idl";

    [
        object,local,uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)
    ]

    interface ICustom : IUnknown {
        HRESULT  Custom([in] long l, [out,retval] long *pLong);
        [local] HRESULT  CustomLocal([in] long l, [out,retval] long *pLong);
    };

    [ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]
    library Foo
    {
        importlib("stdole2.tlb");
        importlib("olepro32.dll");
            [
                version(1.0),
                appobject,uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)
            ]

        coclass CFoo {
            interface ICustom;
        };
    }
   ```

   Ardından, aşağıdaki örnek kodda olduğu gibi ATL'yi doğrudan uygulama dosyasında kullanın.

   Örnek 2 Uygulama (sonra)

   ```cpp
    #include <idl.header.h>
    #include <atlbase.h>

    class ATL_NO_VTABLE CFooImpl :
        public ICustom,
        public ATL::CComObjectRootEx<CComMultiThreadModel>
    {
    public:
        BEGIN_COM_MAP(CFooImpl)
        COM_INTERFACE_ENTRY(ICustom)
        END_COM_MAP()
    };
   ```

- **Önceden derlenmiş üstbilgi (PCH) dosyaları ve eşleşmemiş** #include `/Wall` `/WX`yönergeleri (yalnızca etkiler)

   Derleyicinin önceki sürümleri, önceden derlenmiş üstbilgi (PCH) dosyaları kullanırken kaynak dosyalar ile `#include` `-Yc` `-Yu` derlemeler arasındaki uyumsuz yönergeleri kabul etti. Bu şekilde yazılan kod artık derleyici tarafından kabul edilmez. Derleyici şimdi PCH dosyalarını kullanırken uyumsuz `#include` yönergeleri belirlemeye yardımcı olmak için derleyici uyarı CC4598 sorunları.

   ```Output
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position
   ```

   Örnek (önce):

   X.cpp (-Ycc.h)

   ```cpp
    #include "a.h"
    #include "b.h"
    #include "c.h"
   ```

   Z.cpp (-Yuc.h)

   ```cpp
    #include "b.h"
    #include "a.h"  // mismatched order relative to X.cpp
    #include "c.h"
   ```

   Örnek (sonra)

   X.cpp (-Ycc.h)

   ```cpp
    #include "a.h"
    #include "b.h"
    #include "c.h"
   ```

   Z.cpp (-Yuc.h)

   ```cpp
    #include "a.h"
    #include "b.h" // matched order relative to X.cpp
    #include "c.h"
   ```

- **Önceden derlenmiş üstbilgi (PCH) dosyaları ve eşleşmemiş dizinler içerir** (yalnızca etkiler) `/Wall` `/WX`

   Derleyicinin kabul edilen önceki sürümleri, önceden derlenmiş üstbilgi`-I`(PCH) `-Yc` `-Yu` dosyaları kullanırken derleyici ile derlemeler arasındaki komut satırı bağımsız değişkenlerini içerir. Bu şekilde yazılan kod artık derleyici tarafından kabul edilmez.   Derleyici şimdi, PCH dosyalarını kullanırken eşleşmez dizin (`-I`) komut satırı bağımsız değişkenlerini belirlemeye yardımcı olmak için derleyici uyarı CC4599'u sorunları.

   ```Output
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position
   ```

   Örnek (daha önce)

   ```ms-dos
    cl /c /Wall /Ycc.h -I.. X.cpp
    cl /c /Wall /Yuc.h Z.cpp
   ```

   Örnek (sonra)

   ```ms-dos
    cl /c /Wall /Ycc.h -I.. X.cpp
    cl /c /Wall /Yuc.h -I.. Z.cpp
   ```

## <a name="whats-new-for-c-in-visual-studio-2013"></a>Visual Studio 2013'te C++ Için Yenilikler

### <a name="improved-iso-cc-standards-support"></a>Geliştirilmiş ISO C/C++ Standart Desteği

#### <a name="compiler"></a>Derleyici

MSVC bu ISO C++11 dil özelliklerini destekler:

- Işlev şablonları için varsayılan şablon bağımsız değişkenleri.
- Temsilci oluşturucuları
- Açık dönüştürme işleçleri.
- Initializer listeleri ve tek tip başlatma.
- Ham dize edebi.
- Variadic şablonlar.
- Diğer ad şablonları.
- Silinen işlevler.
- Statik olmayan veri üyesi başlatılması (NSDMIs).
- Varsayılan işlevler. \*
- Bu ISO C99 dil özelliklerini destekler:
- _Bool
- Bileşik edebi.
- Belirlenmiş baş harfler.
- Bildirimleri kodla karıştırma.
- Değiştirilebilir değerlere string literal dönüştürme yeni derleyici seçeneği `/Zc:strictStrings`kullanılarak izin verilemez. C++98'de, string literals'den `char*` (ve geniş `wchar_t*`dize literals'e) dönüştürme küçümsenir. C++11'de dönüştürme tamamen kaldırıldı. Derleyici kesinlikle standarda uygun olsa da, `/Zc:strictStrings` bunun yerine dönüşümü denetleme seçeneği sağlar. Varsayılan olarak, seçenek kapalıdır. Hata ayıklama modunda bu seçeneği kullandığınızda, STL'nin derleme olmayacağını unutmayın.
- rvalue/lvalue Referans Dökümleri. Rvalue referansları ile C++11, ldeğerleri ile r değerleri arasında net bir şekilde ayırt edilebilir. Daha önce, derleyici belirli döküm senaryolarında bu sağlamadı. Derleyiciyi C++ `/Zc:rvalueCast`Dil Çalışma Kağıdı ile uyumlu hale getirmek için yeni bir derleyici seçeneği eklendi (bkz. bölüm 5.4, [expr.cast]/1). Bu seçenek belirtilmediğinde varsayılan davranış Visual Studio 2012 ile aynıdır.

> [!NOTE]
> Varsayılan işlevler için, =default kullanarak üye olarak taşı oluşturucular ve taşıma atama işleçleri istenmez.

### <a name="c99-libraries"></a>C99 Kütüphaneleri

Bu başlıklarda eksik işlevler için bildirimler ve uygulamalar eklenir: math.h, ctype.h, wctype.h, stdio.h, stdlib.h ve wchar.h. Ayrıca eklenen yeni başlıklar complex.h, stdbool.h, fenv.h, ve inttypes.h, ve tüm işlevler için uygulamalar onları beyan. Yeni C++ sarma başlığı (ccomplex, cfenv, cinttypes, ctgmath) ve diğer bir dizi güncellenir (ccomplex, cctype, clocale, cmath, cstdint, cstdio, cstring, cwchar ve cwctype).

### <a name="standard-template-library"></a>Standart Şablon Kitaplığı

C++11 açık dönüştürme işleçleri, baş harf listeleri, kapsamlı enumlar ve değişken şablonlar için destek.
Artık tüm kapsayıcılar C++11 ince taneli öğe gereksinimlerini destekler.
Bu C++14 özellikleri için destek:

- "Saydam operatör functors" daha az<>, daha fazla<>, artı<>,<> çarpar, vb.
- make_unique\<T>(args...) ve make_unique<T[]>(n)
- cbegin()/cend(), rbegin()/rend(), ve crbegin()/crend() üye olmayan işlevler.
- \<atomik> çok sayıda performans geliştirmeleri aldı.
- \<type_traits> büyük sabitleme ve kod düzeltmeleri aldı.

### <a name="breaking-changes"></a>Hataya Neden Olan Değişiklikler

ISO C/C++ standartları için geliştirilmiş bu destek, Varolan kodda C++11'e uygun olması ve Visual Studio 2013'te Visual C++'da doğru şekilde derlemesi için değişiklik yapılmasını gerektirebilir.

### <a name="visual-c-library-enhancements"></a>Visual C++ Kitaplık Geliştirmeleri

- C++ REST SDK eklenir. REST hizmetlerinin modern bir C++ uygulamasına sahiptir.
- C++ AMP Doku desteği geliştirilmiştir. Şimdi mipmaps ve yeni örnekleme modları için destek içerir.
- PPL görevleri birden çok zamanlama teknolojilerini ve eşzamanlı hata ayıklamayı destekler. Yeni API'ler, hem normal sonuçlar hem de özel durum koşulları için PPL görevlerinin oluşturulmasını sağlar.

### <a name="c-application-performance"></a>C++ Uygulama Performansı

- Otomatik Vektörleştirici artık kodunuzu daha hızlı çalıştırmak için daha fazla C++ deseni tanır ve optimize eder.
- ARM platformu ve Atom mikro-mimari kod kalite iyileştirmeleri.
- __vectorcall arama sözleşmesi eklenir. Vektör kayıtları kullanmak için __vectorcall çağrı kuralını kullanarak vektör türü bağımsız değişkenlerini geçirin.
- Yeni Bağlayıcı Seçenekleri. `/Gw` (Derleyici) ve `/Gy` (assembler) anahtarları, bağlayıcı optimizasyonların yalın ikililer oluşturmasını sağlar.
- Cpu ve GPU arasındaki veri kopyalamayı azaltmak veya ortadan kaldırmak için C++ AMP paylaşılan bellek desteği.

### <a name="profile-guided-optimization-pgo-enhancements"></a>Profil Kılavuzlu Optimizasyon (PGO) geliştirmeleri

- PGO kullanılarak optimize edilen uygulamaların çalışma kümesindeki azalmadan kaynaklanan performans iyileştirmeleri.
- Windows Runtime uygulaması geliştirme için yeni PGO.

### <a name="windows-runtime-app-development-support"></a>Windows Runtime Uygulama Geliştirme Desteği

- **Değer yapılarında Kutulu Türler Için Destek.**

   Artık int'in aksine, null `IBox<int>^` olabilecek alanları kullanarak değer **türlerini**tanımlayabilirsiniz. Bu, alanların bir değere sahip olabileceği veya **nullptr'a**eşit olabileceği anlamına gelir.

- **Daha Zengin Özel Durum Bilgileri.**

   C++/CX, uygulama ikili arabirimi (ABI) genelinde zengin özel durum bilgilerinin yakalanmasını ve yayılmasını sağlayan yeni Windows hata modelini destekler; bu çağrı yığınları ve özel ileti dizeleri içerir.

- **Object::Tostring() artık sanal.**

   Artık kullanıcı tanımlı Windows Runtime ref türlerinde ToString'i geçersiz kılabilirsiniz.

- **Amortismana Karşı ApI'ler için destek.**

   Ortak Windows Runtime API'leri artık amortismana ermiş olarak işaretlenebilir ve yapı uyarısı olarak görünen ve geçiş kılavuzu sağlayabilecek özel bir ileti verilebilir.

- **Hata Ayıklama Geliştirmeleri.**

   Yerel/JavaScript interbugging, Windows Runtime özel durum tanılama ve async kodu hata ayıklama (hem Windows Runtime hem de PPL) desteği.

> [!NOTE]
> Bu bölümde açıklanan C++'a özgü özellikler ve geliştirmelere ek olarak, Visual Studio'daki diğer geliştirmeler de daha iyi Windows Runtime uygulamaları yazmanıza yardımcı olabilir.

### <a name="diagnostics-enhancements"></a>Tanılama Geliştirmeleri

- Hata Ayıklama Geliştirmeleri. Async hata ayıklama ve Sadece Kodum hata ayıklama desteği.
- Kod Analizi Kategorileri. Artık kod hatalarını bulmanıza ve düzeltmenize yardımcı olmak için Kod Çözümleyicisi'nden kategorilere ayrılan çıktıyı görüntüleyebilirsiniz.
- XAML Teşhis. Artık XAML'nizde UI yanıt verme ve pil kullanımı sorunlarını tanılayabilirsiniz.
- Grafik ve GPU Hata Ayıklama Geliştirmeleri.
- Gerçek cihazlarda uzaktan yakalama ve oynatma.
- Eşzamanlı C++ AMP ve CPU hata ayıklama.
- Geliştirilmiş C++ AMP çalışma zamanı tanılama.
- HLSL İşlem shader izleme hata ayıklama.

### <a name="3-d-graphics-enhancements"></a>3-B Grafik Geliştirmeleri

- Önceden çarpılmış alfa DDS biçimi için Görüntü İçeriği Boru Hattı desteği.
- Görüntü Düzenleyicisi, işleme için dahili olarak önceden çarpılmış alfa kullanır ve bu nedenle koyu haleler gibi yapıları işlemekten kaçınır.
- Görüntü ve Model Editörleri. Kullanıcı tanımlı filtre oluşturma artık Görüntü Düzenleyicisi ve Model Düzenleyicisi'nde Shader Designer'da destekleniyor.

### <a name="ide-and-productivity"></a>IDE ve Verimlilik

**Geliştirilmiş Kod Biçimlendirme.** C++ kodunuza daha fazla biçimlendirme ayarı uygulayabilirsiniz. Bu ayarları kullanarak, ayraçların ve anahtar kelimelerin, girintilerin, aralıkların ve satır kaydırmanın yeni satır yerleşimini denetleyebilirsiniz. İfadeleri ve blokları tamamladığınızda ve kodu bir dosyaya yapıştırdığınızda kod otomatik olarak biçimlendirilir.

**Ayraç Tamamlama.** C++ kodu artık bu açılış karakterlerine karşılık gelen kapanış karakterlerini otomatik olarak tamamlar:

- { (kıvırcık ayraç)
- [ (kare ayraç)
- ( (parantez)
- ' (tek tırnak)
- "(çift tırnak)

**Ek C++ Otomatik Tamamlama Özellikleri.**

- Sınıf türleri için yarı nokta nokta ekler.
- Ham dize literals için parantez tamamlar.
- Çok satırlı yorumları tamamlar (/\* \*/)

**Tüm Başvuruları Bul** şimdi metin eşleşmeleri listesini görüntüledikten sonra arka planda başvuruları otomatik olarak çözer ve filtreler.

**Bağlam Tabanlı Üye Listesi Filtreleme.** Erişilemeyen üyeler IntelliSense üye listelerinden filtrelenir. Örneğin, türü uygulayan kodu değiştirmediğiniz sürece, özel üyeler üye listesinde görüntülenmez. Üye listesi açıkken, bir filtreleme düzeyini kaldırmak için **Ctrl**+**J** tuşuna basabilirsiniz (yalnızca geçerli üye listesi penceresi için geçerlidir). Metin filtrelemi kaldırmak ve her üyeyi göstermek için **Ctrl**+**J** tuşuna tekrar basabilirsiniz.

**Parametre Yardım Kaydırma.** Parametre yardımı araç ucunda görüntülenen işlev imzası, yalnızca rasgele bir imza gösterip geçerli içeriğe göre güncelleştirmek yerine, gerçekte yazdığınız parametre sayısına bağlı olarak değişir. Parametre, iç içe olan işlevlerde görüntülendiğinde de doğru şekilde çalışır yardımcı olur.

**Üstbilgi/Kod Dosyasını Geçiş.** Artık kısayol menüsünde bir komut veya klavye kısayolu kullanarak üstbilgi ve ilgili kod dosyası arasında geçiş yapabilirsiniz.

**Yeniden Boyutlandırılabilir C++ Proje Özellikleri Penceresi**

**C++/CX ve C++/CLI'de Olay İşleyici Kodu otomatik oluşturma.**  C++/CX veya C++/CLI kod dosyasına olay işleyicisi eklemek için kod yazarken, düzenleyici otomatik olarak temsilci örneği ve olay işleyicisi tanımı oluşturabilir. Olay işleyici kodu otomatik olarak oluşturulabildiği nde bir araç ipucu penceresi görüntülenir.

**DPI Farkındalık Geliştirme.** Uygulama bildirimi dosyaları için DPI Farkındalık ayarı artık "Per Monitor High DPI Aware" ayarını destekler.

**Daha Hızlı Yapılandırma Geçişi.** Büyük uygulamalar için, yapılandırmaları anahtarlama(özellikle sonraki anahtarlama işlemleri) çok daha hızlı yürütülür.

**Zaman verimliliği oluşturun.** Çok sayıda optimizasyon ve çok çekirdekli kullanım, özellikle büyük projeler için yapıyı daha hızlı hale getirmektedir. C++ WinMD'ye başvuruları olan C++ uygulamaları için artımlı yapılar da çok daha hızlıdır.

## <a name="whats-new-for-c-in-visual-studio-2012"></a>Visual Studio 2012'de C++ için Yenilikler

### <a name="improved-c11-standards-support"></a>Geliştirilmiş C++11 Standartları Desteği

#### <a name="standard-template-library"></a>Standart Şablon Kitaplığı

- Yeni STL başlıkları için \<destek: \<atomik \<>, \<chrono>, \<condition_variable \<>, filesystem>, gelecekteki>, mutex>, \<oran> ve \<iş parçacığı>.
- Bellek kaynağı kullanımını en iyi duruma getirmek için kapsayıcılar artık daha küçüktür. Örneğin, varsayılan ayarları olan x86 `std::vector` sürüm modunda, Visual Studio 2010'daki 16 bayttan Visual Studio 2012'de 12 bayt'a küçülmüş ve `std::map` Visual Studio 2010'daki 16 bayttan Visual Studio 2012'de 8 bayt'a küçülmüş.
- C++11 Standardı'nın izin verdiği ancak gerektirmeden SCARY yineleyicileri uygulanmıştır.

#### <a name="other-c11-enhancements"></a>Diğer C++11 Geliştirmeleri

- Döngüler için aralık tabanlı. Diziler, STL kapsayıcıları ve Windows Runtime koleksiyonları yla çalışan daha sağlam döngüler (for-range-declaration : expression) biçiminde yazabilirsiniz. Bu, Çekirdek Dil desteğinin bir parçasıdır.
- Boş bir lambda tanıtıcısı [] ile başlayan ve hiçbir yerel değişkeni yakalamayan kod blokları olan stateless lambdas, artık C++11 Standardının gerektirdiği şekilde işlev işaretçilerine dolaylı olarak dönüştürülebilir.
- Kapsamlı sayısallaştırma desteği. C++ enum sınıfı enum-key artık desteklenir. Aşağıdaki kod, bu enum anahtarının önceki enum davranışından nasıl farklı olduğunu gösterir.

   ```cpp
  enum class Element { Hydrogen, Helium, Lithium, Beryllium };
  void func1(Element e);
  func1(Hydrogen); // error C2065: 'Hydrogen' : undeclared identifier
  func1(Element::Helium); // OK
   ```

### <a name="windows-runtime-app-development-support"></a>Windows Runtime Uygulama Geliştirme Desteği

- **Yerli XAML tabanlı ui modeli.** Windows Runtime uygulamaları için yeni yerel XAML tabanlı Web Sürümü modelini kullanabilirsiniz.
- **Görsel C++ Bileşen Uzantıları**. Bu uzantılar, Windows Runtime uygulamalarının gerekli bir parçası olan Windows Runtime nesnelerinin tüketimini basitleştirir. Daha fazla bilgi için C++ ve [Visual C++ dil referansı (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md) [kullanarak Windows Runtime uygulamaları için Yol Haritası'na](../cppcx/universal-windows-apps-cpp.md) bakın
- **DirectX oyunları**. Windows Runtime uygulamaları için yeni DirectX desteğini kullanarak ilgi çekici oyunlar geliştirebilirsiniz.
- **XAML/DirectX interop**. Hem XAML hem de DirectX kullanan Windows Runtime uygulamaları artık verimli bir şekilde birlikte çalışıyor.
- **Windows Runtime Bileşeni DLL geliştirme**. Bileşen DLL geliştirme, Windows Runtime ortamını genişletilebilir hale getirir.

### <a name="compiler-and-linker"></a>Derleyici ve Bağlayıcı

- **Otomatik vektörleyici.** Derleyici, kodunuzdaki döngüleri analiz eder ve mümkünse tüm modern işlemcilerde bulunan vektör kayıtları ve yönergeleri kullanan yönergeler yayır. Bu döngüler daha hızlı çalışmasını sağlar. (SimD Uzantılarının Akış için işlemci yönergeleri SSE olarak bilinir). Otomatik olarak uygulandığıiçin bu optimizasyonu etkinleştirmeniz veya istemeniz gerekmez.
- **Otomatik paralelleştirici**. Derleyici, kodunuzdaki döngüleri analiz edebilir ve hesaplamaları birden çok çekirdek veya işlemciye yayan yönergeler yayabilir. Bu döngüler daha hızlı çalışmasını sağlayabilir. Varsayılan olarak etkinleştirilemediği için bu optimizasyonu istemeniz gerekir. Çoğu durumda, paralelleştirilmiş olmasını `#pragma loop(hint_parallel(N))` istediğiniz döngülerden hemen önce kodunuza bir tane eklemenize yardımcı olur.
- Otomatik vektörleştirici ve otomatik paralelleştirici birlikte çalışabilir, böylece hesaplamalar birden çok çekirdek arasında yayılır ve her çekirdekteki kod vektör kayıtları kullanır.

### <a name="new-in-visual-studio-2012-update-1"></a>Visual Studio Yeni 2012 Güncelleme 1

C++ kodunuzu oluştururken Windows XP'yi hedefleyin.
Windows XP ve Windows Server 2003'u hedeflemek için Microsoft C++ derleyicisini ve kitaplıklarını kullanabilirsiniz.

#### <a name="parallel-programming-support"></a>Paralel Programlama Desteği

##### <a name="c-accelerated-massive-parallelism-amp"></a>C++ Accelerated Massive Parallelism (AMP)

C++ AMP, normalde ayrı bir grafik kartında GPU olarak bulunan veri paralel donanımından yararlanarak C++ kodunuzu yürütmeyi hızlandırır. C++ AMP programlama modeli çok boyutlu diziler, dizin oluşturma, bellek aktarımı, döşeme ve matematiksel işlev kitaplığı içerir. C++ AMP dil uzantılarını ve derleyici kısıtlamalarını kullanarak, verilerin CPU'dan GPU'ya nasıl taşındığını ve geri döndürülmesini denetleyebilirsiniz.

**Hata ayıklama.** GPU'yu hedeflemek için C++ AMP kullanan uygulamaların hata ayıklama deneyimi, diğer C++ uygulamaları için hata ayıklama gibidir. Bu, daha önce bahsedilen yeni paralel hata ayıklama eklemelerini içerir.

**Profil oluşturma.** C++ AMP ve diğer Direct3D tabanlı programlama modellerini temel alan GPU etkinliği için profil oluşturma desteği artık vardır.

#### <a name="general-parallel-programming-enhancements"></a>Genel Paralel Programlama Geliştirmeleri

DonanımÇok çekirdekli ve çok çekirdekli mimarilere taşınırken, geliştiriciler artık tek çekirdekli saatlerin sürekli artan saat hızlarına güvenemezler. Eşzamanlılık Çalışma Süresi'ndeki paralel programlama desteği, geliştiricilerin bu yeni mimarilerden yararlanmasını sağlar.
Visual Studio 2010'da, Paralel Desenler Kütüphanesi gibi güçlü C++ paralelleştirme kitaplıkları ve gelişmiş veri akışı ardışık noktalarını ifade ederek eşzamanlılıktan yararlanacak özellikler tanıtıldı. Visual Studio 2012'de bu kitaplıklar, geliştiricilerin en çok ihtiyaç duyduğu paralel desenler için daha iyi performans, daha fazla denetim ve daha zengin destek sağlamak için genişletildi. Teklifin genişliği şimdi içerir:

- Eşzamanlılık ve devamı destekleyen zengin bir görev tabanlı programlama modeli.
- Çatal-birleştirme paralelciliği destekleyen Paralel Algoritmalar (parallel_for, parallel_for_each, parallel_sort, parallel_reduce, parallel_transform ile parallel_for).
- priority_queue, sıra, vektör ve harita gibi std veri yapılarının iş parçacığı güvenli sürümlerini sağlayan eşzamanlılık güvenli kapsayıcılar.
- Geliştiricilerin doğal olarak eşzamanlı birimler halinde ayrıştırılan veri akışı ardışık hatlarını ifade etmek için kullanabilecekleri Eşzamanlı Aracılar Kitaplığı.
- Bu listedeki desenlerin düzgün bir şekilde kompozisyonunu kolaylaştırmak için özelleştirilebilir bir zamanlayıcı ve kaynak yöneticisi.

##### <a name="general-parallel-debugging-enhancements"></a>Genel Paralel Hata Ayıklama Geliştirmeleri

Visual Studio 2012, **Paralel Görevler** penceresi ve **Paralel Yığınlar** penceresine ek olarak, bir ifadenin tüm iş parçacıkları ve işlemlerdeki değerlerini inceleyebilmeniz ve sonuca ayırma ve filtreleme yapabilmeniz için yeni bir **Paralel İzleme** penceresi sunar. Ayrıca pencereyi genişletmek için kendi görselleştiricilerinizi kullanabilir ve tüm araç pencerelerinden yeni çoklu işlem desteğinden yararlanabilirsiniz.

### <a name="ide"></a>IDE

**Visual Studio Şablonları desteği.** Artık C++ proje ve öğe şablonlarını yazar için Visual Studio Şablonları teknolojisini kullanabilirsiniz.

**Asynchronous Çözelti Yükü.** Projeler artık eş zamanlı olarak yüklenir —önce çözümün önemli parçaları— böylece daha hızlı çalışmaya başlayabilirsiniz.

**Uzaktan hata ayıklama için otomatik dağıtım.** Visual C++'da uzaktan hata ayıklama için dosyaların dağıtımı basitleştirilmiştir. Proje bağlamı menüsündeki **Dağıt** seçeneği, hata ayıklama yapılandırma özelliklerinde belirtilen dosyaları otomatik olarak uzak bilgisayara kopyalar. Dosyaları uzak bilgisayara el ile kopyalamak artık gerekli değildir.

**C++/CLI IntelliSense.** C++/CLI artık tam IntelliSense desteğine sahiptir. Hızlı Bilgi, Parametre Yardımı, Liste Üyeleri ve Otomatik Tamamlama gibi IntelliSense özellikleri artık C++/CLI için çalışır. Buna ek olarak, bu belgede listelenen diğer IntelliSense ve IDE geliştirmeleri de C++/CLI için çalışır.

**Daha Zengin IntelliSense Araç İpuçları.** C++ IntelliSense Hızlı Bilgi araç ipuçları artık daha zengin XML belgeleri yorum stili bilgilerini gösterir. Bir kitaplıktan bir API kullanıyorsanız (örneğin, XML dokümantasyon açıklamaları olan C++ AMP) IntelliSense araç ipucu yalnızca bildirimden daha fazla bilgi gösterir. Ayrıca, kodunuzda XML dokümantasyon yorumları varsa, IntelliSense araç ipuçları daha zengin bilgileri gösterir.

**C++ Kod Yapıları.** İskelet kodu, liste Üyeleri açılır listesinde, döngü ve diğer temel kod yapıları için anahtar, if-else için kullanılabilir. Listeden bir kod parçasını seçerek kodunuza ekleyin ve gerekli mantığı doldurun. Ayrıca, düzenleyicide kullanılmak üzere kendi özel kod parçalarınızı da oluşturabilirsiniz.

**Üye Geliştirmelerini Listele.** Kod düzenleyicisine kod yazdıkça **Liste Üyeleri** açılır listesi otomatik olarak görüntülenir. Sonuçlar filtrelenir, böylece siz yazarken yalnızca ilgili üyeler görüntülenir. Metin > **Düzenleyicisi C/C++** > **Advanced**altındaki **Seçenekler** iletişim kutusunda Üye Listesi **Text Editor**tarafından kullanılan filtreleme mantığını kontrol edebilirsiniz.

**Anlamsal Renklendirme.** Türleri, sayısallaştırmalar, makrolar ve diğer C++ belirteçleri artık varsayılan olarak renklendirmeye sahiptir.

**Başvuru Vurgulama.** Bir sembol seçmek, şimdi geçerli dosyadaki sembolün tüm örneklerini vurgular. Vurgulanan başvurular arasında ilerlemek için **Ctrl**+**Shift**+**Up Arrow** veya **Ctrl**+**Shift**+**Down Arrow** tuşlarına basın. Bu özelliği, **Text Editor** > **C/C++** > **Advanced** **altında, Seçenekler** iletişim kutusunda kapatabilirsiniz.

### <a name="application-lifecycle-management-tools"></a>Uygulama Yaşam Döngüsü Yönetim Araçları

#### <a name="static-code-analysis"></a>Statik Kod Analizi

C++ için statik çözümleme, daha zengin hata bağlamı bilgileri, daha fazla çözümleme kuralı ve daha iyi analiz sonuçları sağlamak için güncelleştirildi. Yeni Kod Çözümlemesi penceresinde, iletileri anahtar kelimeye, projeye ve önem derecesine göre filtreleyebilirsiniz. Pencerede bir ileti seçtiğinizde, iletinin tetiklendiği koddaki satır kod düzenleyicisinde vurgulanır. Belirli C++ uyarıları için ileti, uyarıya yol açan yürütme yolunu gösteren kaynak satırları listeler; karar noktaları ve belirli bir yol almak için nedenleri vurgulanır.
Kod analizi Visual Studio 2012'nin çoğu sürümünde yer almaktadır. Professional, Premium ve Ultimate sürümlerinde tüm kurallar dahildir. Windows 8 ve Windows Phone için Express sürümlerinde, sadece en kritik uyarılar dahildir. Kod çözümlemesi Web için Express sürümüne dahil edilmez.
Diğer bazı kod çözümlemesi geliştirmeleri şunlardır:

- Yeni eşzamanlılık uyarıları, çok iş parçacığı yla birlikte c/c++ programlarında doğru kilitleme disiplinlerini kullandığınızdan emin olarak eşzamanlılık hatalarından kaçınmanıza yardımcı olur. Çözümleyici olası yarış koşullarını, kilit sırası ters çevirmelerini, arayan/çağrıcı kilitleme sözleşme ihlallerini, eşleşmemiş eşitleme işlemlerini ve diğer eşzamanlılık hatalarını algılar.
- Kural kümelerini kullanarak kod çözümlemesi çalıştırmalarına uygulamak istediğiniz C++ kurallarını belirtebilirsiniz.
- Kod **Çözümlemesi** penceresinde, kaynak koduna seçili bir uyarıyı bastıran bir pragma ekleyebilirsiniz.
- Bir işlevin parametrelerini nasıl kullandığını, onlar hakkında yaptığı varsayımları ve bittiğinde verdiği garantileri açıklamak için Microsoft kaynak kodu ek açıklama dilinin (SAL) yeni sürümünü kullanarak statik kod çözümlemesi doğruluğunu ve bütünlüğünü artırabilirsiniz.
- 64bit C++ projeleri için destek.

#### <a name="updated-unit-test-framework"></a>Güncellenmiş Ünite Test Çerçevesi

C++ birim testleri yazmak için Visual Studio'daki yeni C++ birim test çerçevesini kullanın. Yeni Proje iletişim kutusunda Visual C++ kategorisi altında C++ Birim Test Projesi şablonunu bularak mevcut C++ çözümünüze yeni bir birim test projesi ekleyin. Unittest1.cpp dosyasında oluşturulan TEST_METHOD kod saplama biriminin testlerini yazmaya başlayın. Test kodu yazıldığında, çözümü oluşturun. Testleri çalıştırmak istediğinizde, > **Diğer Windows** > Birimi Test Gezgini'ni **Görüntüle'yi**seçerek bir **Birim Test Gezgini** penceresi açın ve ardından istediğiniz test çalışması için kısayol menüsünde**Unit Test Explorer** **seçili testi çalıştır'ı**seçin. Test çalışması bittikten sonra, test sonuçlarını ve ek yığın izleme bilgilerini aynı pencerede görüntüleyebilirsiniz.

#### <a name="architecture-dependency-graphs"></a>Mimari Bağımlılık Grafikleri

Kodunuzu daha iyi anlamak için, artık ikili, sınıf, ad alanı için bağımlılık grafikleri oluşturabilir ve bir çözüme dosyalar ekleyebilirsiniz. Menü çubuğunda, bağımlılık grafiği oluşturmak için **Mimari** > **Bağımlılık Oluştur Grafiği'ni**ve ardından **Çözüm veya** Dosya Ekle için bir bağımlılık grafiği oluşturmak **için** oluşturun'u seçin. Grafik oluşturma tamamlandığında, her düğümü genişleterek onu keşfedebilir, düğümler arasında hareket ederek bağımlılık ilişkilerini öğrenebilir ve düğüm için kısayol menüsünde **İçeriği Görüntüle'yi** seçerek kaynak koduna göz atabilirsiniz. \*.cpp kaynak kod dosyası veya \*.h üstbilgi dosyasının kısayol menüsünde, dosyaları eklemek için bağımlılık grafiği oluşturmak için Dosyaları Dahil Et **Grafiği'ni**seçin.

#### <a name="architecture-explorer"></a>Mimari Gezgini

**Mimari**Gezgini'ni kullanarak, C++ çözümünüzdeki, projelerinizdeki veya dosyalarınızdaki varlıkları keşfedebilirsiniz. Menü çubuğunda **Mimari** > **Windows** > **Architecture Explorer'ı**seçin. İlgilendiğiniz bir düğüm seçebilirsiniz, **örneğin, Sınıf Görünümü.** Bu durumda, araç penceresinin sağ tarafı ad alanları listesi yle genişletilir. Bir ad alanı seçerseniz, yeni bir sütun bu ad alanında sınıfların, yapıların ve gelenlerin listesini gösterir. Bu varlıkları keşfetmeye devam edebilir veya başka bir sorgu başlatmak için en soldaki sütuna geri dönebilirsiniz. **Bkz. Mimari Explorer ile Kodu Bul.**

#### <a name="code-coverage"></a>Kod Kapsamı

Kod kapsamı, çalışma zamanında dinamik olarak enstrüman ikilileri olarak güncelleştirildi. Bu, yapılandırma ek yükü düşürür ve daha iyi performans sağlar. C++ uygulamaları için birim testlerinden kod kapsamı verileri de toplayabilirsiniz. C++ birim testleri oluşturduğunuzda, çözümünüzü bulmak için **Birim Test Gezgini'ni** kullanabilirsiniz. Birim testlerini çalıştırmak ve onlar için kod kapsamı verilerini toplamak için **Birim Test Gezgini'nde** **Kod Kapsamını Çözümle'yi**seçin. **Kod Kapsamı Sonuçları** penceresindeki kod kapsamı sonuçlarını menü çubuğunda inceleyebilir,**Windows** > **Kodu Kapsamı Sonuçlarını** **Test'i** > seçebilirsiniz.

## <a name="whats-new-for-c-in-visual-studio-2010"></a>Visual Studio 2010'da C++ için Yenilikler

### <a name="c-compiler-and-linker"></a>C++ Derleyici ve Bağlayıcı

**otomatik Anahtar Kelime.** **Otomatik** anahtar kelimenin yeni bir amacı vardır. Değişkenin bildirimindeki başlatma ifadesinden türü çıkarılan bir değişkeni bildirmek için **otomatik** anahtar kelimenin varsayılan anlamını kullanın. Derleyici seçeneği, `/Zc:auto` **otomatik** anahtar kelimenin yeni veya önceki anlamını çağırır.

**decltype Tip Belirtici.** **Decltype** türü belirtici belirtilen ifade türünü döndürür. Karmaşık veya yalnızca derleyici tarafından bilinen bir türü bildirmek için **otomatik** anahtar kelimeyle birlikte **decltype** türü belirtileyicisini kullanın. Örneğin, geri dönüş türü şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevini bildirmek için birleşimi kullanın. Veya, başka bir işlev çağıran ve sonra çağrılan işlevin dönüş türünü döndüren bir şablon işlevi bildirin.

**Lambda İfadeler.** Lambda fonksiyonları bir fonksiyon gövdesi var ama hiçbir adı. Lambda işlevleri işlev işaretçileri ve işlev nesnelerinin en iyi özelliklerini birleştirir. Bir lambda işlevini, işlev nesnesi yerine şablon işlev parametresi olarak veya türü lambda olan bir değişkeni bildirmek için **otomatik** anahtar kelimeyle birlikte kullanın.

**Rvalue Başvuru.** Rvalue başvuru beyanatörü (&&) bir rvalue için bir başvuru bildirir. Rvalue başvurusu, daha verimli yapıcılar, işlevler ve şablonlar yazmak için taşıma semantikve mükemmel yönlendirme kullanmanıza olanak sağlar.

**static_assert Beyannamesi.** **static_assert** bildirimi, çalışma zamanında sınanan diğer sahipleç mekanizmalarının aksine, bir yazılım iddiasını derleme zamanında sınar. İddia başarısız olursa, derleme başarısız olur ve belirtilen bir hata iletisi verilir.

**nullptr ve __nullptr Anahtar Kelimeler.** **MSVC, nullptr** anahtar sözcüğünün yerel kodla veya yönetilen kodla kullanılmasına olanak tanır. **Nullptr** anahtar sözcüğü, nesne tutamacının, iç işaretçisinin veya yerel işaretçi türünün bir nesneyi işaret etmediğini gösterir. Derleyici, `/clr` derleyici seçeneğini kullandığınızda `/clr` **nullptr'u** yönetilen kod olarak, seçeneği kullanmadığınızda ise yerel kodu yorumlar.
**Microsoft'a** özgü __nullptr anahtar kelimesi **nullptr**ile aynı anlama gelir, ancak yalnızca yerel kod için geçerlidir. `/clr` Derleyici seçeneğini kullanarak yerel C/C++ kodunu derlerseniz, derleyici **nullptr** anahtar sözcüğünün yerel mi yoksa yönetilen bir terim mi olduğunu belirleyemez. Niyetinizi derleyiciye açık hale getirmek için yönetilen terimi belirtmek için nullptr anahtar sözcük ve yerel terimi belirtmek için **__nullptr** kullanın.

**/Zc:trigraphs Derleyici Seçeneği.** Varsayılan olarak, trigraphs için destek devre dışı bırakılır. Trigraphs desteğini etkinleştirmek için `/Zc:trigraphs` derleyici seçeneğini kullanın.
Bir trigraph iki ardışık soru işaretleri (??) ve ardından benzersiz bir üçüncü karakter oluşur. Derleyici, bir trigraph'ı karşılık gelen noktalama işareti karakteriyle değiştirir. Örneğin, derleyici değiştirir ?? = # (sayı işareti) karakteri ile trigraph. Belirli noktalama işaretleri içermeyen bir karakter kümesi kullanan C kaynak dosyalarında üç grafi kullanın.

**Yeni Profil Destekli Optimizasyon Seçeneği.** PogoSafeMode, uygulamanızı optimize ettiğinizde güvenli mod mu yoksa hızlı mod mu kullanacağınızı belirtmenizi sağlayan yeni bir profil güdümlü optimizasyon seçeneğidir. Güvenli mod iş parçacığı için güvenlidir, ancak hızlı moddan daha yavaştır. Hızlı mod varsayılan davranıştır.

**Yeni Ortak Dil Çalışma Süresi (CLR) Seçeneği /clr:nostdlib.** (Ortak Dil Çalışma `/clr` Zamanı Derlemesi) için yeni bir seçenek eklenir. Aynı kitaplıkların farklı sürümleri eklenmişse, derleme hatası verilir. Yeni seçenek, programınızın belirli bir sürümü kullanabilmesi için varsayılan CLR kitaplıklarını hariç tutmanızı sağlar.

**Yeni pragma direktifi detect_mismatch.** detect_mismatch pragma yönergesi, dosyalarınıza aynı ada sahip diğer etiketlerle karşılaştırılabilen bir etiket koymanızı sağlar. Aynı ad için birden çok değer varsa, bağlayıcı bir hata verir.

**XOP Intrinsics, FMA4 Intrinsics ve LWP Intrinsics.** Visual Studio 2010 SP1 için eklenen XOP İçsel, Visual Studio 2010 SP1 için eklenen FMA4 İçsel ve Visual Studio 2010 SP1 için eklenen LWP Intrinsics'i desteklemek için yeni içsel fonksiyonlar eklendi. Belirli bir bilgisayarda hangi işlemci teknolojilerinin destekleniyi belirlemek için __cpuid __cpuidex kullanın.

### <a name="visual-studio-c-projects-and-the-build-system"></a>Visual Studio C++ projeleri ve Yapı Sistemi

**Msbuild.** Visual C++ çözümleri ve projeleri artık VCBuild.exe'nin yerini alan MSBuild.exe kullanılarak oluşturulmuştür. MSBuild, diğer Visual Studio dilleri ve proje türleri tarafından kullanılan aynı esnek, genişletilebilir, XML tabanlı yapı aracıdır. Bu değişiklik nedeniyle Visual Studio C++ proje dosyaları artık XML dosya biçimini kullanıyor ve .vcxproj dosya adı uzantısına sahip. Visual Studio'nun önceki sürümlerindeki Visual Studio C++ proje dosyaları otomatik olarak yeni dosya biçimine dönüştürülür.

**VC++ Dizinleri.** VC++ dizinleri ayarı artık iki yerde bulunuyor. VC++ dizinleri için proje başına değerleri ayarlamak için proje özelliği sayfalarını kullanın. VC++ dizinleri için yapılandırma başına genel değerleri ayarlamak için **Özellik Yöneticisi'ni** ve özellik sayfasını kullanın.

**Projeden Projeye Bağımlılıklar.** Önceki sürümlerde, projeler arasındaki tanımlı bağımlılıklar çözüm dosyasında depolandı. Bu çözümler yeni proje dosyası biçimine dönüştürüldüğünde, bağımlılıklar projeden projeye başvurulara dönüştürülür. Çözüm bağımlılıkları ve projeden projeye başvuru kavramları farklı olduğundan, bu değişiklik uygulamaları etkileyebilir.

**Makrolar ve Çevre Değişkenleri.** Yeni _ITERATOR_DEBUG_LEVEL makro, yineleyiciler için hata ayıklama desteği çağırır. Eski _SECURE_SCL ve _HAS_ITERATOR_DEBUGGING makroları yerine bu makroyu kullanın.

### <a name="visual-c-libraries"></a>Visual C++ Kitaplıkları

**Eşzamanlı Çalışma Zamanı Kitaplıkları.** Eşzamanlı Çalışma Zamanı çerçevesi, aynı anda çalışan uygulamaları ve bileşenleri destekler ve Visual C++'da eşzamanlı uygulamaları programlamak için bir çerçevedir. Paralel Desenler Kitaplığı (PPL), eşzamanlı uygulama programlamayı desteklemek için ince taneli paralellik gerçekleştirmek için genel amaçlı kapsayıcılar ve algoritmalar sağlar. Asynchronous Agents Library, kaba taneli veri akışı ve pipelining görevleri için aktör tabanlı bir programlama modeli ve ileti geçiş arabirimleri sağlar.

**Standart C++ Kitaplığı.** Aşağıdaki liste, Standart C++ Kitaplığı'nda yapılan değişikliklerin çoğunu açıklar.

- Yeni rvalue reference C++ dil özelliği, Standart Şablon Kitaplığı'ndaki birçok işlev için taşıma semantikve mükemmel yönlendirme uygulamak için kullanılmıştır. Semantik ve mükemmel yönlendirmeyi, değişkenleri veya parametreleri ayıran veya atayabilen işlemlerin performansını büyük ölçüde artırın.
- Rvalue başvuruları, `unique_ptr` `auto_ptr` sınıftan daha güvenli bir akıllı işaretçi türü olan yeni sınıfı uygulamak için de kullanılır. Sınıf `unique_ptr` taşınabilir ancak kopyalanamaz, güvenliği etkilemeden katı sahiplik semantikleri uygular ve rvalue başvurularının farkında olan kapsayıcılarla iyi çalışır. Sınıf `auto_ptr` amortismana lı.
- Örneğin, `find_if_not` `copy_if` `is_sorted`algoritmaya> üstbilgisine \<on beş yeni işlev eklendi.
- \<Bellek> üstbilgide, yeni make_shared işlevi, nesnenin oluşturulduğu anda bir nesneye paylaşılan işaretçi yapmak için kullanışlı, sağlam ve etkili bir yoldur.
- Tek bağlantılı listeler \<forward_list> üstbilgi tarafından desteklenir.
- Yeni `cbegin`, `cend` `crbegin`, `crend` , ve `const_iterator` üye işlevler bir kapsayıcı aracılığıyla ileri veya geri hareket eden bir sağlar.
- üstbilgi \<ve ilgili şablonlar> system_error, alt düzey sistem hatalarının işlenmesini destekler. `exception_ptr` Sınıfın üyeleri, özel durumları iş parçacıkları arasında taşımak için kullanılabilir.
- Codecvt \<> üstbilgi, Unicode karakterlerinin çeşitli kodlamalarını diğer kodlamalara dönüştürmeyi destekler.
- Üstbilgi \<> ayırıcılar, düğüm tabanlı kapsayıcılar için ayırmaya ve bellek bloklarını boşaltmaya yardımcı olan birkaç şablon tanımlar.
- \<Rasgele> üstbilgi için çok sayıda güncelleştirme vardır.

### <a name="microsoft-foundation-class-mfc-library"></a>Microsoft Hazırlık Sınıfı (MFC) Kitaplığı

**Windows 7 Özellikleri.** MFC, Şerit kullanıcı arabirimi (UI), Görev Çubuğu, atlama listeleri, sekmeli küçük resimler, küçük resim önizlemeleri, ilerleme çubuğu, simge bindirme ve arama dizini gibi birçok Windows 7 özelliğini destekler. MFC birçok Windows 7 özelliğini otomatik olarak desteklediğinden, varolan uygulamanızı değiştirmeniz gerekmeyebilir. Yeni uygulamalardaki diğer özellikleri desteklemek için, kullanmak istediğiniz işlevselliği belirtmek için MFC Uygulama Sihirbazı'nı kullanın.

**Çoklu dokunma lı Farkındalık.** MFC, microsoft surface işletim sistemi için yazılmış çok dokunuşlu kullanıcı arabirimine sahip uygulamaları destekler. Çoklu dokunma uygulaması, dokunmatik iletilerin birleşimleri olan Windows touch iletilerini ve hareket iletilerini işleyebilir. Dokunma ve hareket olayları için başvurunuzu kaydetmeniz ve işletim sistemi çoklu dokunma olaylarını etkinlik işleyicilerinize yönlendirecektir.

**Yüksek DPI farkındalığı.** Varsayılan olarak, MFC uygulamaları artık Yüksek DPI farkındadır. Bir uygulama Yüksek DPI (inç başına yüksek noktalar) farkındaysa, işletim sistemi pencereleri, metni ve diğer Kullanıcı Arası öğelerini geçerli ekran çözünürlüğüne ölçeklendirebilir. Bu, ölçeklenmiş bir görüntünün doğru şekilde döşenme olasılığının daha yüksek olduğu ve kırpılmama veya piksellenmediği anlamına gelir.

**Manager'ı yeniden başlat.** Yeniden başlatma yöneticisi belgeleri otomatik olarak kaydeder ve beklenmedik bir şekilde kapanırsa veya yeniden başlatılırsa başvurunuzu yeniden başlatır. Örneğin, uygulamanız otomatik güncelleştirme tarafından kapatıldıktan sonra yeniden başlatma yöneticisini kullanabilirsiniz. Yeniden başlatma yöneticisini kullanmak için uygulamanızı yapılandırma hakkında daha fazla bilgi için **bkz.**

**Ctaskdialog.** Sınıf, `CTaskDialog` standart `AfxMessageBox` ileti kutusu yerine kullanılabilir. Sınıf, `CTaskDialog` standart ileti kutusundan daha fazla bilgi görüntüler ve toplar.

#### <a name="safeint-library"></a>SafeInt Kitaplığı

Yeni SafeInt Kitaplığı, tamsayı taşmasını hesaba katan güvenli aritmetik işlemler gerçekleştirir. Bu kitaplık aynı zamanda farklı tamsa türlerini de karşılaştırır.

#### <a name="new-active-template-library-atl-macros"></a>Yeni Etkin Şablon Kitaplığı (ATL) makroları

PROP_ENTRY_TYPE ve PROP_ENTRY_TYPE_EX işlevselliğini genişletmek için ATL'ye yeni makrolar eklendi. PROP_ENTRY_INTERFACE ve PROP_ENTRY_INTERFACE_EX geçerli CLSID'lerin bir listesini eklemenize izin verin. PROP_ENTRY_INTERFACE_CALLBACK ve PROP_ENTRY_INTERFACE_CALLBACK_EX, CLSID'nin geçerli olup olmadığını belirlemek için bir geri arama işlevi belirtmenize izin verin.

#### <a name="analyze-warnings"></a>/uyarıları analiz et

Çoğu `/analyze` (Kurumsal Kod Çözümlemesi) uyarıları C Çalışma Süresi (CRT), MFC ve ATL kitaplıklarından kaldırıldı.

#### <a name="animation-and-d2d-support"></a>Animasyon ve D2D desteği

MFC artık animasyon ve Direct2D grafiklerini destekler. MFC kitaplığı, bu işlevselliği desteklemek için birkaç yeni MFC sınıfı ve işlevine sahiptir. Ayrıca, bir Projeye D2D nesnesi ve animasyon nesnesi nasıl ekleyeceğini gösteren iki yeni gözden geçirme vardır. Bu walkthroughs şunlardır: Bir MFC Projesi ve Walkthrough **bir D2D Nesne ekleme:** **Bir MFC Projesi animasyon ekleme**.

### <a name="ide"></a>IDE

**Geliştirilmiş IntelliSense.** IntelliSense for Visual C++ daha hızlı, daha doğru ve daha büyük projeleri işleyebilir şekilde tamamen yeniden tasarlandı. Bu gelişmeyi sağlamak için IDE, geliştiricinin kaynak kodunu nasıl görüntüleleri ve modiyi nasıl yaptığı ile IDE'nin bir çözüm oluşturmak için kaynak kodu ve proje ayarlarını nasıl kullandığı arasında bir ayrım yapar.
Bu görev ayrımı nedeniyle, **Sınıf Görünümü** ve yeni **Gezin** iletişim kutusu gibi tarama özellikleri, eski derleme yok göz atma (.ncb) dosyasının yerini alan yeni bir SQL Server masaüstü veritabanı (.sdf) dosyasını temel alan bir sistem tarafından işlenir. IntelliSense, Hızlı Bilgi, Otomatik Tamamlama ve Parametre Yardım gibi özellikler çeviri birimlerini yalnızca gerektiğinde ayrıştırın. Yeni **Çağrı Hiyerarşisi** penceresi gibi karma özellikler, gözatma ve IntelliSense özelliklerinin bir birleşimini kullanır.
IntelliSense yalnızca şu anda ihtiyaç duyduğunuz bilgileri işlediği için, IDE daha duyarlıdır. Ayrıca, bilgiler daha güncel olduğundan, IDE görünümleri ve pencereleri daha doğrudur. Son olarak, IDE altyapısı daha iyi organize, daha yetenekli ve daha ölçeklenebilir olduğundan, daha büyük projeleri işleyebilir.

**Geliştirilmiş IntelliSense Hataları.** IDE, IntelliSense kaybına neden olabilecek hataları daha iyi algılar ve altlarında kırmızı dalgalı alt çizgi görüntüler. Buna ek olarak, IDE Hata Listesi **Penceresine**IntelliSense hataları raporlar. Soruna neden olan kodu görüntülemek için **Hata Listesi Penceresindeki**hatayı çift tıklatın.

**#include Otomatik Tamamlama Özelliği.** IDE, anahtar kelimeiçin `#include` otomatik tamamlamayı destekler. `#include`Yazdığınızda, IDE geçerli üstbilgi dosyalarının açılır liste kutusunu oluşturur. Bir dosya adı yazarak devam ederseniz, IDE girişinize göre listeyi filtreler. Herhangi bir noktada, eklemek istediğiniz dosyayı listeden seçebilirsiniz. Bu, tam dosya adını bilmeden dosyaları hızla eklemenizi sağlar.

**Gidin.** **Gezin** iletişim kutusu, projenizdeki belirli bir dizeyle eşleşen tüm sembolleri ve dosyaları aramanızı sağlar. Arama dizenize ek karakterler yazdıkça arama sonuçları hemen gözden geçirilir. **Sonuçlar** geri bildirim alanı, bulunan öğelerin sayısını söyler ve aramanızı kısıtlayıp kısıtlamayacağınıza karar vermenize yardımcı olur. **Tür/Kapsam,** **Konum**ve **Önizleme** geri bildirim alanları, benzer adlara sahip öğeleri birbirinden belirlemenize yardımcı olur. Ayrıca, bu özelliği diğer programlama dillerini desteklemek için genişletebilirsiniz.

**Paralel Hata Ayıklama ve Profil Oluşturma.** Visual Studio hata ayıklama, Eşzamanlılık Çalışma Zamanı'nın farkındadır ve paralel işleme uygulamalarını gidermenize yardımcı olur. Uygulamanızın genel davranışını görselleştirmek için yeni eşzamanlılık profil oluşturucu aracını kullanabilirsiniz. Ayrıca, görevlerin durumunu ve çağrı yığınlarını görselleştirmek için yeni araç pencerelerini kullanabilirsiniz.

**Kurdele Tasarımcısı.** **Şerit Tasarımcısı,** MFC şerit lii oluşturmanıza ve değiştirmenize olanak tanıyan bir grafik düzenleyicidir. Son şerit UI XML tabanlı kaynak dosyası (.mfcribbon-ms) ile temsil edilir. Varolan uygulamalar için, geçici olarak birkaç kod satırı ekleyerek ve ardından **Şerit Tasarımcısı'nı**çağırarak geçerli şerit kullanıcı arabirimi'nizi yakalayabilirsiniz. Şerit kaynak dosyası oluşturulduktan sonra, el yazısı şerit lii ui kodunuzu şerit kaynağını yükleyen birkaç deyimle değiştirebilirsiniz.

**Hiyerarşi'yi arayın.** **Çağrı Hiyerarşisi** penceresi, belirli bir işlev tarafından çağrılan tüm işlevlere veya belirli bir işlevi çağıran tüm işlevlere gezinmenizi sağlar.

### <a name="tools"></a>Araçlar

**MFC Sınıf Sihirbazı.** Visual C++ 2010, saygın MFC Sınıf Sihirbazı aracını geri getirir. MFC Sınıf Sihirbazı, kaynak dosya kümelerini el ile değiştirmek zorunda kalmadan projeye sınıflar, iletiler ve değişkenler eklemek için kullanışlı bir yoldur.

**ATL Kontrol Sihirbazı.** ATL Denetim Sihirbazı artık alanı `ProgID` otomatik olarak doldurmaz. Bir ATL denetiminde başka `ProgID`araçlar yoksa, başka araçlar onunla çalışmayabilir. Denetimlerin olmasını gerektiren `ProgID` bir araca örnek olarak Etkin Denetim **Ekle** iletişim kutusu eklenir. İletişim kutusu hakkında daha fazla bilgi için **ActiveX Denetimi İletişim Kutusu Ekle'ye**bakın.

### <a name="microsoft-macro-assembler-reference"></a>Microsoft Macro Assembler Başvurusu

YMMWORD veri türünün eklenmesi, Intel Advanced Vector Extensions (AVX) talimatlarında yer alan 256 bit multimedya operandlarını destekler.

## <a name="whats-new-for-c-in-visual-studio-2008"></a>Visual Studio 2008'de C++ için Yenilikler

### <a name="visual-c-integrated-development-environment-ide"></a>Visual C++ Entegre Geliştirme Ortamı (IDE)

- ATL, MFC ve Win32 uygulamalarında oluşturulan iletişim kutuları artık Windows Vista stil yönergelerine uygundur. Visual Studio 2008'i kullanarak yeni bir proje oluşturduğunuzda, uygulamanıza eklediğiniz tüm iletişim kutuları Windows Vista stil kılavuzuna uygun olacaktır. Oluşturduğunuz bir projeyi Visual Studio'nun önceki bir sürümüyle yeniden derlerseniz, varolan iletişim kutuları daha önce sahip oldukları görünümü korur. Uygulamanıza iletişim kutuları ekleme hakkında daha fazla bilgi için **İletişim Düzenleyicisi'ne**bakın.

- **ATL Project** sihirbazı artık tüm kullanıcılar için bileşenleri kaydetme seçeneğine sahiptir. Visual Studio 2008'den başlayarak, **Tüm kullanıcılar için Kaydol bileşenini**seçmediğiniz sürece, **ATL Project** sihirbazı tarafından oluşturulan COM bileşenleri ve tür kitaplıkları kayıt defterinin HKEY_CURRENT_USER düğümüne kaydedilir.
- **ATL Project** sihirbazı artık atfedilen ATL projeleri oluşturmak için bir seçenek sağlamaz. Visual Studio 2008'den başlayarak, **ATL Project** sihirbazının yeni bir projenin atfedilen durumunu değiştirme seçeneği yoktur. Sihirbazın oluşturduğu tüm yeni ATL projeleri artık atfedilmemiştir.
- Kayıt defterine yazma yönlendirilebilir. Windows Vista'nın piyasaya sürülmesiyle, kayıt defterinin belirli alanlarına yazma nın yüksek modda çalışması için bir program gerektirir. Visual Studio'yu her zaman yüksek modda çalıştırmak istenmez. Kullanıcı başına yeniden yönlendirme, kayıt defteri yazarlarını herhangi bir programlama değişikliği olmadan HKEY_CLASSES_ROOT'dan HKEY_CURRENT_USER otomatik olarak yönlendirir.
- **Sınıf Tasarımcısı** artık yerel C++ kodu için sınırlı desteğe sahiptir. Visual Studio'nun önceki **sürümlerinde, Sınıf Tasarımcısı** sadece Visual C# ve Visual Basic ile çalışmıştır. C++ kullanıcıları artık **Sınıf**Tasarımcısı'nı, ancak yalnızca salt okunur modunda kullanabilirler. C++'lı **Sınıf Tasarımcısı'nın** nasıl kullanılacağı hakkında daha fazla bilgi için **bkz.**
- Proje sihirbazı artık bir C++ SQL Server projesi oluşturma seçeneğine sahip değildir. Visual Studio 2008'den başlayarak, yeni proje sihirbazınc++ SQL Server projesi oluşturma seçeneği yoktur. Visual Studio'nun önceki bir sürümünü kullanarak oluşturulan SQL Server projeleri yine de derlenecek ve doğru çalışacaktır.

### <a name="visual-c-libraries"></a>Visual C++ Kitaplıkları

#### <a name="general"></a>Genel

- Uygulamalar Visual C++ kitaplıklarının belirli sürümlerine bağlanabilir. Bazen bir uygulama, bir sürümden sonra Visual C++ kitaplıklarında yapılan güncelleştirmelere bağlıdır. Bu durumda, uygulamayı kitaplıkların önceki sürümlerine sahip bir bilgisayarda çalıştırmak beklenmeyen davranışlara neden olabilir. Artık bir uygulamayı kitaplıkların belirli bir sürümüne bağlayabilirsiniz, böylece kitaplıkların önceki sürümüolan bir bilgisayarda çalışmaz.

#### <a name="stlclr-library"></a>STL/CLR Kitaplığı

- Visual C++ artık STL/CLR Kitaplığını içerir. STL/CLR Kitaplığı, Standart C++ Kitaplığı'nın bir alt kümesi olan Standart Şablon Kitaplığı'nın (STL) C++ ve .NET Framework ortak dil çalışma süresi (CLR) ile kullanılmak üzere bir ambalajıdır. STL/CLR ile artık yönetilen bir ortamda STL'nin tüm kapsayıcılarını, yineleyicilerini ve algoritmalarını kullanabilirsiniz.

#### <a name="mfc-library"></a>MFC Kütüphanesi

- Windows Vista Ortak Denetimleri destekler. Windows Vista'daki özellikleri desteklemek veya geçerli MFC sınıflarında işlevselliği geliştirmek için 18 yeni veya varolan sınıfta 150'den fazla yöntem eklendi.
- Yeni `CNetAddressCtrl` sınıf, IPv4 ve IPv6 adreslerini veya DNS adlarını giriş yapmanızı ve doğrulamanızı sağlar.
- Yeni `CPagerCtrl` sınıf, Windows çağrı cihazı denetiminin kullanımını basitleştirir.
- Yeni `CSplitButton` sınıf, varsayılan veya isteğe bağlı bir eylem seçmek için Windows splitbutton denetiminin kullanımını basitleştirir.

#### <a name="c-support-library"></a>C++ Destek Kitaplığı

- C++, mareşallik kitaplığını tanıtıyor. Mareşalkitapyerel ve yönetilen ortamlar arasında veri mareşal kolay ve optimize edilmiş bir yol sağlar. Kitaplık, PInvoke kullanma gibi daha karmaşık ve daha az verimli yaklaşımlara alternatiftir. Daha fazla bilgi için **C++'da Mareşallik** Bölümü'ne genel bakış.

#### <a name="atl-server"></a>ATL Sunucu

- ATL Server paylaşılan bir kaynak projesi olarak yayımlanır.
- ATL Server kod tabanının çoğu CodePlex'te paylaşılan kaynak projesi olarak yayımlanmıştır ve Visual Studio 2008'in bir parçası olarak yüklenmez. ATL Server ile ilişkili çeşitli dosyalar artık Visual Studio'nun bir parçası değildir. Kaldırılan dosyalar listesi için Bkz. **Kaldırılan ATL Sunucu Dosyaları.**
- Atlenc.h'den veri kodlama ve kod çözme sınıfları ve atlutil.h ve atlpath.h'deki yardımcı işlevler ve sınıflar artık ATL kitaplığının bir parçasıdır.
- Microsoft, Visual Studio'nun önceki sürümlerinde yer alan ATL Server sürümlerini, Visual Studio'nun sürümleri desteklendikçe desteklemeye devam edecektir. CodePlex, topluluk projesi olarak ATL Server kodunun geliştirilmesine devam edecektir. Microsoft, ATL Server'ın CodePlex sürümünü desteklemez.

### <a name="visual-c-compiler-and-linker"></a>Görsel C++ Derleyici ve Bağlayıcı

#### <a name="compiler-changes"></a>Derleyici Değişiklikleri

- Derleyici yönetilen artımlı yapıları destekler. Bu seçeneği belirttiğiniz zaman, derleyici başvurulan bir derleme değiştiğinde kodu yeniden derlemez. Bunun yerine artımlı bir yapı gerçekleştirecektir. Dosyalar yalnızca değişiklikler bağımlı kodu etkiliyorsa yeniden derlenir.
- ATL Server ile ilgili öznitelikler artık desteklenmez. Derleyici artık Doğrudan ATL Server ile ilgili çeşitli öznitelikleri destekler. Kaldırılan özniteliklerin tam listesi için, Son Lama Değişikliklerine bakın.
- Derleyici Intel Core mikromimarisini destekler. Derleyici, kod oluşturma sırasında Intel Core mikromimarisi için aparat içerir. Varsayılan olarak, bu aparat, Pentium 4 ve diğer işlemcilere de yardımcı olduğu için devre dışı bırakılır.
- İçsel bilgiler yeni AMD ve Intel işlemcileri destekler. Birkaç yeni içsel talimatlar daha yeni AMD ve Intel işlemcilerde daha büyük işlevselliği destekler. Yeni içselbilgiler hakkında daha fazla bilgi için, **Bkz. Ek Streaming SIMD Uzantıları 3 Talimatlar**, **Streaming SIMD Uzantıları 4 Talimatlar**, **SSE4A ve Gelişmiş Bit Manipülasyon İçseller**, **AES Intrinsics**, **_mm_clmulepi64_si128**, ve **__rdtscp**.
- İşlev `__cpuid` güncelleştirildi. `__cpuid`Amd `__cpuidex` ve Intel işlemcilerin en son revizyonlarından birkaç yeni özellik desteklatıyor. İçsel `__cpuidex` yeni ve son işlemcilerden daha fazla bilgi toplar.
- `/MP` Derleyici seçeneği toplam oluşturma süresini azaltır. Bu `/MP` seçenek, dosyaları aynı anda derleyen birkaç işlem oluşturarak birkaç kaynak dosyaderlemenin toplam süresini önemli ölçüde azaltabilir. Bu seçenek özellikle hiperiş parçacığı, birden çok işlemci veya birden çok çekirdeği destekleyen bilgisayarlarda kullanışlıdır.
- Derleyici `/Wp64` seçeneği ve **__w64** anahtar kelime amortismana alınır. Derleyici `/Wp64` seçeneği ve 64 bit taşınabilirlik sorunlarını algılayan **__w64** anahtar sözcüğü amortismana alınır ve derleyicinin gelecekteki sürümünde kaldırılır. Bu derleyici seçeneği ve anahtar kelime yerine, 64 bit platform hedefleyen bir MSVC kullanın.
- `/Qfast_transcendentals`transandantal işlevler için satır içinde kod oluşturur.
- `/Qimprecise_fwaits``/fp:except` derleyici seçeneğini kullandığınızda blokları denemek için iç fwait komutlarını kaldırır.

### <a name="linker-changes"></a>Bağlayıcı Değişiklikleri

- Kullanıcı Hesabı Denetimi bilgileri artık Visual C++ bağlayıcısı (link.exe) tarafından yürütülebilir olarak oluşturulan manifesto dosyalarına gömülüdür. Bu özellik varsayılan olarak etkinleştirilir. Bu özelliğin nasıl devre dışı bırakılır veya varsayılan davranışın nasıl `/MANIFESTUAC` değiştirilecek hakkında daha fazla bilgi için bkz.
- Bağlayıcı artık Windows `/DYNAMICBASE` Vista'nın Adres Alanı Düzeni Randomization özelliğini etkinleştirme seçeneğine sahiptir. This option modifies the header of an executable to indicate whether the application should be randomly rebased at load time.

## <a name="whats-new-for-c-in-visual-studio-2005"></a>Visual Studio 2005'te C++ Için Yenilikler

Visual C++ 2005 Service Pack 1'de aşağıdaki özellikler yeniydi:

### <a name="intrinsics-for-x86-and-x64"></a>X86 ve x64 için İçsel

- __halt
- __lidt
- __nop
- __readcr8
- __sidt
- __svm_clgi
- __svm_invlpga
- __svm_skinit
- __svm_stgi
- __svm_vmload
- __svm_vmrun
- __svm_vmsave
- __ud2
- __vmx_off
- __vmx_vmptrst
- __writecr8

### <a name="intrinsics-for-x64-only"></a>Sadece x64 için İçsel

- __vmx_on
- __vmx_vmclear
- __vmx_vmlaunch
- __vmx_vmptrld
- __vmx_vmread
- __vmx_vmresume
- __vmx_vmwrite

### <a name="new-language-keywords"></a>Yeni Dil Anahtar Kelimeleri

__sptr, __uptr

### <a name="new-compiler-features"></a>Yeni Derleyici Özellikleri

Derleyici bu sürümde değişiklikler kırma vardır.

- '64-bit yerli ve çapraz derleyiciler.
- `/analyze`(Kurumsal Kod Analizi) derleyici seçeneği eklendi.
- `/bigobj`derleyici seçeneği eklendi.
- `/clr:pure`, `/clr:safe`ve `/clr:oldSyntax` eklenmiştir. (Daha sonra Visual Studio 2015'te amortismana kattı ve Visual Studio 2017'de kaldırıldı.)
- Deprecated derleyici seçenekleri: birçok derleyici seçenekleri bu sürümde deprecated edilmiştir; daha fazla bilgi için **Deprecated Derleyici Seçenekleri'ne** bakın.
- Kodda `/clr` çift thunking azalır; daha fazla bilgi için **Double Thunking (C++) (C++)** bilgisine bakın.
- `/EH`(Özel Durum Taşıma `/EHs` Modeli) veya artık bir atış dışında bir şey ile yükseltilen bir özel durum yakalamak için kullanılamaz; kullanın. `/EHa`
- `/errorReport`(Report Internal Compiler Errors) derleyici seçeneği eklendi.
- `/favor`(64 için optimize edin) derleyici seçeneği eklendi.
- `/FA`, `/Fa` (Listeleme Dosyası) derleyici seçeneği eklendi.
- `/FC`(Tanılamada Kaynak Kod Dosyasının Tam Yolu) derleyici seçeneği eklendi.
- `/fp`(Kayan Nokta Davranışı Belirt) derleyici seçeneği eklendi.
- `/G`(İşlemci için Optimize Edin) Seçenekler derleyici seçeneği eklendi.
- `/G`(İşlemci için Optimize Edin) Seçenekler derleyici seçeneği eklendi.
- `/G3`, `/G4` `/G5`, `/G6` `/G7`, `/GB` , , ve derleyici seçenekleri kaldırıldı. Derleyici şimdi tüm mimariler için en iyi çıktı dosyasını oluşturmaya çalışan bir "karma model" kullanır.
- `/Gf`Kaldırıldı. Bunun `/GF` yerine (Yinelenen Dizeleri Ortadan Kaldır) kullanın.
- `/GL`(Tüm Program Optimizasyonu) artık `/CLRHEADER`.
- `/GR`artık varsayılan olarak açıktır.
- `/GS`(Arabellek Güvenlik Denetimi) artık güvenlik koruması sağlar. `/GS`artık varsayılan olarak açıktır. `/GS`şimdi de MSIL için `/clr` derlenmiş fonksiyonlar üzerinde çalışır (Ortak Dil Runtime Derleme).
- `/homeparams`(Register Parametrelerini Yığına Kopyala) derleyici seçeneği eklendi.
- `/hotpatch`(Hotpatchable Image oluştur) derleyici seçeneği eklendi.
- Satır satır işlevi buluşsal güncelleştirildi; daha fazla bilgi için **satır içinde**, **__inline,** **__forceinline** ve **inline_depth** bakın
- Birçok yeni içsel fonksiyonlar eklendi ve daha önce belgelenmemiş birçok içsel şimdi belgelenmiştir.
- Varsayılan olarak, başarısız olan yeni herhangi bir çağrı bir özel durum atar.
- `/ML`ve `/MLd` derleyici seçenekleri kaldırıldı. Visual C++ artık tek iş parçacığı, statik olarak bağlı CRT kitaplık desteğini desteklemez.
- `/O1`Derleyici, "Boyut `/O2` Küçültme, Hızı En Üst Düzeye Düzeye Çıkarma" (Genel Optimizasyonlar) `/Og` ve `/Ox` (Tam Optimizasyon) ile derlediğinizde etkinleştirilen Adlandırılmış İade Değeri Optimizasyonu'nu uygular.
- `/Oa`derleyici seçeneği kaldırıldı, ancak sessizce yoksayılır; `noalias` derleyicinin `restrict__declspec` diğer adı nasıl yaptığını belirtmek için veya değiştiricilerkullanın.
- `/Op`derleyici seçeneği kaldırılmıştı. Bunun `/fp` yerine kullanın (Kayan Nokta Davranışı belirtin).
- OpenMP artık Visual C++ tarafından desteklenir.
- `/openmp`(OpenMP 2.0 Desteği etkinleştir) derleyici seçeneği eklendi.
- `/Ow`derleyici seçeneği kaldırıldı, ancak sessizce yoksayılır. `noalias` Derleyicinin `restrict__declspec` diğer adı nasıl yaptığını belirtmek için veya değiştiricileri kullanın.

### <a name="profile-guided-optimizations"></a>Profil Temelli İyileştirmeler

- `/QI0f`Kaldırıldı.
- `/QIfdiv`Kaldırıldı.
- `/QIPF_B`(B CPU Stepping için Errata) derleyici seçeneği eklendi.
- `/QIPF_C`(C CPU Stepping için Errata) derleyici seçeneği eklendi.
- `/QIPF_fr32`(Üst 96 Kayan Nokta Kaydı Kullanmayın) derleyici seçeneği eklendi.
- `/QIPF_noPIC`(Pozisyon Bağımlı Kod Oluştur) derleyici seçeneği eklendi.
- `/QIPF_restrict_plabels`(Çalışma Zamanında İşlev Oluşturulmama) derleyici seçeneği eklendi.

### <a name="unicode-support-in-the-compiler-and-linker"></a>Derleyicide ve Bağlayıcıda Unicode Desteği

- `/vd`(Yapı Yer değiştirmelerini devre dışı) artık dynamic_cast Operatör'ü inşa edilen bir nesnede (/vd2) kullanmanıza olanak tanır
- `/YX`derleyici seçeneği kaldırıldı. Bunun `/Yc` yerine Kullanım (Önceden Derlenmiş `/Yu` Üstbilgi Dosyası Oluştur) veya (Önceden Derlenmiş Üstbilgi Dosyalarını Kullan) Yapı yapılandırmalarınızdan kaldırır `/YX` ve hiçbir şey ile değiştirirseniz, daha hızlı yapılara neden olabilir.
- `/Zc:forScope`artık varsayılan olarak açıktır.
- `/Zc:wchar_t`artık varsayılan olarak açıktır.
- `/Zd`derleyici seçeneği kaldırıldı. Satır numarası yalnızca hata ayıklama bilgileri artık desteklenmez. Bunun `/Zi` yerine (daha fazla bilgi için **/Z7, /Zi, /ZI (Hata Ayıklama Bilgi Biçimi)** kullanın).
- `/Zg`artık yalnızca C kaynak kodu dosyalarında geçerlidir ve C++ kaynak kodu dosyalarında geçerli değildir.
- `/Zx`(Hata Ayıklama Optimize Edilmiş Itanium Kodu) derleyici seçeneği eklendi.

### <a name="new-language-features"></a>Yeni Dil Özellikleri

- Öznitelik şimdi azat edilir.
- `appdomain__declspec`değiştirici eklendi.
- `__clrcall`çağırma sözleşmesi eklenmiştir.
- deprecated (C++) **declspec** değiştirici şimdi bir kullanıcı amortismana geçmiş bir sınıf veya işlev erişmeye çalıştığında, derleme zamanda görüntülenecek bir dize belirtmenize olanak sağlar.
- **dynamic_cast** Operatör değişiklikleri bozuyor.
- Yerel enumlar artık altta yatan türü belirtmenize olanak sağlar.
- `jitintrinsicdeclspec`değiştirici eklendi.
- `noaliasdeclspec`değiştirici eklendi.
- `process__declspec`değiştirici eklendi.
- **özet**, **geçersiz kılma**, ve **mühürlü** yerel derlemeler için geçerlidir.
- **__restrict** anahtar kelime eklendi.
- `restrictdeclspec`değiştirici eklendi.
- **__thiscall** artık bir anahtar kelime.
- **__unaligned** anahtar kelime şimdi belgelenmiştir.
- **volatile** (C++) optimizasyonlara ilişkin davranışı güncelleştirmiştir.

### <a name="new-preprocessor-features"></a>Yeni Önİşlemci Özellikleri

- __CLR_VER önceden tanımlanmış makro eklendi.
- Yorum (C/C++) pragma artık `/MANIFESTDEPENDENCY` bağlayıcı bir yorum olarak kabul eder. Yorum yapmak için exestr seçeneği şimdi azat edilir.
- `embedded_idl`öznitelik `#import` (Yönerge) şimdi isteğe bağlı bir parametre alır.
- `fenv_access`Pragma
- `float_control`Pragma
- `fp_contract`Pragma
- Pragma yönetilen, yönetilmeyen ve yönetilmeyen bölümlerde global değişkenler varsa, genel değişkenler, beyan edildikleri sırada başharfe atılamaz. Bu, örneğin, yönetilmeyen bir global değişken yönetilen bir global değişkenle baş harfe dönüşmüşse ve tam olarak oluşturulmuş yönetilen bir nesne gerekiyorsa, olası bir kesme değişikliğidir.
- init_seg belirtilen bölümler artık yalnızca okunur ve önceki sürümlerde olduğu gibi okuma/yazma değildir.
- inline_depth varsayılan şimdi 16' dır. Visual C++ .NET 2003'te de 16 varsayılan değer etkindi.
- önceden tanımlanmış makro ek_INTEGRAL_MAX_BITS bkz.
- _M_CEE, _M_CEE_PURE ve önceden tanımlanmış makrolar _M_CEE_SAFE bkz.
- _M_IX86_FP önceden tanımlanmış makro eklendi.
- _M_X64 önceden tanımlanmış makro eklendi.
- `make_public`Pragma
- `managed`, `unmanaged` pragma sözdizimi `push` güncellendi `pop`(şimdi var ve )
- mscorlib.dll artık tüm `#using` `/clr` derlemelerde Direktif tarafından dolaylı olarak başvurulmusur.
- önceden tanımlanmış _OPENMP makro eklendi.
- optimize pragma güncellendi, a ve w artık geçerli parametrelerdir.
- no_registry#alma özniteliği eklendi.
- `region`, `endregion` pragmas eklendi
- _VC_NODEFAULTLIB önceden tanımlanmış makro eklendi.
- Variadic Makrolar artık uygulanmaktadır.
- `vtordisp`amortismana alınır ve Visual C++'ın gelecekteki sürümünde kaldırılır.
- Pragma `warning` şimdi bastırma belirteç vardır.

### <a name="new-linker-features"></a>Yeni Bağlantı Özellikleri

- Modüllere (montaj dışı MSIL çıktı dosyaları) artık bağlayıcıya giriş olarak izin verilir.
- `/ALLOWISOLATION`(Manifest Lookup) bağlantı seçeneği eklendi.
- `/ASSEMBLYRESOURCE`(Yönetilen Kaynak Gömme) şimdi derlemede kaynağın adını belirtmenize ve kaynağın derlemede özel olduğunu belirtmenize olanak sağlayacak şekilde güncelleştirildi.
- `/CLRIMAGETYPE`(CLR Resim Türünü Belirt) bağlantı seçeneği eklendi.
- `/CLRSUPPORTLASTERROR`(PInvoke Aramaları için Son Hata Kodunu Koru) bağlantı seçeneği eklendi.
- `/CLRTHREADATTRIBUTE`(CLR İş Parçacığı Atföçlerini Ayarla) bağlantı seçeneği eklendi.
- `/CLRUNMANAGEDCODECHECK`(SuppressUnmanagedCodeSecurityAttribute ekle) bağlayıcı seçeneği eklendi.
- `/ERRORREPORT`(Report Internal Linker Hataları) bağlantı seçeneği eklendi.
- `/EXETYPE`bağlayıcı seçeneği kaldırıldı. Bağlayıcı artık Windows 95 ve Windows 98 aygıt sürücüleri oluşturmayı desteklemez. Bu aygıt sürücülerini oluşturmak için uygun bir DDK kullanın. EXETYPE anahtar kelimesi artık modül tanım dosyaları için geçerli değildir.
- `/FUNCTIONPADMIN`(Hotpatchable Image oluştur) bağlantı seçeneği eklendi.
- `/LTCG`linker seçeneği artık `/clr`derlenmiş modüllerde desteklenir. `/LTCG`profil güdümlü optimizasyonları destekleyecek şekilde de güncelleştirildi.
- `/MANIFEST`(Yan yana Montaj Bildirimi Oluştur) bağlantı seçeneği eklendi.
- `/MANIFESTDEPENDENCY`(Bildirim Bağımlılıklarını Belirt) bağlantı seçeneği eklendi.
- `/MANIFESTFILE`(Name Manifest File) bağlayıcı seçeneği eklendi.
- `/MAPINFO:LINES`bağlayıcı seçeneği kaldırıldı.
- `/NXCOMPAT`(Veri Yürütme Önleme ile uyumlu) bağlantı seçeneği eklendi.
- `/PGD`(Profil Güdümlü Optimizasyonlar için Veritabanı Belirt) bağlantı seçeneği eklendi.
- `/PROFILE`(Performans Araçları Profiler) bağlantı seçeneği eklendi.
- `/SECTION`(Bölüm Öznitelikleri belirt) bağlayıcı seçeneği artık öznitelik olumsuzlaması destekler ve artık L veya D (VxD ile ilgili) özniteliklerini desteklemez.
- Derleyicide ve Bağlayıcıda Unicode Desteği
- `/VERBOSE`(Yazdırma İlerleme İletileri) bağlantı seçeneği artık ICF ve REF'yi de kabul etmektedir.
- `/VXD`bağlayıcı seçeneği kaldırıldı. Bağlayıcı artık Windows 95 ve Windows 98 aygıt sürücüleri oluşturmayı desteklemez. Bu aygıt sürücülerini oluşturmak için uygun bir DDK kullanın. VXD anahtar kelimesi artık modül tanım dosyaları için geçerli değildir.
- `/WS`bağlayıcı seçeneği kaldırıldı. `/WS`Windows NT 4.0 için hedeflenen görüntüleri değiştirmek için kullanılmıştır. IMAGECFG.exe -R dosya adı yerine `/WS`kullanılabilir. IMAGECFG.exe, SUPPORT\DEBUG\I386\IMAGECFG adresindeki Windows NT 4.0 CD-ROM'da bulunabilir. Exe.
- `/WX`(Bağlayıcı Uyarılarını Hata Olarak Ele) bağlantı seçeneği artık belgelenmiştir.

### <a name="new-linker-utility-features"></a>Yeni Linker Yardımcı Özellikleri

- `/ALLOWISOLATION`editbin seçeneği eklenmiş
- TANIMI modülü tanımı dosya deyimi kaldırılır. Bağlayıcı artık sanal aygıt sürücüleri oluşturmayı desteklemiyor.
- `/ERRORREPORT`seçeneği bscmake.exe, dumpbin.exe, editbin.exe ve lib.exe eklenmiştir.
- `/LTCG`lib seçeneği eklendi.
- `/NXCOMPAT`editbin seçeneği eklendi.
- `/RANGE`dumpbin seçeneği eklendi.
- `/TLS`dumpbin seçeneği eklendi.
- `/WS`editbin seçeneği kaldırıldı. `/WS`Windows NT 4.0 için hedeflenen görüntüleri değiştirmek için kullanılmıştır. IMAGECFG.exe -R dosya adı yerine `/WS`kullanılabilir. IMAGECFG.exe, SUPPORT\DEBUG\I386\IMAGECFG adresindeki Windows NT 4.0 CD-ROM'da bulunabilir. Exe.
- /WX[:NO] lib seçeneği eklendi.

### <a name="new-nmake-features"></a>Yeni NMAKE Özellikleri

- `/ERRORREPORT`Eklenmiştir.
- `/G`Eklenmiştir.
- Önceden tanımlanmış kurallar güncelleştirildi.
- Özyineleme Makroları'nda belgelenen $(MAKE) makrosu artık nmake.exe'ye tam yol verir.

### <a name="new-masm-features"></a>Yeni MASM Özellikleri

- MASM ifadeleri artık 64 bit değerlerdir. Önceki sürümlerde MASM ifadeleri 32 bit değerleri ydi.
- Int 3'__asm yönergesi artık bir işlevin yerel olarak derlenmesine neden olur.
- ALIAS (MASM) artık belgelenmiştir.
- `/ERRORREPORT`ml.exe ve ml64.exe seçeneği eklenir.
- . FPO artık belgelenmiştir.
- H2INC.exe Visual C++ 2005'te gönderilmez. H2INC kullanmaya devam etmek gerekiyorsa, Visual C++'ın önceki sürümünden H2INC.exe'yi kullanın.
- işleç IMAGEREL eklendi.
- işletici HIGH32 eklendi.
- işletici LOW32 eklendi.
- ml64.exe x64 mimarisi için MASM bir sürümüdür. X64 .asm dosyalarını x64 nesne dosyalarına toplar. X64 derleyicisinde satır içinde montaj dili desteklenmez. Ml64.exe (x64) için aşağıdaki MASM direktifleri eklenmiştir:
- .ALLOCSTACK
- .ENDPROLOG
- .PUSHFRAME
- .PUSHREG
- .SAVEREG
- .SAVEXMM128
- . SETFRAME Ayrıca, PROC yönergesi yalnızca x64 sözdizimi ile güncelleştirildi.
- MMWORD yönergesi eklendi
- `/omf`(ML.exe komut satırı seçeneği) şimdi ima eder. `/c` ML.exe, OMF biçimnesneleri bağlamayı desteklemez.
- SEGMENT yönergesi artık ek öznitelikleri destekler.
- işleç SECTIONREL eklenmiştir.
- XMMWORD yönergesi eklendi

### <a name="new-crt-features"></a>Yeni CRT Özellikleri

- Çeşitli işlevlerin güvenli sürümleri eklendi. Bu işlevler hataları daha iyi bir şekilde işler ve sık karşılaşılan güvenlik hatalarını önlemeye yardımcı olmak için arabelleklerde daha sıkı denetimler uygular. Yeni güvenli sürümler **_s** soneki ile tanımlanır.
- Birçok işlevin varolan daha az güvenli sürümleri küçümsülmektedir. Amortisman uyarılarını devre dışı kalmak için _CRT_SECURE_NO_WARNINGS tanımlayın.
- Varolan birçok işlev artık parametrelerini doğrular ve geçersiz bir parametre geçirildiğinde geçersiz parametre işleyicisini çağırır.
- Varolan birçok `errno` işlev artık daha önce yapmadıkları yerde ayarlanır.
- Typein `errno_t` insalı typedef eklendi. `errno_t`bir işlev dönüş türü veya parametre hata kodları `errno`ile fırsatlar zaman kullanılır. `errno_t`yerini `errcode`alır.
- Yerele bağımlı işlevler artık geçerli yerel alanı kullanmak yerine yerel alanı parametre olarak alan sürümlere sahiptir. Bu yeni işlevler **_l** soneki vardır. Yerel nesnelerle çalışmak için birkaç yeni işlev eklendi. Yeni işlevler `_create_locale` `_free_locale`içerir `_get_current_locale`ve .
- Dosya tutamaçlarının kilitlenmesini ve kilidini açmak için yeni işlevler eklendi.
- İşlevler ailesi, `_spawn` önceki sürümlerde olduğu gibi errno'yu başarıda sıfırlamıyor.
- Bağımsız değişkenlerin kullanıldığı sırayı belirtmenize olanak tanıyan `printf` işlevler ailesinin sürümleri kullanılabilir.
- Unicode artık desteklenen bir metin biçimidir. İşlev `_open` _O_TEXTW, _O_UTF8 ve _O_UTF16 öznitelikleri destekler. İşlev, `fopen` Unicode biçimini belirtmenin "ccs=ENCODING" yöntemini destekler.
- Yönetilen kodda (MSIL) yerleşik CRT kitaplıklarının yeni bir sürümü artık `/clr` kullanılabilir ve (Ortak Dil Çalışma Süresi Derlemesi) seçeneğiyle derlenirken kullanılır.
- _fileinfo kaldırıldı.
- Varsayılan `time_t` boyut şimdi 64 bit, hangi aralığı genişletir `time_t` ve zaman birkaç yıl 3000 dışarı işlevleri.
- CRT artık yerel ayarları iş parçacığı bazında desteklemektedir. İşlev `_configthreadlocale` bu özelliği desteklemek için eklendi.
- X87 `_statusfp2` ve `__control87_2` SSE2 kayan nokta işlemcisi üzerindeki kayan nokta kontrol sözcüğüne erişim ve denetim sağlamak için işlevler eklendi.
- Ve `_mkgmtime` `_mkgmtime64` işlevler greenwich Ortalama Saati (GMT) için dönüştürme süreleri (struct tm) desteği sağlamak için eklendi.
- Standartta daha `swprintf` `vswprintf` iyi uyum sağlamak ve bunlara daha uygun değişiklikler yapıldı.
- Yeni bir başlık dosyası, INTRIN. H, bazı içsel fonksiyonlar için prototip sağlar.
- İşlev `fopen` şimdi bir N özniteliği vardır.
- İşlev `_open` şimdi _O_NOINHERIT bir özniteliği vardır.
- İşlev `atoi` şimdi INT_MAX `errno` döndürür ve taşma da ERANGE ayarlar. Önceki sürümlerde, taşma davranışı tanımsızdı.
- İşlevler ailesi, `printf` %a ve %A biçim türü belirteçleri kullanılarak ANSI C99 standardına göre uygulanan hexadecimal kayan nokta çıktısını destekler.
- Aile `printf` artık "ll" (uzun) boyut önekini destekler.
- İşlev `_controlfp` daha iyi performans için optimize edilmiştir.
- Bazı işlevlerin hata ayıklama sürümleri eklendi.
- Eklendi `_chgsignl` `_cpysignl` ve (uzun çift sürümleri).
- Tür `_locale_t` tablosuna yazı türü eklendi.
- Yeni `_countof` makro Makro bir dizi elemanlarının bilgisayar sayısı için eklendi.
- Her işlev konusuna .NET Framework eşdeğerleri ile ilgili bir bölüm eklenmiştir.
- Çeşitli dize işlevleri artık çıkış arabellekleri çok küçük olduğunda başarısız olmak yerine dizeleri kesilen seçeneğine sahiptir; **_TRUNCATE**bakın.
- `_set_se_translator`şimdi derleyici seçeneğinin `/EHa` kullanımını gerektirir.
- `fpos_t`**(C** kodu `/Za` için) ve __STDC__ el ile ayarlandığında (C++ kodu için) __int64. Eskiden bir **yapıya**ait.
- _CRT_DISABLE_PERFCRIT_LOCKS tek iş parçacığı programlarının G/Ç performansını artırabilir.
- POSIX adları ISO C++ uyumlu adları lehine amortismana uğramamıştır `getch`(örneğin, yerine kullanın). `_getch`
- Yeni bağlantı seçenekleri .obj dosyaları saf modu için kullanılabilir
- `_recalloc`özelliklerini birleştirir `realloc` `calloc`ve .

## <a name="whats-new-for-c-in-visual-studio-2003"></a>Visual Studio 2003'te C++ Için Yenilikler

### <a name="compiler"></a>Derleyici

- Geçerli sürümün derleyicisi ile çalışma zamanının önceki sürümünde oluşturulmuş C++ uygulaması için Yönetilen Uzantıların nasıl çalıştırılacaklarına ilişkin bilgiler.
- C++ Sık Sorulan Sorular için Yönetilen Uzantılar.
- C++: Walkthrough: Varolan Bir Yerel C++ Uygulamasını .NET Framework Bileşenleri yle birlikte çalıştırmak üzere taşıma için Yönetilen Uzantıları kullanmak için varolan, yerel bir uygulamayı nasıl kilitlendireceklerini gösteren bir izlenme eklendi.
- Artık değer türünde bir yöntem de bir temsilci oluşturabilirsiniz.
- Derleyicinin C++ standardına uygunluğu Visual C++ .NET 2003 için önemli ölçüde geliştirilmiştir.
- `/arch`derleyici seçeneği eklenir.
- `/Gf`amortismana alınır ve Visual C++'ın bir sonraki sürümünde kaldırılır.
- `/G7`derleyici seçeneği eklenir.
- Derleyici seçeneği, `/GS` yerel değişkenlerin doğrudan arabellek taşmaları korunmasına yardımcı olmak için geliştirilmiştir.
- Derleyici `/noBool` seçeneği kaldırıldı. Derleyici artık **bool'un** C++ kaynak kod dosyasında yalnızca bir anahtar kelime (tanımlayıcı olarak değil) olarak görünmesini sağlar.
- **Uzun uzun** tip artık **crt** uzun **uzun** için henüz destek olmadığını __int64 Not bir **typedef** olarak kullanılabilir.
- Derleyici `/Zm` seçeneği şimdi önceden derlenmiş üstbilgi bellek ayırma sınırını belirtir.
- _InterlockedCompareExchange şimdi belgelenmiş.
- _InterlockedDecrement şimdi belgelenmiş.
- _InterlockedExchange şimdi belgelenmiş içsel.
- _InterlockedExchangeAdd şimdi belgelenmiştir.
- _InterlockedIncrement şimdi belgelenmiştir.
- _ReadWriteBarrier içsel ekledi.

### <a name="attributes"></a>Öznitelikler

- `implements`öznitelik artık belgelenmiştir.

### <a name="linker-features"></a>Bağlayıcı özellikleri

Aşağıdaki bağlayıcı anahtarları eklendi:

- /ASSEMBLYDEBUG
- /ASSEMBLYLINKRESOURCE
- DELAYSIGN
- /KEYFILE
- /KEYCONTAINER
- /SAFESEH

### <a name="masm"></a>MASM

Şey. SAFESEH direktifi ve `/safeseh` ml.exe seçeneği eklendi.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)
