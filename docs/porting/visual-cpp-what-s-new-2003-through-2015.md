---
title: Visual C++ &#39;s yeni 2003 ile 2015 arasında
ms.date: 07/02/2019
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
ms.openlocfilehash: 6a3db2c9af2bcd9201f696756053cedb0788571a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510307"
---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Visual C++ &#39;s yeni 2003 ile 2015 arasında

Bu sayfa, Visual Studio 2015 ' deki tüm Visual C++ sürümleri için "yenilikler" sayfalarını 2003 ' e geri toplar. Bu bilgiler, Visual Studio 'nun önceki sürümlerinden yükseltirken yararlı olabilecek bir kolaylık olması durumunda sunulmaktadır.

> [!NOTE]
> Visual Studio 'nun geçerli sürümü hakkında daha fazla bilgi için bkz. Visual Studio ['Daki Visual C++ Studio](../overview/what-s-new-for-visual-cpp-in-visual-studio.md) yenilikleri ve Visual [Studio 'da Visual C++ Studio uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md).

## <a name="whats-new-for-c-in-visual-studio-2015"></a>Visual Studio 2015 C++ ' deki yenilikler

Visual Studio 2015 ve üzeri sürümlerde, derleyici uyumsuzluğuna yönelik sürekli geliştirmeler bazen derleyicinin mevcut kaynak kodunuzu nasıl anladığını değiştirebilir. Bu durumda, derlemeniz sırasında yeni veya farklı hatalarla karşılaşabilirsiniz, hatta daha önce oluşturulmuş ve daha önce doğru şekilde çalışacak şekilde çalışan kodda davranış farklılıkları yaşayabilirsiniz.

Neyse ki, bu farkların çoğu kaynak kodunuzun büyük bir etkisi yoktur ve bu farklılıklara yönelik kaynak kodu veya başka değişiklikler gerektiğinde, düzeltmeler genellikle küçük ve düz ileri ' dir. Daha önceden kabul edilebilir kaynak kodu örnekleri, değiştirilmesi gerekebilecek *(önce)* ve bunları düzeltmek için düzeltmeler (daha *sonra)* ekledik.

Bu farklılıklar, kaynak kodunuzu veya diğer yapı yapıtlarınızı etkileyebilse de, Visual C++ sürümlerindeki güncelleştirmeler arasındaki ikili uyumluluğu etkilemez. Daha ciddi bir değişiklik türü, önemli *değişiklik* ikili uyumluluğu etkileyebilir, ancak bu tür ikili uyumluluk sonlarının yalnızca görselin C++ana sürümleri arasında meydana gelir. Örneğin, Visual C++ 2013 ile Visual C++ 2015 arasında. Visual C++ 2013 ve Visual C++ 2015 arasında oluşan önemli değişiklikler hakkında daha fazla bilgi için bkz. [görsel C++ değişiklik geçmişi 2003-2015](../porting/visual-cpp-change-history-2003-2015.md).

- [Visual Studio 2015 uyumluluk geliştirmeleri](#VS_RTM)

- [Visual Studio 2015 güncelleştirme 1 ' deki uyumluluk geliştirmeleri](#VS_Update1)

- [Visual Studio 2015 güncelleştirme 2 ' deki uyumluluk geliştirmeleri](#VS_Update2)

- [Visual Studio 2015 güncelleştirme 3 ' te uyumluluk geliştirmeleri](#VS_Update3)

### <a name="VS_RTM"></a>Visual Studio 2015 uyumluluk geliştirmeleri

- **/Zc: forScope-seçenek**

   Derleyici seçeneği `/Zc:forScope-` kullanımdan kaldırılmıştır ve gelecek sürümde kaldırılacaktır.

   ```output
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release
   ```

   Bu seçenek genellikle, standart olarak, kapsam dışı bir noktaya göre döngü değişkenlerini kullanan standart olmayan koda izin vermek için kullanılır. Yalnızca `/Za` seçeneği ile derlerken, `/Za`döngünün sonuna kadar bir for döngüsü değişkeninin kullanılması her zaman izin verilir. Standartlara uygunluğu konusunda endişelenmezseniz (örneğin, kodunuz diğer derleyicilere taşınabilir değilse), `/Za` seçeneğini kapatabilir (veya **dil uzantılarını devre dışı bırak** özelliğini **Hayır**olarak ayarlayabilirsiniz). Taşınabilir, standartlara uyumlu kod yazma konusunda dikkatli değilseniz, bu tür değişkenlerin bildirimini döngü dışındaki bir noktaya taşıyarak, kodunuzu standart olacak şekilde yeniden yazmanız gerekir.

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

   `/Zg` Derleyici seçeneği (işlev prototipleri üret) artık kullanılamıyor. Bu derleyici seçeneği daha önce kullanım dışıdır.

- Artık, MSTest. exe ile komut satırından C++/CLI ile birim testlerini çalıştıramazsınız. Bunun yerine, VSTest. Console. exe ' yi kullanın

- **kesilebilir anahtar sözcüğü.**

   Daha önce hata olmadan derlenen konumlarda **kesilebilir** depolama sınıfı belirticisine artık izin verilmez. Artık derleyici hata C2071 (Geçersiz depolama sınıfı) veriyor. Standart olarak, kesilebilir tanımlayıcı yalnızca sınıf veri üyelerinin adlarına uygulanabilir ve const veya static olarak belirtilen adlara uygulanamaz ve başvuru üyelerine uygulanamaz.

   Örneğin, aşağıdaki kodu göz önünde bulundurun:

   ```cpp
    struct S {
        mutable int &r;
    };
   ```

   Microsoft C++ derleyicisinin önceki sürümleri bunu kabul etti, ancak artık derleyici şu hatayı veriyor:

   ```Output
    error C2071: 'S::r': illegal storage class
   ```

   Hatayı onarmak için, gereksiz **kesilebilir** anahtar sözcüğünü kaldırmanız yeterlidir.

- **char_16_t ve char32_t**

   Bu türler artık yerleşik olarak `char16_t` değerlendirildiğinden, bir typedef içinde artık diğer adlar kullanılamaz `char32_t` . Kullanıcılar ve kitaplık yazarlarının, `char16_t` sırasıyla ve `uint32_t`' nin `uint16_t` diğer adlarını `char32_t` tanımlamak için yaygındır.

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

   Kodunuzu güncelleştirmek için, **typedef** bildirimlerini kaldırın ve bu adlarla çakışan diğer tanımlayıcıları yeniden adlandırın.

- **Tür olmayan şablon parametreleri**

   Tür olmayan şablon parametreleri içeren bazı kodlar artık açık şablon bağımsız değişkenleri sağladığınızda tür uyumluluğu için doğru denetlenir. Örneğin, aşağıdaki kod Visual C++'ın önceki sürümlerinde hata olmadan derlendi.

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

   Şablon parametre türü şablon bağımsız değişkeniyle eşleşmediğinden geçerli derleyici doğru bir hata verir (parametre bir const üyesinin işaretçisi, ancak f işlevi const değil):

   ```Output
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'
   ```

   Kodunuzda bu hatayı gidermek için kullandığınız şablon bağımsız değişkeninin türünün şablon parametresinin belirtilen türüyle eşleştiğinden emin olun.

- **__declspec (align)**

   Derleyici artık işlevlerde kabul `__declspec(align)` etmez. Bu her zaman yoksayıldı, ancak şimdi bir derleyici hatası veriyor.

   ```cpp
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations
   ```

   Bu sorunu gidermek için, işlev `__declspec(align)` bildiriminden kaldırın. Hiçbir etkisi olmadığından, kaldırma hiçbir şeyi değiştirmez.

- **Özel durum işleme**

   Özel durum işlemede birkaç değişiklik vardır. İlk olarak, özel durum nesnelerinin kopyalanabilir veya taşınabilir olması gerekir. Aşağıdaki kod Visual Studio 2013 derlendi, ancak Visual Studio 2015 ' de derlenmiyor:

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

   Bu sorun, kopya oluşturucusunun özel olması, bu nedenle bir özel durumu işlemek için normal bir şekilde nesne kopyalanamaz. Kopya Oluşturucu **Açık**olarak bildirildiğinde aynı durum geçerlidir.

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

   Kodunuzu güncelleştirmek için, özel durum nesnenizin kopya oluşturucusunun ortak olduğundan ve **Açık**olarak işaretlenmemiş olduğundan emin olun.

   Bir özel durumu değere göre yakalamak Ayrıca özel durum nesnesinin kopyalanabilir olmasını gerektirir. Aşağıdaki kod Visual Studio 2013 derlendi, ancak Visual Studio 2015 ' de derlenmiyor:

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

   **Catch** için parametre türünü bir başvuruya dönüştürerek bu sorunu çözebilirsiniz.

   ```cpp
    catch(D& d)
    {
    }
   ```

- **Dize sabit değerleri ve ardından makrolar**

   Derleyici artık Kullanıcı tanımlı değişmez değerleri desteklemektedir. Sonuç olarak, herhangi bir boşluk olmadan makro tarafından izlenen dize sabit değerleri, Kullanıcı tanımlı değişmez değerler olarak yorumlanır ve bu da hata veya beklenmedik sonuçlar doğurabilir. Örneğin, önceki derleyicilerde aşağıdaki kod başarıyla derlendi:

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

   Derleyici bunu bir "Hello" dize sabit değeri olarak, ardından "burada" genişletilmiş olan ve iki dize sabit değerinin bir tane ile bitiştirildiği bir makro tarafından yorumlanıyor. Visual Studio 2015 ' de derleyici bunu Kullanıcı tanımlı bir değişmez değer olarak yorumlar, ancak eşleşen bir Kullanıcı tanımlı sabit değer _X tanımlanmadığı için bir hata verir.

   ```cpp
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found
    note: Did you forget a space between the string literal and the prefix of the following string literal?

   ```

   Bu sorunu gidermek için, dize sabiti ve makro arasına bir boşluk ekleyin.

- **Bitişik dize sabit değerleri**

   Benzer şekilde, dize ayrıştırması içindeki ilgili değişiklikler nedeniyle, herhangi bir boşluk olmadan bitişik dize değişmez değerleri (geniş veya dar karakter dizesi değişmez değerleri), daha önceki Vizaul C++sürümlerinde tek bir birleştirilmiş dize olarak yorumlanmıştı. Visual Studio 2015 ' de, artık iki dize arasına boşluk eklemeniz gerekir. Örneğin, aşağıdaki kod değiştirilmelidir:

   ```cpp
    char * str = "abc""def";
   ```

   Yalnızca iki dize arasına bir boşluk ekleyin.

   ```cpp
    char * str = "abc" "def";
   ```

- **Yeni yerleştirme ve silme**

   C++ 14 standardı ile uyumlu hale getirmek için **Delete** işlecinde bir değişiklik yapılmıştır. Standartlar değişikliğinin ayrıntıları, [ C++ boyutu kaldırma](https://isocpp.org/files/papers/n3778.html)sırasında bulunabilir. Değişiklikler, bir boyut parametresi alan Global **Delete** işlecinin bir formunu ekler. Son değişiklik, daha önce aynı imzaya sahip bir işleç **silme** işlemi kullanıyorsanız ( **Yeni bir yerleştirme** işlecine karşılık gelmesi için), bir derleyici hatası (C2956, **yerleştirme yeni bir noktada gerçekleşen** , derleyicinin uygun eşleşen **silme** işlecini belirlemeyi denediği koddaki konum olduğundan, kullanılır.

   İşlev `void operator delete(void *, size_t)` , c++ 11 ' deki **yerleştirme yeni** işlevine `void * operator new(size_t, size_t)` karşılık gelen bir **yerleşim silme** işleçiydi. C++ 14 boyutunda ayırmayı kaldırma ile, bu **Delete** işlevi artık *olağan bir ayırmayı kaldırma işlevidir* (Global **Delete** işleci). Standart, **Yeni bir yerleşim** kullanılması karşılık gelen bir **silme** işlevini arar ve normal bir ayırmayı kaldırma işlevi bulursa programın hatalı biçimlendirilmiş olması gerekir.

   Örneğin, kodunuzun hem **yerleştirmesini** hem de bir **yerleşimi silmeyi**tanımladığını varsayalım:

   ```cpp
    void * operator new(std::size_t, std::size_t);
    void operator delete(void*, std::size_t) noexcept;
   ```

   Bu sorun, tanımladığınız bir **yerleşim silme** işleci ve yeni global boyutlu **silme** işleci arasındaki işlev imzalarındaki eşleşme nedeniyle oluşur. Herhangi bir `size_t` **yerleştirme New** ve **Delete** işleçleri için dışında farklı bir tür kullanıp kullanmayacağınızı göz önünde bulundurun.  `size_t` **Typedef** türünün derleyiciye bağlı olduğunu ve Visual C++'teki **işaretsiz int** için bir **typedef** olduğunu unutmayın. İyi bir çözüm, şöyle bir numaralandırılmış tür kullanmaktır:

   ```cpp
    enum class my_type : size_t {};
   ```

   Ardından, **Yeni** yerleştirme tanımınızı değiştirin ve bu türü, `size_t`yerine ikinci bağımsız değişken olarak kullanmak için silin. Ayrıca yeni bir türü geçirmek (örneğin, tam sayı değerinden dönüştürmek için kullanarak `static_cast<my_type>` ) ve **Yeni** ve **silme** tanımını tam sayı türüne dönüştürmek için yeni yerleştirme için yapılan çağrıları güncelleştirmeniz gerekir. Bunun için bir **enum** kullanmanız gerekmez; `size_t` üye içeren bir sınıf türü de çalışır.

   Alternatif bir çözüm de **yeni yerleşimi** tamamen ortadan kaldırabilmeyebilirsiniz. Kodunuz, yerleştirme bağımsız değişkeninin ayrılan veya Silinen nesnenin boyutu olduğu bir bellek havuzunu uygulamak için **yeni yerleştirme** kullanıyorsa, boyutu kaldırma özelliği kendi özel bellek havuzu kodunuzu değiştirmek için uygun olabilir ve şu şekilde kurtulabilen yerleştirme işlevleri ve yerleştirme işlevleri yerine kendi iki bağımsız değişkenli **silme** işlecini kullanın.

   Kodunuzu hemen güncelleştirmek istemiyorsanız, derleyici seçeneğini `/Zc:sizedDealloc-`kullanarak eski davranışa dönüştürebilirsiniz. Bu seçeneği kullanırsanız, iki bağımsız değişken **silme** işlevi yoktur ve **yerleştirme silme** işleçle bir çakışmaya neden olmaz.

- **Birleşim veri üyeleri**

   Birleşimlerin veri üyeleri artık başvuru türlerine sahip olamaz. Aşağıdaki kod Visual Studio 2013 içinde başarıyla derlendi, ancak Visual Studio 2015 ' de hata veriyor.

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

   Yukarıdaki kod aşağıdaki hataları üretir:

   ```Output
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type
   ```

   Bu sorunu gidermek için başvuru türlerini bir işaretçiye ya da değere değiştirin. Türü bir işaretçi olarak değiştirmek, birleşim alanını kullanan kodda değişiklik yapılmasını gerektirir. Kodu bir değere değiştirmek, birleşimde depolanan verileri değiştirecek, bu da birleşim türlerindeki alanlar aynı belleği paylaştığından diğer alanları etkiler. Değerin boyutuna bağlı olarak, birleşim boyutunu da değiştirebilir.

- **Anonim birleşimler**

   artık standart için daha uyumlu. Derleyicinin önceki sürümleri anonim birleşimler için açık bir Oluşturucu ve yıkıcı oluşturdu. Bunlar Visual Studio 2015 ' de silinir.

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

   Yukarıdaki kod, Visual Studio 2015 ' de aşağıdaki hatayı üretir:

   ```cpp
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here
   ```

   Bu sorunu çözmek için oluşturucuya ve/veya yıkıcıya ait tanımlarınızı belirtin.

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

- **Anonim yapılar içeren birleşimler**

   Standart ile uyumlu olması için, Birleşimlerdeki anonim yapıların üyeleri için çalışma zamanı davranışı değişmiştir. Bir Union içindeki anonim yapı üyeleri için Oluşturucu artık böyle bir birleşim oluşturulduğunda örtük olarak çağrılmaz. Ayrıca, birleşim kapsam dışına geçtiğinde, bir Union içindeki anonim yapı üyeleri için yıkıcı artık örtük olarak çağrılmaz. Bir UNION U 'nın yok edicisi olan adlandırılmış bir yapı olan bir üyeyi içeren anonim bir yapı içerdiği aşağıdaki kodu göz önünde bulundurun.

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

   Visual Studio 2013 ' de, birleşim oluşturulduğunda for için oluşturucu çağrılır ve f işlevi için yığın temizlendiğinde, for için yıkıcısı çağrılır. Ancak Visual Studio 2015 ' de, Oluşturucu ve yıkıcısı çağrılmaz. Derleyici bu davranış değişikliği hakkında bir uyarı verir.

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

   Alternatif olarak, oluşturucuyu ve yıkıcı kodu yeni işlevlere taşımayı deneyin ve birleşim için oluşturucudan ve yıkıcıdan bu işlevlere çağrı ekleyin.

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

   Şablonların ad çözümlemesinde değişiklikler yapılmıştır. ' C++De, bir adın çözümlenme adaylarını düşünürken, olası eşleşmeler olarak dikkate alınması gereken bir veya daha fazla ad geçersiz bir şablon örneği oluşturuyor olabilir. Bu geçersiz örneklemeler normalde, SFINAE olarak bilinen bir ilke olan (değiştirme hatası bir hata değil) derleyici hatalarına neden olmaz.

   Şimdi, SFINAE derleyicinin bir sınıf şablonunun özelleştirimini örneğini oluşturmak isterse, bu işlem sırasında oluşan hatalar derleyici hatalardır. Önceki sürümlerde, derleyici bu tür hataları yoksayar. Örneğin, aşağıdaki kodu göz önünde bulundurun:

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

   Geçerli derleyici ile derlerseniz, şu hatayı alırsınız:

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

   Bunun nedeni, is_base_of sınıfının ilk çağırma noktasında henüz tanımlanmamıştır.

   Bu durumda, bu, sınıf tanımlanmadığı sürece bu tür nitelikleri kullanmaz. B ve D tanımlarını kod dosyasının başlangıcına taşırsanız, hata çözülür. Tanımlar üst bilgi dosyalarında ise, herhangi bir sınıf tanımının sorunlu şablonlar kullanılmadan önce derlendiğinden emin olmak için, üst bilgi dosyalarına dahil etme deyimlerinin sırasını kontrol edin.

- **Kopya oluşturucular**

   Hem Visual Studio 2013 hem de Visual Studio 2015 ' de, derleyici Kullanıcı tanımlı bir taşıma oluşturucusuna sahipse ancak kullanıcı tanımlı kopya Oluşturucusu yoksa bir sınıf için bir kopya Oluşturucu oluşturur. Dev14 ' de, örtülü olarak oluşturulan bu kopya Oluşturucusu Ayrıca "= Delete" olarak işaretlenir.

### <a name="VS_Update1"></a>Visual Studio 2015 güncelleştirme 1 ' deki uyumluluk geliştirmeleri

- **Özel sanal temel sınıflar ve dolaylı devralma**

   Derleyicinin önceki sürümleri, türetilmiş bir sınıfın *dolaylı olarak türetilmiş* `private virtual` temel sınıfların üye işlevlerini çağırmasını sağlar. Bu eski davranış yanlıştı ve C++ standart ile uyumlu değil. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve sonuç olarak derleyici hatası C2280 yayınlar.

   ```Output
    error C2280: 'void *S3::__delDtor(unsigned int)': attempting to reference a deleted function
   ```

   Örnek (önce)

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

   Örnek (sonrasında)

   ```cpp
    class base;  // as above

    class middle: protected virtual base {};
    class top: public virtual middle {};

    void destroy(top *p)
    {
        delete p;
    }
   ```

  \-veya

   ```cpp
    class base;  // as above

    class middle: private virtual base {};
    class top: public virtual middle, private virtual bottom {};

    void destroy(top *p)
    {
        delete p;
    }
   ```

- **Yeni işleç New ve delete işleci**

   Derleyicinin önceki sürümleri, üyenin üye olmayan **işlecine** ve üyenin statik olarak bildirilmesini ve genel ad alanından farklı ad alanlarında bildirilmesine izin verilir.  Bu eski davranış, programın programladığı **Yeni** veya **silme** işletmeni uygulamasını çağırmayacağı ve sessiz bozuk çalışma zamanı davranışına neden olan bir risk oluşturdu. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve bunun yerine derleyici hatası C2323 yayınlar.

   ```Output
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace.
   ```

   Örnek (önce)

   ```cpp
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323
   ```

   Örnek (sonrasında)

   ```cpp
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'
   ```

   Ayrıca, derleyici belirli bir tanılama sunmasa da, yeni satır içi işleç hatalı biçimlendirilmiş olarak kabul edilir.

- **Sınıf olmayan türlerde ' operator *Type*() ' (Kullanıcı tanımlı dönüştürme) çağrısı** yapılıyor derleyicinin önceki sürümleri ' işleç *türü*() ', sessizce yoksayma sırasında sınıf olmayan türlerde çağrılabilir. Bu eski davranış sessiz hatalı kod oluşturma riskini oluşturdu, bu durum öngörülemeyen çalışma zamanı davranışına neden oldu. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve bunun yerine derleyici hatası C2228 yayınlar.

   ```Output
    error C2228: left of '.operator type' must have class/struct/union
   ```

   Örnek (önce)

   ```cpp
    typedef int index_t;

    void bounds_check(index_t index);

    void login(int column)
    {
        bounds_check(column.operator index_t());  // error C2228
    }
   ```

   Örnek (sonrasında)

   ```cpp
    typedef int index_t;

    void bounds_check(index_t index);

    void login(int column)
    {
         bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'
    }
   ```

- **Ayrıntılı tür tanımlayıcıda gereksiz TypeName**  Derleyicinin önceki sürümlerinde ayrıntılı tür tanımlayıcılarında **TypeName** izni verilir; Bu şekilde yazılan kod anlam yanlış olur. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve bunun yerine derleyici hatası C3406 yayınlar.

   ```Output
    error C3406: 'typename' cannot be used in an elaborated type specifier
   ```

   Örnek (önce)

   ```cpp
    template <typename class T>
    class container;
   ```

   Örnek (sonrasında)

   ```cpp
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case
    class container;
   ```

- **Bir başlatıcı listesinden dizilere ait tür kesintisi**  Derleyicinin önceki sürümleri Başlatıcı listesinden dizilerin tür kesintiyi desteklemiyor. Derleyici artık bu tür kesintiyi destekler ve sonuç olarak, başlatıcı listeleri kullanılarak işlev şablonlarına yapılan çağrılar artık belirsiz olabilir veya derleyicinin önceki sürümlerinden farklı bir aşırı yükleme seçilebilir. Bu sorunları çözmek için program artık programcı tarafından hedeflenen aşırı yüklemeyi açıkça belirtmelidir.

   Bu yeni davranış, aşırı yük çözümüne geçmiş aday kadar eşit olan ek bir aday göz önünde bulundurmasına neden olursa, çağrı belirsiz hale gelir ve derleyici sonuç olarak derleyici hatası C2668 yayınlar.

   ```Output
    error C2668: 'function' : ambiguous call to overloaded function.
   ```

   Örnek 1: Aşırı yüklenmiş işleve belirsiz çağrı (önce)

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

   Örnek 1: aşırı yüklenmiş işleve belirsiz çağrı (sonrasında)

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

   Bu yeni davranış, aşırı yüklenmiş adayından daha iyi eşleşen ek bir aday göz önünde bulundurmasına neden olduğunda, çağrı yeni aday için kesin bir şekilde çözümlenir ve büyük olasılıkla, bir program davranışından farklı Programcı amaçlanıyor.

   Örnek 2: aşırı yükleme çözünürlüğünde değişiklik (önce)

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

   Örnek 2: aşırı yükleme çözünürlüğünde değişiklik (sonrasında)

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

- **Switch ifadesinin uyarılarını geri yükleme**

   Derleyicinin önceki bir sürümü, **Switch** deyimleriyle ilgili önceden var olan uyarıları kaldırdı; Bu uyarılar artık geri yüklendi. Derleyici artık geri yüklenen uyarıları verir ve belirli durumlar (varsayılan durum dahil) ile ilgili uyarılar artık switch ifadesinin son satırı yerine sorunlu durumu içeren satıra çıkarılır. Artık bu uyarıların geçmiş dışında farklı satırlarda verilmesi sonucunda, daha önce kullanılarak `#pragma warning(disable:####)` gizlenen uyarılar amaçlanan şekilde gizlemeyebilir. Bu uyarıların istendiği şekilde görüntülenmesini sağlamak için, `#pragma warning(disable:####)` yönergeyi ilk olası olay durumunun üzerindeki bir satıra taşımak gerekebilir. Geri yüklenen uyarılar aşağıda verilmiştir.

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

   C4063 (öncesi) örneği

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

   Diğer geri yüklenen uyarıların örnekleri belgelerde verilmiştir.

- **#include: PathName 'teki '.. ' üst dizin belirticisinin kullanımı** (yalnızca etkiler `/Wall`) `/WX`

   Derleyicinin önceki sürümleri, '.. ' üst dizin belirticisinin kullanımını algılamadı `#include` yönergelerinin yol. Bu şekilde yazılan kod, genellikle proje ile ilgili yollar kullanarak proje dışında var olan üst bilgilerin dahil edilmesine yöneliktir. Bu eski davranış, programın, programcı tarafından amaçlanan farklı bir kaynak dosyası ekleyerek derlenebilecek veya bu göreli yolların diğer derleme ortamlarına taşınmayan bir risk oluşturdu. Derleyici artık kod Programlayıcısının bu şekilde yazıldığını algılar ve bildirir ve etkinleştirilirse isteğe bağlı bir derleyici uyarısı C4464 yayınlar.

   ```Output
    warning C4464: relative include path contains '..'
   ```

   Örnek (önce)

   ```cpp
    #include "..\headers\C4426.h"  // emits warning C4464
   ```

   Örnek (sonrasında)

   ```cpp
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories
   ```

   Ayrıca, derleyici belirli bir tanılama sunmasa da ".." üst dizin belirticisinin, projenizin içerme dizinlerini belirtmek için kullanılması gerektiğini de öneririz.

- **#pragma optimize () üst bilgi dosyasının son sonunu genişletiyor** (yalnızca etkiler `/Wall`) `/WX`

   Önceki derleyicinin sürümleri, bir çeviri birimi içinde yer alan bir üst bilgi dosyası ile çıkış yapan iyileştirme bayrağı ayarlarında yapılan değişiklikleri algılamadı. Derleyici artık, kod programcısında bu şekilde yazılmış kodu algılar ve bildirir ve etkinleştiriliyorsa, soruna `#include`neden olan isteğe bağlı bir derleyici uyarısı C4426 yayınlar. Bu uyarı yalnızca, derleyici için komut satırı bağımsız değişkenleri tarafından ayarlanan iyileştirme bayraklarıyla çakışırsa değişiklikler yapılır.

   ```Output
    warning C4426: optimization flags changed after including header, may be due to #pragma optimize()
   ```

   Örnek (önce)

   ```cpp
    // C4426.h
    #pragma optimize("g", off)
    ...
    // C4426.h ends

    // C4426.cpp
    #include "C4426.h"  // warning C4426
   ```

   Örnek (sonrasında)

   ```cpp
    // C4426.h
    #pragma optimize("g", off)
    ...
    #pragma optimize("", on)  // restores optimization flags set via command-line arguments
    // C4426.h ends

    // C4426.cpp
    #include "C4426.h"
   ```

- **Eşleşmeyen #pragma warning (push)** ve **#pragma warning (pop)** (yalnızca etkiler `/Wall`) `/WX`

   Derleyicinin önceki sürümleri, farklı bir kaynak dosyadaki `#pragma warning(push)` `#pragma warning(pop)` durum değişiklikleriyle eşleştirmekte olan durum değişikliklerinin algılanmadığını algılamadı, ancak nadiren tasarlanmıştır. Bu eski davranış, programın, programcı tarafından amaçlanan farklı bir uyarı kümesiyle derlenmesi, büyük olasılıkla sessiz hatalı çalışma zamanı davranışına neden olduğundan bir risk oluşturdu. Derleyici artık kod programcısının bu şekilde yazılmış olduğunu algılar ve bildirir ve etkinleştirilirse, isteğe bağlı bir derleyici uyarısı C5031, bu şekilde eşleşen `#pragma warning(pop)`konuma sorun verir. Bu uyarı, karşılık gelen `#pragma warning(push)`konumuna başvuran bir nota sahiptir.

   ```Output
    warning C5031: #pragma warning(pop): likely mismatch, popping warning state pushed in different file
   ```

   Örnek (önce)

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

   Örnek (sonrasında)

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

   Yaygın olarak, bu şekilde yazılan kod bazen bilerek yapılır. Bu şekilde yazılan kod, `#include` sırayla yapılan değişikliklere duyarlıdır; mümkün olduğunda, kaynak kodu dosyalarının uyarı durumunu kendi kendine içeren bir şekilde yönetmesini öneririz.

- **Eşleşmeyen #pragma Uyarısı (gönderim)** (yalnızca etkiler `/Wall`) `/WX`

   Derleyicinin önceki sürümleri, bir çeviri biriminin sonunda eşleşmeyen `#pragma warning(push)` durum değişikliklerini algılamadı. Derleyici artık kod programcısının bu şekilde yazıldığını algılar ve bildirir ve etkinleştirilirse, eşleşmeyen `#pragma warning(push)`bir derleyici uyarı C5032. Bu uyarı yalnızca çeviri biriminde derleme hatası yoksa verilir.

   ```Output
    warning C5032: detected #pragma warning(push) with no corresponding #pragma warning(pop)
   ```

   Örnek (önce)

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

   Örnek (sonrasında)

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

- **Gelişmiş #pragma uyarı durumu izlemenin sonucu olarak ek uyarılar verilebilir**

   Derleyici tarafından izlenen `#pragma warning` durum değişikliklerinin önceki sürümleri, tüm amaçlanan uyarıları vermek için yeterince iyi sonuç veriyor. Bu davranış, belirli uyarıların, programcı tarafından farklı koşullarda etkili bir şekilde gizleneceği bir risk oluşturdu. Derleyici artık daha fazla `#pragma warning` robustly durumu izler; özellikle şablonların içindeki `#pragma warning` durum değişiklikleriyle ilgilidir ve isteğe bağlı olarak, programcı 'nin istenmeyenkullanımlarınıbulmasınısağlamayayönelikyeniuyarılarC5031veC5032`#pragma warning(push)` ve .`#pragma warning(pop)`

   Geliştirilmiş `#pragma warning` durum değişikliği izlemenin bir sonucu olarak, daha önce yanlış bir şekilde gizlenen uyarılar ya da daha önce yanlış tanılanmış sorunlarla ilgili uyarılar artık verilebilir.

- **Erişilemeyen kodun geliştirilmiş kimliği**

   C++Derleyicinin önceki sürümleri üzerinden satır içi işlev çağrılarının standart kitaplık değişiklikleri ve geliştirilmiş özelliği, derleyicinin belirli bir kodun artık ulaşılamaz olduğunu kanıtlamasını sağlayabilir. Bu yeni davranış, yeni ve daha sık verilen uyarı C4720 örneklerinin oluşmasına neden olabilir.

   ```Output
    warning C4720: unreachable code
   ```

   Çoğu durumda, bu uyarı yalnızca iyileştirmeler etkinken derlenirken verilebilir, çünkü iyileştirmeler daha fazla işlev çağrısı yapabilir, gereksiz kodu ortadan kaldırabilir, aksi takdirde belirli kodun ulaşılamaz olduğunu belirlemeyi mümkün hale getirir. Özellikle de [std:: Find](assetId:///std::find?qualifyHint=False&autoUpgrade=True)kullanımı ile ilgili olarak **try/catch** blokları içinde yeni uyarı C4720 örneklerinin oluştuğunu gözlemliyoruz.

   Örnek (önce)

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

   Örnek (sonrasında)

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

### <a name="VS_Update2"></a>Visual Studio 2015 güncelleştirme 2 ' deki uyumluluk geliştirmeleri

- **Ek uyarılar ve hatalar, SFıNAE ifadesi için kısmi destek sonucu olarak verilebilir.**

   Derleyicinin önceki sürümleri, SFıNAE ifadesi için destek eksikliği nedeniyle, **decltype** belirticileri içindeki belirli tür ifadeleri ayrıştırmadı. Bu eski davranış yanlıştı ve C++ standart ile uyumlu değil. Derleyici artık bu ifadeleri ayrıştırır ve sürekli uyumluluk geliştirmeleri nedeniyle ifade SFıNAE için kısmi desteğe sahiptir. Sonuç olarak, derleyici artık derleyicinin önceki sürümlerinin ayrıştırmadığı ifadelerde bulunan uyarıları ve hataları verir.

   Bu yeni davranış, henüz bildirilmemiş bir tür içeren bir **decltype** ifadesini ayrıştırdığında, derleyici bir sonuç olarak derleyici hatası C2039 yayınlar.

   ```Output
    error C2039: 'type': is not a member of '`global namespace''
   ```

   Örnek 1: bildirilmemiş bir türün kullanımı (önce)

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

   Bu yeni davranış, bağımlı bir adın bir tür olduğunu belirtmek için **TypeName** anahtar sözcüğünün gerekli bir kullanımı eksik olan bir **decltype** ifadesini ayrıştırdığında, derleyici derleyici uyarısı C4346 ve derleyici hatası C2923 ile birlikte verir.

   ```Output
    warning C4346: 'S2<T>::Type': dependent name is not a type
   ```

   ```Output
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'
   ```

   Örnek 2: bağımlı ad bir tür değil (önce)

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

- `volatile`**üye değişkenleri örtük olarak tanımlanmış oluşturucuları ve atama işleçlerini önler** Derleyicinin önceki sürümlerinde, varsayılan kopyalama/taşıma oluşturucuları ve varsayılan kopyalama/taşıma atama işleçleri otomatik olarak oluşturulan **geçici** üye değişkenlerine sahip bir sınıf izin verilir. Bu eski davranış yanlıştı ve C++ standart ile uyumlu değil. Derleyici artık, bu işleçlerin varsayılan uygulamalarının otomatik olarak oluşturulmasını önleyen, önemsiz olmayan oluşturma ve atama işleçleri olan geçici üye değişkenleri olan bir sınıfı kabul eder. Böyle bir sınıf bir birleşimin üyesi (veya bir sınıfın içindeki anonim bir birleşim) olduğunda, birleşimin kopyalama/taşıma oluşturucuları ve kopyalama/taşıma atama işleçleri (veya unontanýmlý birleşimini içeren sınıf) örtük olarak silindi olarak tanımlanır. Açıkça tanımlanmaksızın birleşim (veya anonim birleşim içeren sınıf) oluşturmaya veya kopyalamaya çalışılması bir hatadır ve derleyici sonuç olarak derleyici hatası C2280 yayınlar.

   ```Output
    error C2280: 'B::B(const B &)': attempting to reference a deleted function
   ```

   Örnek (önce)

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

   Örnek (sonrasında)

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

- **Statik üye işlevleri CV niteleyicilerini desteklemez.**

   Visual C++ 2015 'nin önceki sürümleri, statik üye işlevlerinin CV niteleyicilerine sahip olmasına izin verilir. Bu davranış, Visual C++ 2015 ve Visual C++ 2015 güncelleştirme 1 ' deki bir gerileme nedeniyle yapılır; Visual C++ 2013 ve önceki görsel C++ reddetme kodu bu şekilde yazılmıştır. Visual C++ 2015 ve Visual C++ 2015 Update 1 davranışı yanlıştır ve C++ standart ile uyumlu değildir.  Visual Studio 2015 güncelleştirme 2 bu şekilde yazılmış kodu reddeder ve bunun yerine derleyici hatası C2511 yayınlar.

   ```Output
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'
   ```

   Örnek (önce)

   ```cpp
    struct A
    {
      static void func();
    };

    void A::func() const {}  // C2511
   ```

   Örnek (sonrasında)

   ```cpp
    struct A
    {
      static void func();
    };

    void A::func() {}  // removed const
   ```

- **WinRT kodunda numaralandırmanın iletme bildirimine izin verilmiyor** (yalnızca `/ZW` etkiler)

   Windows çalışma zamanı (WinRT) için derlenen kod, C++ `/clr` derleme türlerinin, bir derleyici anahtarı kullanılarak .NET Framework için derlendiğine benzer şekilde bildirilmesine izin vermez. Bu davranış, bir numaralandırma boyutunun her zaman bilinmesini ve WinRT türü sistemine doğru şekilde yansıtılmasını sağlar. Derleyici bu şekilde yazılmış kodu reddeder ve derleyici hatası C3197 ile birlikte derleyici hatası C2599 yayınlar.

   ```Output
    error C2599: 'CustomEnum': the forward declaration of a WinRT enum is not allowed
   ```

   ```Output
    error C3197: 'public': can only be used in definitions
   ```

   Örnek (önce)

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

   Örnek (sonrasında)

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

- **Aşırı yüklenmiş üye olmayan New işleci ve delete işleci satır içi olarak bildirilemez** (Düzey 1 (`/W1`)-varsayılan)

   Önceki derleyicinin sürümleri, üye olmayan **operator new** ve **operator delete** işlevleri satır içi olarak bildirildiğinde bir uyarı vermez. Bu şekilde yazılan kod hatalı biçimlendirilmiş (Tanılama gerekmez) ve eşleşmeyen yeni ve silme işleçlerinden kaynaklanan bellek sorunlarına neden olabilir (özellikle de boyutu kaldırma ile birlikte kullanıldığında), tanılanması zor olabilir. Derleyici artık bu şekilde yazılmış kodu belirlemesine yardımcı olmak için derleyici uyarısı C4595 ' i yayınlar.

   ```Output
    warning C4595: 'operator new': non-member operator new or delete functions may not be declared inline
   ```

   Örnek (önce)

   ```cpp
    inline void* operator new(size_t sz)  // warning C4595
    {
      ...
    }
   ```

   Örnek (sonrasında)

   ```cpp
    void* operator new(size_t sz)  // removed inline
    {
      ...
    }
   ```

   Bu şekilde yazılmış kodu düzeltme, işleç tanımlarının bir üstbilgi dosyasından ve karşılık gelen bir kaynak dosyaya taşınmasını gerektirebilir.

### <a name="VS_Update3"></a>Visual Studio 2015 güncelleştirme 3 ' te uyumluluk geliştirmeleri

- **std:: is_convertable artık kendi kendine atamayı algılar**  (Standart Kitaplık) Nitelik `std::is_convertable` türünün önceki sürümleri, kopya Oluşturucusu silindiği veya özel bir sınıf türünün kendi kendine atamasını doğru bir şekilde algılamadı. Şimdi, `std::is_convertable<>::value` silinmiş veya özel kopya Oluşturucusu olan bir sınıf türüne uygulandığında doğru olarak **false** olarak ayarlanmıştır.

   Bu değişiklik ile ilişkili bir derleyici tanılaması yok.

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

   Visual C++'ın önceki sürümlerinde, bu örneğin en altındaki statik onaylar, yanlış şekilde **doğru**olarak ayarlandığı `std::is_convertable<>::value` için geçti. Artık yanlış olarak ayarlanmıştır, statik onayların başarısız olmasına neden olur. `std::is_convertable<>::value`

- **Varsayılan olarak ayarlanmış veya silinmiş önemsiz kopyalama ve taşıma oluşturucuları erişim belirticilerine göre**

   Derleyicinin önceki sürümleri, çağrılmalarına izin vermeden önce, varsayılan olarak ayarlanmış veya silinmiş Önemsiz kopya ve taşıma oluşturucularının erişim belirticisini denetmedi. Bu eski davranış yanlıştı ve C++ standart ile uyumlu değil. Bazı durumlarda, bu eski davranış sessiz hatalı kod oluşturma riskini oluşturmuştur ve bu da öngörülemeyen çalışma zamanı davranışına neden olur. Derleyici artık, çağrılabilir olup olmadığını anlamak için varsayılan olarak ayarlanmış veya silinmiş önemsiz kopyalama ve taşıma oluşturucularının erişim belirticisini denetler ve bu durumda, bir sonuç olarak derleyici uyarısı C2248 yayınlar.

   ```Output
    error C2248: 'S::S' cannot access private member declared in class 'S'
   ```

   Örnek (önce)

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

   Örnek (sonrasında)

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

- **ÖZNITELIKLI atl kod desteğinin kullanımdan kaldırılması** (Düzey 1 (`/W1`)-varsayılan)

   Derleyicinin önceki sürümleri, öznitelikli ATL kodunu destekliyordu. [Visual C++ 2008 ' de başlayan](#whats-new-for-c-in-visual-studio-2008)öznitelikli atl kodu desteğini kaldırmanın sonraki AŞAMASı olarak, öznitelikli atl kodu kaldırılmıştır. Derleyici artık bu tür kullanım dışı kodu belirlemesine yardımcı olmak için derleyici uyarısı C4467 ' i yayınlar.

   ```Output
    warning C4467: Usage of ATL attributes is deprecated
   ```

   Destek derleyicisinden kaldırılana kadar öznitelikli atl kodu kullanmaya devam etmek istiyorsanız, `/Wv:18` veya `/wd4467` komut satırı bağımsız değişkenlerini derleyiciye geçirerek veya kaynak kodunuza ekleyerek `#pragma warning(disable:4467)` bu uyarıyı devre dışı bırakabilirsiniz.

   Örnek 1 (önceki)

   ```cpp
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
    class A {};
   ```

   Örnek 1 (sonra)

   ```cpp
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};
   ```

   Bazen, aşağıdaki örnek kodda olduğu gibi kullanım dışı ATL özniteliklerini kullanmaktan kaçınmak için bir IDL dosyası oluşturmanız gerekebilir veya bir IDL dosyası oluşturmak isteyebilirsiniz.

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

   İlk olarak, *. IDL dosyasını oluşturun; vc140. IDL tarafından oluşturulan dosya, arabirimleri ve ek açıklamaları içeren \*bir. IDL dosyası elde etmek için kullanılabilir.

   Ardından, C++ arabirim tanımlarının oluşturulduğundan emin olmak için, derlemenize BIR MIDL adımı ekleyin.

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

   Ardından, aşağıdaki örnek kodda olduğu gibi doğrudan uygulama dosyasında ATL kullanın.

   Örnek 2 uygulama (sonrasında)

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

- **Önceden derlenmiş üstbilgi (pch) dosyaları ve eşleşmeyen #include yönergeleri** (yalnızca etkiler `/Wall`) `/WX`

   Derleyicinin önceki sürümleri, önceden derlenmiş üst `#include` bilgi (pch) dosyaları `-Yc` kullanılırken `-Yu` ve derlemeler arasında kaynak dosyalarda eşleşmeyen yönergeleri kabul etti. Bu şekilde yazılan kod artık derleyici tarafından kabul edilmez. Derleyici artık, PCH dosyalarını kullanırken eşleşmeyen `#include` yönergeleri tanımlamanızı sağlamak için derleyici uyarısı CC4598 ' i yayınlar.

   ```Output
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position
   ```

   Örnek (öncesi):

   X. cpp (-YCC. h)

   ```cpp
    #include "a.h"
    #include "b.h"
    #include "c.h"
   ```

   Z. cpp (-yuc. h)

   ```cpp
    #include "b.h"
    #include "a.h"  // mismatched order relative to X.cpp
    #include "c.h"
   ```

   Örnek (sonrasında)

   X. cpp (-YCC. h)

   ```cpp
    #include "a.h"
    #include "b.h"
    #include "c.h"
   ```

   Z. cpp (-yuc. h)

   ```cpp
    #include "a.h"
    #include "b.h" // matched order relative to X.cpp
    #include "c.h"
   ```

- **Ön derlenmiş üstbilgi (pch) dosyaları ve eşleşmeyen içerme dizinleri** (yalnızca etkiler `/Wall`) `/WX`

   Derleyicinin önceki sürümleri kabul edildi, önceden derlenmiş üst bilgi`-I`(pch) dosyalarını kullanırken derlemeler arasında `-Yc` ve `-Yu` derlemelerde dizin () komut satırı bağımsız değişkenleri içerir. Bu şekilde yazılan kod artık derleyici tarafından kabul edilmez.   Derleyici artık, PCH dosyalarını kullanırken eşleşmeyen içerme dizini (`-I`) komut satırı bağımsız değişkenlerini tanımlamanızı sağlamak için derleyici uyarısı CC4599 ' i yayınlar.

   ```Output
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position
   ```

   Örnek (önce)

   ```ms-dos
    cl /c /Wall /Ycc.h -I.. X.cpp
    cl /c /Wall /Yuc.h Z.cpp
   ```

   Örnek (sonrasında)

   ```ms-dos
    cl /c /Wall /Ycc.h -I.. X.cpp
    cl /c /Wall /Yuc.h -I.. Z.cpp
   ```

## <a name="whats-new-for-c-in-visual-studio-2013"></a>Visual Studio 2013 C++ 'daki yenilikler

### <a name="improved-iso-cc-standards-support"></a>Geliştirilmiş ISO C/C++ standartları desteği

#### <a name="compiler"></a>Derleyici

MSVC, bu ISO C++ 11 dil özelliklerini destekler:

- İşlev şablonları için varsayılan şablon bağımsız değişkenleri.
- Temsilci oluşturucuları
- Açık dönüştürme işleçleri.
- Başlatıcı listeleri ve Tekdüzen başlatma.
- Ham dize değişmez değerleri.
- Değişken bağımsız değişken şablonlar.
- Diğer ad şablonları.
- Silinen İşlevler.
- Statik olmayan veri üyesi başlatıcıları (NSDMIs).
- Varsayılan işlevler. [https://doi.org/10.13012/J8PN93H8](\*)
- Bu ISO C99 dil özelliklerini destekler:
- _Bool
- Bileşik değişmez değerler.
- Belirlenen başlatıcılar.
- Bildirimleri kodla karıştırma.
- Yeni derleyici seçeneği `/Zc:strictStrings`kullanılarak, değiştirilebilir değerlere dize sabiti dönüştürmeye izin verilmez. C++ 98 ' de, dize değişmez `char*` değerlerinin (ve geniş dize `wchar_t*`değişmez değerleri) dönüşümü kullanım dışıdır. C++ 11 ' de, dönüştürme tamamen kaldırılmıştır. Derleyici, standardı kesin olarak uyumlu hale gelse de, bunun yerine dönüştürmeyi denetleyebilmeniz için `/Zc:strictStrings` seçeneğini sağlar. Varsayılan olarak, seçeneği kapalıdır. Bu seçeneği hata ayıklama modunda kullandığınızda STL 'in derlenmeyeceğini unutmayın.
- rvalue/lvalue başvuru yayınları. Rvalue başvuruları ile C++ 11, lvalues ve rvalues değerlerini açıkça ayırt edebilir. Daha önce, derleyici bunu belirli atama senaryolarında sağlamadı. Derleyicinin C++ dil çalışma kağıdına uyumlu `/Zc:rvalueCast`hale getirmek için yeni bir derleyici seçeneği eklenmiştir (bkz. Bölüm 5,4, [expr. Cast]/1). Bu seçenek belirtilmediğinde varsayılan davranış, Visual Studio 2012 ile aynıdır.

> [!NOTE]
> Varsayılan işlevler için, üye tabanlı taşıma oluşturucuları ve taşıma atama işleçleri istemek için = Default kullanılması desteklenmez.

### <a name="c99-libraries"></a>C99 kitaplıkları

Bildirimler ve uygulamalar bu üstbilgilere eksik işlevler için eklendi: Math. h, CType. h, wctype. h, stdio. h, Stdlib. h ve wchar. h. Ayrıca eklenen yeni başlıklar, karmaşık. h, stdbool. h, fenv. h ve ınttypes. h, ve içinde belirtilen tüm işlevler için uygulamalar. Yeni C++ sarmalayıcı üstbilgileri (ccomplex, cfenv, cinttypes, ctgmath) ve bazı diğerleri güncelleştirilir (ccomplex, cctype, clocale, cmath, cstdint, cstdio, CString, cwchar ve cwctype).

### <a name="standard-template-library"></a>Standart Şablon Kitaplığı

C++ 11 açık dönüştürme işleçleri, başlatıcı listeleri, kapsamlı numaralandırmalar ve bağımsız değişken olmayan şablonlar için destek.
Tüm kapsayıcılar artık C++ 11 ayrıntılı öğe gereksinimlerini desteklemektedir.
Bu C++ 14 özellikleri için destek:

- "Saydam operatör" daha az < >, daha fazla < > ve < >, < > ve benzeri.
- make_unique<T>(args...) ve make_unique < T [] > (n)
- cbegin ()/cend (), rbegin ()/rend (), ve crbegin ()/crend () üye olmayan işlevleri.
- \<Atomik > çok sayıda performans geliştirmesi aldı.
- \<type_traits >, büyük sabitleştirme ve kod düzeltmeleri aldı.

### <a name="breaking-changes"></a>Yeni Değişiklikler

ISO C/C++ standartları için geliştirilmiş bu destek, c++ 11 ' e uymak ve Visual Studio 2013 Visual C++ üzerinde doğru bir şekilde derleme yapmak için mevcut kodda değişiklik yapılmasını gerektirebilir.

### <a name="visual-c-library-enhancements"></a>Görsel C++ kitaplık geliştirmeleri

- C++REST SDK eklenir. REST hizmetlerinin modern C++ bir uygulamasına sahiptir.
- C++AMP doku desteği geliştirildi. Artık, MIN haritaları ve yeni örnekleme modları için destek içerir.
- PPL görevleri birden çok zamanlama teknolojilerini ve zaman uyumsuz hata ayıklamayı destekler. Yeni API 'Ler, hem normal sonuçlar hem de özel durum koşulları için PPL görevlerinin oluşturulmasını etkinleştirir.

### <a name="c-application-performance"></a>C++Uygulama performansı

- Otomatik Vektörleştirici şimdi kodunuzun daha hızlı çalışmasını sağlamak C++ için daha fazla desen tanır ve iyileştirir.
- ARM platformu ve Atom mikro mimari kod kalitesi geliştirmeleri.
- __vectorcall çağırma kuralı eklendi. Vektör kayıtlarını kullanmak için __vectorcall çağırma kuralını kullanarak vektör türü bağımsız değişkenlerini geçirin.
- Yeni bağlayıcı seçenekleri. ( `/Gw` Derleyici) ve `/Gy` (Assembler) anahtarları, geçiş ikililerini oluşturmak için bağlayıcı iyileştirmelerini etkinleştirir.
- C++CPU ve GPU arasında veri kopyalamayı azaltmak veya ortadan kaldırmak için AMP paylaşılan bellek desteği.

### <a name="profile-guided-optimization-pgo-enhancements"></a>Profil temelli Iyileştirme (PGO) geliştirmeleri

- PGO kullanılarak en iyi duruma getirilmiş çalışan uygulama kümesindeki bir azalmayla ilgili performans iyileştirmeleri.
- Windows Çalışma Zamanı uygulama geliştirmesi için yeni PGO.

### <a name="windows-runtime-app-development-support"></a>Windows Çalışma Zamanı uygulama geliştirme desteği

- **Değer yapılarında kutulanmış türler Için destek.**

   Artık null olabilecek alanları (örneğin, `IBox<int>^` **int**yerine) kullanarak değer türlerini tanımlayabilirsiniz. Bu, alanların bir değeri olabileceği ya da **nullptr**'ye eşit olabileceği anlamına gelir.

- **Daha zengin özel durum bilgileri.**

   C++/CX, uygulama ikili arabirimi (ABı) genelinde zengin özel durum bilgilerinin yakalanmasını ve yayılmasını sağlayan yeni Windows hata modelini destekler. Buna çağrı yığınları ve özel ileti dizeleri dahildir.

- **Object:: ToString () artık sanal.**

   Artık Kullanıcı tanımlı Windows Çalışma Zamanı başvuru türlerinde ToString geçersiz kılabilirsiniz.

- **Kullanımdan kaldırılan API 'Ler Için destek.**

   Genel Windows Çalışma Zamanı API 'Leri artık kullanım dışı olarak işaretlenebilir ve derleme uyarısı olarak görünen ve geçiş Kılavuzu sağlayan özel bir ileti verilir.

- **Hata ayıklayıcı geliştirmeleri.**

   Yerel/JavaScript birlikte çalışma hata ayıklaması, Windows Çalışma Zamanı özel durum tanılaması ve zaman uyumsuz kod hata ayıklaması (hem Windows Çalışma Zamanı hem de PPL) için destek.

> [!NOTE]
> Bu bölümde açıklanan özel C++özelliklere ve geliştirmelere ek olarak, Visual Studio 'daki diğer geliştirmeler de daha iyi Windows çalışma zamanı uygulamalar yazmanıza yardımcı olabilir.

### <a name="diagnostics-enhancements"></a>Tanılama geliştirmeleri

- Hata ayıklayıcı geliştirmeleri. Zaman uyumsuz hata ayıklama ve Yalnızca kendi kodum hata ayıklama desteği.
- Kod Analizi kategorileri. Artık kod hatalarını bulup düzeltmenize yardımcı olması için kod çözümleyicisinden kategorize edilmiş çıktıyı görüntüleyebilirsiniz.
- XAML tanılama. Artık XAML 'de UI-yanıt verme ve pil kullanımı sorunlarını tanılayabilirsiniz.
- Grafikler ve GPU hata ayıklama geliştirmeleri.
- Gerçek cihazlarda uzaktan yakalama ve kayıttan yürütme.
- Eşzamanlı C++ amp ve CPU hata ayıklaması.
- İyileştirilmiş C++ amp çalışma zamanı tanılaması.
- HLSL Işlem gölgelendirici izleme hata ayıklaması.

### <a name="3-d-graphics-enhancements"></a>3-b grafik geliştirmeleri

- Önceden çarpılan alfa DDS biçimi için görüntü Içeriği ardışık düzeni desteği.
- Görüntü Düzenleyicisi, işleme için dahili olarak önceden çarpılan Alfa kullanır ve böylece koyu hatlar gibi işleme yapıtları önler.
- Görüntü ve model düzenleyicileri. Kullanıcı tanımlı filtre oluşturma artık görüntü düzenleyici ve Model Düzenleyicisi 'nde gölgelendirici tasarımcısında destekleniyor.

### <a name="ide-and-productivity"></a>IDE ve üretkenlik

**Geliştirilmiş kod biçimlendirmesi**. C++ Kodunuza daha fazla biçimlendirme ayarı uygulayabilirsiniz. Bu ayarları kullanarak, küme ayraçları, anahtar sözcükler, girintileme, Aralık ve çizgi kaydırma için yeni satır yerleştirmeyi denetleyebilirsiniz. Deyimleri ve blokları tamamladığınızda ve bir dosyaya kod yapıştırdığınızda kod otomatik olarak biçimlendirilir.

**Küme ayracı tamamlama.** C++kod şimdi bu açılış karakterlerine karşılık gelen kapatma karakterlerini otomatik olarak tamamlar:

- {(süslü ayraç)
- [(köşeli ayraç)
- (parantez)
- ' (tek tırnak)
- "(çift tırnak)

**Ek C++ otomatik tamamlama özellikleri.**

- Sınıf türleri için noktalı virgül ekler.
- Ham dize değişmez değerleri için ayraçları tamamlar.
- Çok satırlı açıklamaları tamamlar (/\* \*/)

**Tüm başvuruları bul** artık, metin eşleşmeleri listesini görüntülendikten sonra arka planda başvuruları otomatik olarak çözümler ve filtreler.

**Bağlam tabanlı üye listesi filtrelemesi.** Erişilemeyen Üyeler, IntelliSense üye listelerinden filtrelenmez. Örneğin, türü uygulayan kodu değiştirmediğiniz müddetçe, özel üyeler üye listesinde gösterilmez. Üye listesi açıkken, tek bir filtreleme düzeyini kaldırmak için **CTRL**+**J** tuşlarına basabilirsiniz (yalnızca geçerli üye listesi penceresi için geçerlidir). Metin filtrelemeyi kaldırmak ve her üyeyi göstermek için **CTRL**+**J** 'ye tekrar basabilirsiniz.

**Parametre yardımı kaydırma.** Parametre-Yardım araç ipucunda gösterilen işlev imzası, yalnızca rastgele bir imzayı göstermek ve geçerli bağlam temelinde güncelleştirilemeymek yerine gerçekten yazdığınız parametre sayısına göre değişir. Parametre yardımı, iç içe yerleştirilmiş işlevlerde görüntülendiğinde de doğru şekilde çalışır.

**Üst bilgi/kod dosyası değiştirme.** Artık kısayol menüsündeki bir komutu veya klavye kısayolunu kullanarak bir üst bilgi ve ilgili kod dosyası arasında geçiş yapabilirsiniz.

**Yeniden C++ boyutlandırılabilir proje özellikleri penceresi**

**/CX ve C++ C++/CLIA 'da olay işleyici kodu otomatik oluşturma.**  Bir C++/CX veya C++/CLI kod dosyasına bir olay işleyicisi eklemek için kod yazarken, düzenleyici temsilci örneğini ve olay işleyici tanımını otomatik olarak oluşturabilir. Olay işleyici kodu otomatik olarak oluşturulursa bir araç ipucu penceresi görüntülenir.

**DPı tanıma geliştirmesi.** Uygulama bildirim dosyaları için DPı tanıma ayarı artık "yüksek DPı kullanan monitör başına" ayarını destekler.

**Daha hızlı yapılandırma geçişi.** Büyük uygulamalar için, yapılandırmaların değiştirme, özellikle de sonraki anahtarlama işlemleri — çok daha hızlı yürütülür.

**Derleme zamanı verimliliği.** Çok sayıda iyileştirme ve çok çekirdekli kullanım, özellikle büyük projeler için yapıları daha hızlı hale getirir. WinMD 'ye C++ başvurular C++ içeren uygulamalar için Artımlı derlemeler de çok daha hızlıdır.

## <a name="whats-new-for-c-in-visual-studio-2012"></a>Visual Studio 2012 C++ ' deki yenilikler

### <a name="improved-c11-standards-support"></a>Geliştirilmiş C++ 11 standartları desteği

#### <a name="standard-template-library"></a>Standart Şablon Kitaplığı

- Yeni STL üstbilgileri için destek: \<atomik >, \<No >, \<condition_variable >, \<dosya sistemi > \<, gelecekteki > \<, mutex > \<, oran > ve \< iş parçacığı >.
- Bellek kaynağı kullanımını iyileştirmek için kapsayıcılar artık küçüktür. Örneğin, varsayılan ayarlarla x86 yayın modunda, `std::vector` Visual Studio 2010 ' de 16 bayttan Visual Studio 2012 ' de 12 bayt kadar küçültülebilir ve `std::map` Visual Studio 2010 ' de 16 bayttan Visual Studio 2012 ' e kadar küçültülebilir.
- C++ 11 standardı için izin verilen ancak gerekli olmadığı için, SCARY yineleyiciler uygulandı.

#### <a name="other-c11-enhancements"></a>Diğer C++ 11 geliştirmeleri

- Döngüler için Aralık tabanlı. (For-range-declaration: ifadesi) formundaki diziler, STL kapsayıcıları ve Windows Çalışma Zamanı koleksiyonlarıyla çalışan daha güçlü döngüler yazabilirsiniz. Bu, çekirdek dil desteğinin bir parçasıdır.
- Boş bir lambda tanıtıcı kümesi [] ile başlayan ve yerel değişken içermeyen kod blokları olan durum bilgisiz Lambdalar, artık C++ 11 standardı tarafından istenen işlev işaretçilerine örtük olarak dönüştürülebilir.
- Kapsamlı numaralandırmalar desteği. C++ Enum sınıfı enum-Key artık desteklenmektedir. Aşağıdaki kod, bu numaralandırma anahtarının önceki enum davranışından nasıl farklılık gösterir.

   ```cpp
  enum class Element { Hydrogen, Helium, Lithium, Beryllium };
  void func1(Element e);
  func1(Hydrogen); // error C2065: 'Hydrogen' : undeclared identifier
  func1(Element::Helium); // OK
   ```

### <a name="windows-runtime-app-development-support"></a>Windows Çalışma Zamanı uygulama geliştirme desteği

- **Yerel XAML tabanlı kullanıcı arabirimi modeli**. Windows Çalışma Zamanı uygulamalar için, yeni yerel XAML tabanlı kullanıcı arabirimi modelini kullanabilirsiniz.
- **Görsel C++ bileşen uzantıları**. Bu uzantılar, Windows Çalışma Zamanı uygulamalarının gerekli bir parçası olan Windows Çalışma Zamanı nesnelerinin tüketimini basitleştirir. Daha fazla bilgi için bkz. [Windows çalışma zamanı C++ uygulamalar için yol haritası](../cppcx/universal-windows-apps-cpp.md) ve [Visual C++ dil başvurusuC++(/CX)](../cppcx/visual-c-language-reference-c-cx.md)
- **DirectX oyunları**. Windows Çalışma Zamanı uygulamalar için yeni DirectX desteğini kullanarak ilgi çekici Oyunlar geliştirebilirsiniz.
- **Xaml/DirectX birlikte çalışması**. Hem XAML hem de DirectX kullanan Windows Çalışma Zamanı uygulamalar artık verimli bir şekilde çalışır.
- **Windows çalışma zamanı bileşen DLL 'si geliştirme**. Bileşen DLL 'SI geliştirme Windows Çalışma Zamanı ortamını Genişletilebilir hale getirir.

### <a name="compiler-and-linker"></a>Derleyici ve bağlayıcı

- **Otomatik Vektörleştirici**. Derleyici, kodunuzda döngüleri analiz eder ve mümkün olduğunda, tüm modern işlemcilerde bulunan vektör kayıtlarını ve talimatlarını kullanan yönergeleri yayar. Bu, döngülerin daha hızlı çalışmasını sağlar. (İşlemci yönergeleri, Streaming SIMD Extensions için SSE olarak bilinir). Otomatik olarak uygulandığından, bu iyileştirmeyi etkinleştirmeniz veya istemeniz gerekmez.
- **Otomatik paralelleştirme**. Derleyici, kodunuzda döngüleri çözümleyebilir ve hesaplamaları birden çok çekirdeğe veya işlemciye yayan yönergeler yayabilir. Bu, döngülerin daha hızlı çalışmasını sağlayabilir. Varsayılan olarak etkinleştirilmediğinden Bu iyileştirmeyi istemeniz gerekir. Birçok durumda, paralel olarak istediğiniz döngülere hemen `#pragma loop(hint_parallel(N))` önce kodunuza bir eklemek yardımcı olur.
- Otomatik Vektörleştirici ve otomatik paralelleştirme birlikte çalışarak, hesaplamaların birden çok çekirdeğe yayılmasını ve her bir çekirdekte kodun vektör kayıtlarını kullanmasını sağlayabilirsiniz.

### <a name="new-in-visual-studio-2012-update-1"></a>Visual Studio 2012 güncelleştirme 1 ' de yeni

C++ Kodunuzu oluştururken Windows XP 'yi hedefleyin.
Windows XP ve Windows Server C++ 2003 ' i hedeflemek için Microsoft derleyicisini ve kitaplıklarını kullanabilirsiniz.

#### <a name="parallel-programming-support"></a>Paralel programlama desteği

##### <a name="c-accelerated-massive-parallelism-amp"></a>C++ Accelerated Massive Parallelism (AMP)

C++AMP, genellikle ayrı bir grafik C++ kartında GPU olarak bulunan veri paralel donanımının avantajlarından yararlanarak kodunuzun yürütülmesini hızlandırır. C++ Amp programlama modeli çok boyutlu diziler, dizin oluşturma, bellek aktarımı, döşeme ve bir matematiksel işlev kitaplığı içerir. AMP dil C++ uzantılarını ve derleyici kısıtlamalarını kullanarak, verilerin CPU 'dan GPU 'ya ve geri nasıl taşındığını kontrol edebilirsiniz.

**Masının.** GPU 'YU hedeflemek için amp kullanan C++ uygulamalar için hata ayıklama deneyimi diğer C++ uygulamalar için hata ayıklamaya benzer. Bu, daha önce bahsedilen yeni paralel hata ayıklama eklemeleri içerir.

**Profilini.** Artık C++ amp ve diğer Direct3D tabanlı programlama MODELLERINE dayalı GPU etkinlikleri için profil oluşturma desteği vardır.

#### <a name="general-parallel-programming-enhancements"></a>Genel paralel programlama geliştirmeleri

Çok çekirdekli ve çok çekirdekli mimarilere yönelik donanımlar sayesinde, geliştiriciler artık tek çekirdekler için asla artan saat hızına sahip olamaz. Eşzamanlılık Çalışma Zamanı paralel programlama desteği, geliştiricilerin bu yeni mimarilerin avantajlarından yararlanmasını sağlar.
Visual Studio 2010 ' de, C++ paralel Desenler kitaplığı gibi güçlü paralelleştirme kitaplıkları, gelişmiş veri akışı işlem hatlarını ifade ederek eşzamanlılık avantajlarından yararlanma özellikleriyle birlikte sunulmuştur. Visual Studio 2012 ' de, bu kitaplıklar daha iyi performans, daha fazla denetim ve geliştiricilerin en çok ihtiyaç duyduğu paralel desenler için daha zengin destek sağlamak üzere genişletilmiştir. Teklifin genişliği artık şunları içerir:

- Zaman uyumsuzluğu ve devamlılıkları destekleyen zengin görev tabanlı bir programlama modeli.
- Çatalla birleşen paralellik (parallel_for, parallel_for ile benzeşim, parallel_for_each, parallel_sort, parallel_reduce, parallel_transform) destekleyen paralel algoritmalar.
- Priority_queue, Queue, vector ve Map gibi std veri yapılarının iş parçacığı güvenli sürümlerini sağlayan eşzamanlılık güvenli kapsayıcılar.
- Geliştiricilerin, doğal olarak eşzamanlı birimlerde bulunan veri akışı işlem hatlarını hızlı bir şekilde ifade etmek için kullanabileceği zaman uyumsuz aracılar Kitaplığı.
- Bu listedeki desenlerin düzgün bir şekilde oluşumunu kolaylaştırmak için özelleştirilebilir bir Zamanlayıcı ve Kaynak Yöneticisi.

##### <a name="general-parallel-debugging-enhancements"></a>Genel paralel hata ayıklama geliştirmeleri

**Paralel görevler** penceresi ve **Paralel Yığınlar** penceresine ek olarak Visual Studio 2012, bir ifadenin değerlerini tüm iş parçacıkları ve süreçler genelinde incelemenize ve sıralamayı gerçekleştirmenize olanak tanıyan yeni bir **paralel izleme** penceresi sunar. Sonuç üzerine filtreleniyor. Ayrıca, pencereyi genişletmek için kendi görselleştiricilerini de kullanabilir ve tüm araç pencereleri genelinde yeni çok işlem desteğinden yararlanabilirsiniz.

### <a name="ide"></a>IDE

**Visual Studio şablonları desteği.** Artık proje ve öğe şablonlarını yazmak C++ Için Visual Studio şablonları teknolojisini kullanabilirsiniz.

**Zaman uyumsuz çözüm yükü.** Daha hızlı çalışmaya başlayabilmeniz için projeler artık zaman uyumsuz olarak (önce çözümün önemli kısımları) yüklenir.

**Uzaktan hata ayıklama için otomatik dağıtım.** Visual C++ 'te uzaktan hata ayıklama için dosya dağıtımı basitleştirilmiştir. Proje bağlam menüsündeki **Dağıt** seçeneği, hata ayıklama yapılandırma özelliklerinde belirtilen dosyaları uzak bilgisayara otomatik olarak kopyalar. Dosyaları uzak bilgisayara el ile kopyalamak artık gerekli değildir.

**C++/CLı IntelliSense.** C++/CLı artık tam IntelliSense desteğine sahiptir. Hızlı bilgi, parametre yardımı, liste üyeleri ve otomatik tamamlama gibi IntelliSense özellikleri artık/Cliiçin C++de çalışır. Ayrıca, bu belgede listelenen diğer IntelliSense ve IDE geliştirmeleri de/Cliiçin C++de çalışır.

**Daha zengin IntelliSense araç Ipuçları.** C++IntelliSense hızlı bilgi araç ipuçları artık daha zengin XML belge açıklamaları stil bilgilerini gösteriyor. Kitaplıktan bir API kullanıyorsanız — Örneğin, C++ amp — XML belge açıklamalarını içeren IntelliSense araç ipucu, yalnızca bildirimden daha fazla bilgi gösterir. Ayrıca, kodunuzun XML belge açıklamaları varsa, IntelliSense araç ipuçları daha zengin bilgileri gösterir.

**C++Kod yapıları.** Çatı kodu, anahtar, if-else, for döngüsü ve diğer temel kod yapıları için liste üyeleri açılan listesinde kullanılabilir. Koda eklemek için listeden bir kod parçası seçin ve gerekli mantığı girin. Ayrıca, düzenleyicide kullanmak üzere kendi özel kod parçalarını da oluşturabilirsiniz.

**Üyelerin geliştirmelerini listeleyin.** Kod Düzenleyicisi 'ne kod yazarken, **üyeleri Listele** açılır listesi otomatik olarak görünür. Sonuçlar filtrelenmiştir, böylece siz yazarken yalnızca ilgili üyelerin görüntülenmesini sağlayabilirsiniz. Üye listesi tarafından kullanılan filtreleme mantığının türünü, >  **metin düzenleyici** > **C/C++** **Gelişmiş**altındaki **Seçenekler** iletişim kutusunda kontrol edebilirsiniz.

**Anlam renklendirme.** Türler, numaralandırmalar, makrolar ve diğer C++ belirteçler artık varsayılan olarak renklendirmektedir.

**Başvuru vurgulama.** Bir sembol seçilmesi artık geçerli dosyadaki sembolün tüm örneklerini vurgular. Vurgulanan başvurular arasında gezinmek için **CTRL**+ **+ Shift**+**yukarı ok** veya **CTRL**+**SHIFT**+**aşağı ok** tuşlarına basın. Bu özelliği, **Seçenekler** iletişim kutusunda, **metin düzenleyici** >  > **C++C/** **Gelişmiş**altında devre dışı bırakabilirsiniz.

### <a name="application-lifecycle-management-tools"></a>Uygulama yaşam döngüsü yönetimi araçları

#### <a name="static-code-analysis"></a>Statik kod analizi

İçin C++ statik analiz, daha zengin hata bağlamı bilgileri, daha fazla analiz kuralı ve daha iyi analiz sonuçları sağlamak üzere güncelleştirilmiştir. Yeni Kod Analizi penceresinde, iletileri anahtar sözcüğe, projeye ve önem derecesine göre filtreleyebilirsiniz. Pencerede bir ileti seçtiğinizde, kodun tetiklendiği kodun satırı kod düzenleyicide vurgulanır. Bazı C++ uyarılarda ileti, uyarıya yol gösteren yürütme yolunu gösteren kaynak satırları listeler; karar noktaları ve söz konusu yolu alma nedenleri vurgulanır.
Kod Analizi, çoğu Visual Studio 2012 sürümüne dahildir. Profesyonel, Premium ve Ultimate sürümlerinde tüm kurallar dahil edilmiştir. Windows 8 ve Windows Phone için Express sürümlerinde yalnızca en kritik uyarılar dahil edilmiştir. Web için Express Edition 'da kod analizi dahil değildir.
Diğer kod analizi geliştirmeleri aşağıda verilmiştir:

- Yeni eşzamanlılık uyarıları, çok iş parçacıklı C/C++ programlarındaki doğru kilitleme disiplinlerinin kullandığınızdan emin olarak eşzamanlılık hatalarından kaçınmanıza yardımcı olur. Çözümleyici olası yarış durumlarını, kilit sırası ınmallerini, çağıran/çağrılan, anlaşma ihlallerini, eşleşmeyen eşitleme işlemlerini ve diğer eşzamanlılık hatalarını algılar.
- Kural kümelerini kullanarak, C++ kod analizi çalıştırmaları için uygulamak istediğiniz kuralları belirtebilirsiniz.
- **Kod Analizi** penceresinde, seçili bir uyarıyı gösteren bir pragma kaynak koduna ekleyebilirsiniz.
- Bir işlevin parametrelerini nasıl kullandığını, kendileri hakkında yaptığı varsayımları ve bunun garanti edilmesini sağlamak için, Microsoft kaynak kodu ek açıklama dili 'nin (SAL) yeni sürümünü kullanarak statik kod analizinin doğruluğunu ve tamamlananmasını artırabilirsiniz. tamamlandığında yapar.
- 64bit C++ projeleri için destek.

#### <a name="updated-unit-test-framework"></a>Güncelleştirilmiş birim test çerçevesi

Birim testlerini yazmak C++ C++ için Visual Studio 'da yeni birim testi çerçevesini kullanın. Yeni proje iletişim kutusundaki görsel C++ C++ C++ kategori altında bulunan birim testi proje şablonunu bularak varolan çözümünüze yeni bir birim test projesi ekleyin. UnitTest1. cpp dosyasındaki oluşturulan TEST_METHOD Code saplamasında birim testlerinizi yazmaya başlayın. Test kodu yazıldığında Çözümü derleyin. Testleri çalıştırmak istediğinizde,**diğer Windows** > **birim testi Gezginini** **görüntüle** > ' yi seçerek bir **birim testi gezgin** penceresi açın ve ardından istediğiniz test çalışmasının kısayol menüsünde Çalıştır ' ı seçin.  **seçili test**. Test çalıştırması bittikten sonra, test sonuçlarını ve ek yığın izleme bilgilerini aynı pencerede görüntüleyebilirsiniz.

#### <a name="architecture-dependency-graphs"></a>Mimari bağımlılık grafikleri

Kodunuzu daha iyi anlamak için artık ikili, sınıf, ad alanı ve ekleme dosyaları için bir çözüme bağımlılık grafikleri oluşturabilirsiniz. Menü çubuğunda, **mimari** > **bağımlılık grafiği oluştur**' u ve ardından bir bağımlılık grafiği oluşturmak için **çözüm** ya da **içerme dosyası için bir dosya** seçin. Grafik oluşturma işlemi tamamlandığında, her bir düğümü genişleterek, düğümler arasında hareket ederek bağımlılık ilişkilerini öğrenerek ve düğüm için kısayol menüsünde **Içeriği görüntüle** ' yi seçerek kaynak koda göz atarak bunu keşfedebilirsiniz. İçerme dosyaları için bir bağımlılık grafiği oluşturmak üzere, \*. cpp kaynak kodu dosyası veya \*. h üstbilgi dosyası için kısayol menüsünde, **ekleme dosyalarının grafiğini oluştur**' u seçin.

#### <a name="architecture-explorer"></a>Mimari Gezgini

**Mimari Gezginini**kullanarak C++ çözümünüzdeki, projelerinizde veya dosyalarınızda varlıkları keşfedebilirsiniz. Menü çubuğunda **mimari** > **Windows** > **Mimari Gezgini**' ni seçin. İlgilendiğiniz bir düğümü seçebilirsiniz, örneğin, **sınıf görünümü**. Bu durumda, araç penceresinin sağ tarafı bir ad alanı listesi ile genişletilir. Bir ad alanı seçerseniz, yeni bir sütun bu ad alanındaki sınıfların, yapıların ve Numaralandırmaların bir listesini gösterir. Bu varlıkları keşfetmeye devam edebilir veya başka bir sorgu başlatmak için en soldaki sütuna geri dönebilirsiniz. Bkz. **Mimari Gezgini Ile kod bulma**.

#### <a name="code-coverage"></a>Kod Kapsamı

Kod kapsamı, çalışma zamanında dinamik olarak araç ikilileriyle güncelleştirildi. Bu, yapılandırma yükünü düşürür ve daha iyi performans sağlar. Ayrıca, uygulamalar için C++ birim testlerinden kod kapsamı verileri toplayabilirsiniz. C++ Birim testleri oluşturduğunuzda, çözümünüzdeki testleri öğrenmek Için **birim test Gezgini** ' ni kullanabilirsiniz. Birim testlerini çalıştırmak ve bunlara yönelik kod kapsamı verilerini toplamak için, **birim testi Gezgini**'Nde **kod kapsamını çözümle**' yi seçin. Kod kapsamı sonuçlarını **kod kapsamı** sonuçları penceresinde inceleyebilirsiniz: menü çubuğunda, **Test** > **Windows** > **kod kapsamı sonuçları**' nı seçin.

## <a name="whats-new-for-c-in-visual-studio-2010"></a>Visual Studio 2010 C++ ' deki yenilikler

### <a name="c-compiler-and-linker"></a>C++Derleyici ve bağlayıcı

**auto anahtar sözcüğü.** **Auto** anahtar sözcüğünün yeni bir amacı vardır. Değişkeni, değişkenin bildiriminde başlatma ifadesinden çıkarılan bir değişken bildirmek için **Auto** anahtar sözcüğünün varsayılan anlamını kullanın. Derleyici seçeneği, auto anahtar sözcüğünün yeni ya da önceki anlamını çağırır. `/Zc:auto`

**decltype türü belirleyicisi.** **Decltype** türü tanımlayıcısı, belirtilen bir ifadenin türünü döndürür. Karmaşık veya yalnızca derleyicinin bildiği bir türü bildirmek için **Auto** anahtar sözcüğüyle birlikte **decltype** tür belirticisini kullanın. Örneğin, dönüş türü kendi şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevi bildirmek için birleşimini kullanın. Ya da başka bir işlevi çağıran bir şablon işlevi bildirin, sonra çağrılan işlevin dönüş türünü döndürür.

**Lambda Ifadeleri.** Lambda işlevlerinin bir işlev gövdesi vardır ancak adı yoktur. Lambda işlevleri, işlev işaretçilerinin ve işlev nesnelerinin en iyi özelliklerini birleştirir. Bir Lambda işlevini, bir işlev nesnesi yerine şablon işlev parametresi olarak veya türü lambda olan bir değişkeni bildirmek için **Auto** anahtar sözcüğüyle birlikte kullanın.

**Rvalue başvurusu.** Rvalue başvuru bildirimci (& &) bir rvalue başvurusu bildirir. Rvalue başvurusu, daha verimli oluşturucular, işlevler ve şablonlar yazmak için taşıma semantiğini ve kusursuz iletme özelliğini kullanmanıza olanak sağlar.

**static_assert bildirimi.** Bir **static_assert** bildirimi, çalışma zamanında test eden diğer onaylama mekanizmalarından farklı olarak, derleme zamanında bir yazılım onayını sınar. Onaylama başarısız olursa, derleme başarısız olur ve belirtilen bir hata iletisi verilir.

**nullptr ve __nullptr anahtar sözcükleri.** MSVC, yerel kodla veya yönetilen kodla **nullptr** anahtar sözcüğünü kullanmanıza olanak sağlar. **Nullptr** anahtar sözcüğü bir nesne tanıtıcısı, iç işaretçi veya yerel işaretçi türünün bir nesneyi işaret içermediğini belirtir. Derleyici, `/clr` derleyici seçeneğini kullandığınızda **nullptr** 'yi yönetilen kod olarak yorumlar ve `/clr` seçeneğini kullanmazsanız yerel koddur.
Microsoft 'a özgü **__nullptr** anahtar sözcüğü, **nullptr**ile aynı anlama sahiptir, ancak yalnızca yerel kod için geçerlidir. `/clr` Derleyici seçeneğini kullanarak yerel C/C++ Code derlerseniz, derleyici **nullptr** anahtar sözcüğünün yerel mi yoksa yönetilen bir terim mi olduğunu belirleyemez. Derleyicisini derleyiciye eklemek için, yönetilen terimi belirtmek için nullptr anahtar sözcüğünü ve yerel terimi belirtmek için **__nullptr** ' yi kullanın.

**/Zc: trigraf derleyici seçeneği.** Trigraf desteği varsayılan olarak devre dışıdır. Trigraf desteğini etkinleştirmek için derleyiciseçeneğinikullanın.`/Zc:trigraphs`
Üçlü grafik, birbirini izleyen iki soru işaretinden (??) ve ardından benzersiz bir üçüncü karakterden oluşur. Derleyici, karşılık gelen noktalama karakteriyle bir trigraf yerini alır. Örneğin, derleyici??? = # (sayı işareti) karakteri ile trigraf. Belirli noktalama karakterleri içermeyen bir karakter kümesi kullanan C kaynak dosyalarında trigraf kullanın.

**Yeni Profil temelli Iyileştirme seçeneği.** PogoSafeMode, uygulamanızı en iyi duruma getirmeye yönelik güvenli mod veya hızlı mod kullanıp kullanmayacağınızı belirtmenize imkan tanıyan yeni bir profil temelli iyileştirme seçeneğidir. Güvenli mod iş parçacığı açısından güvenlidir, ancak hızlı moddan daha yavaştır. Hızlı mod varsayılan davranıştır.

**Yeni ortak dil çalışma zamanı (CLR) seçeneği/clr: nostdlib.** (Ortak dil çalışma zamanı derlemesi `/clr` ) için yeni bir seçenek eklenir. Aynı kitaplıkların farklı sürümleri dahil edilip, bir derleme hatası verilir. Yeni seçenek, programınızın belirtilen bir sürümü kullanabilmesi için varsayılan CLR kitaplıklarını dışlamanızı sağlar.

**Yeni pragma yönergesi detect_mismatch.** Pragma yönergesi detect_mismatch, dosyalarınıza aynı ada sahip diğer etiketlerle karşılaştırılan bir etiket yerleştirmenizi sağlar. Aynı ad için birden çok değer varsa, bağlayıcı bir hata verir.

**XOP Iç bilgileri, FMA4 Içleri ve LWP Iç bilgileri.** Visual Studio 2010 SP1 için eklenen XOP iç işlevleri, Visual Studio 2010 SP1 için eklenen FMA4 l 'ler ve Visual Studio 2010 SP1 işlemci teknolojileri için eklenen LWP Iç işlevleri desteklemek için yeni iç işlevler eklenmiştir. Belirli bir bilgisayarda hangi işlemci teknolojilerinin desteklendiğini öğrenmek için __cpuıd, __cpuıdex kullanın.

### <a name="visual-studio-c-projects-and-the-build-system"></a>Visual Studio C++ projeleri ve derleme sistemi

**MSBUILD.** Visual C++ Solutions ve projeler artık vcbuild. exe ' nin yerini alan MSBuild. exe kullanılarak oluşturulmuştur. MSBuild, diğer Visual Studio dilleri ve proje türleri tarafından kullanılan esnek, Genişletilebilir, XML tabanlı derleme aracıdır. Bu değişiklik nedeniyle, Visual Studio C++ proje dosyaları artık bir XML dosya biçimi kullanır ve. vcxproj dosya adı uzantısına sahiptir. Visual Studio C++ 'nun önceki sürümlerinden Visual Studio proje dosyaları otomatik olarak yeni dosya biçimine dönüştürülür.

**VC + + dizinleri.** VC + + dizinleri ayarı artık iki yerde bulunur. VC + + dizinlerinin proje başına değerlerini ayarlamak için proje özellik sayfaları ' nı kullanın. VC + + dizinlerinin genel, yapılandırma başına değerlerini ayarlamak için **Özellik Yöneticisi** ve özellik sayfasını kullanın.

**Projeden projeye bağımlılıklar.** Önceki sürümlerde, projeler arasında tanımlanan bağımlılıklar çözüm dosyasında depolanmıştı. Bu çözümler yeni proje dosya biçimine dönüştürüldüğünde, bağımlılıklar proje-proje başvurularına dönüştürülür. Çözüm bağımlılıklarının ve projeden projeye başvuruların kavramları farklı olduğundan bu değişiklik uygulamaları etkileyebilir.

**Makrolar ve ortam değişkenleri.** New _ıTERATOR_DEBUG_LEVEL makrosu yineleyiciler için hata ayıklama desteğini çağırır. Eski _SECURE_SCL ve _HAS_ıTERATOR_HATA ayıklama makroları yerine bu makroyu kullanın.

### <a name="visual-c-libraries"></a>Visual C++ Kitaplıkları

**Eşzamanlılık Çalışma Zamanı kitaplıkları.** Eşzamanlılık Çalışma Zamanı Framework, eşzamanlı olarak çalışan uygulamaları ve bileşenleri destekler ve Visual C++'te eşzamanlı uygulamalar programlama çerçevesidir. Eşzamanlı uygulama programlamayı desteklemek için paralel Desenler kitaplığı (PPL), hassas paralellik gerçekleştirmeye yönelik genel amaçlı kapsayıcılar ve algoritmalar sağlar. Zaman uyumsuz aracılar Kitaplığı, aktör tabanlı bir programlama modeli ve bir, kaba veri akışı ve ardışık düzen oluşturma görevleri için arabirimler iletme iletisi sağlar.

**Standart C++ kitaplık.** Aşağıdaki listede, standart C++ kitaplıkta yapılan birçok değişikliğin birçoğu açıklanmaktadır.

- Yeni rvalue başvuru C++ dili özelliği, standart şablon kitaplığındaki birçok işlev için taşıma semantiğini ve kusursuz iletme uygulamak amacıyla kullanılmıştır. Taşıma semantiği ve kusursuz iletme, değişkenler veya parametreler ayıran veya atayan işlemlerin performansını önemli ölçüde geliştirir.
- Rvalue başvuruları, `auto_ptr` sınıftan daha güvenli bir akıllı işaretçi `unique_ptr` türü olan yeni sınıfı uygulamak için de kullanılır. `unique_ptr` Sınıf taşınabilir ancak kopyalanabilir değildir, güvenliği etkilemeden katı sahiplik semantiğini uygular ve Rvalue başvurularını algılayan kapsayıcılarla iyi sonuç verir. `auto_ptr` Sınıf kullanım dışıdır.
- On beş `find_if_not`yeni işlev, örneğin `copy_if`,, ve `is_sorted`, \<algoritma > başlığına eklenmiştir.
- \<Bellek > üstbilgisinde, yeni make_shared işlevi, nesne oluşturulduğu anda bir nesneye paylaşılan bir işaretçi oluşturmanın kullanışlı, sağlam ve verimli bir yoludur.
- Listedir bağlantılı listeler \<forward_list > üst bilgisi tarafından desteklenir.
- New `cbegin`, `cend` `const_iterator` , ve`crbegin`member işlevleribirkapsayıcıboyuncaİleriveya`crend` geri taşınan bir sağlar.
- \<System_error > üstbilgisi ve ilgili şablonlar, alt düzey sistem hatalarının işlenmesini destekler. `exception_ptr` Sınıfının üyeleri, iş parçacıkları arasında özel durumları aktarmak için kullanılabilir.
- Codecvt \<> üstbilgisi, Unicode karakterlerinin çeşitli kodlamalarının diğer kodlara dönüştürülmesini destekler.
- Ayrıcılar > üst bilgisi, \<düğüm tabanlı kapsayıcılar için bellek blokları ayırmaya ve serbest bırakma konusunda yardımcı olan çeşitli şablonları tanımlar.
- \<Rastgele > üst bilgisinde çok sayıda güncelleştirme vardır.

### <a name="microsoft-foundation-class-mfc-library"></a>Microsoft Foundation Class (MFC) kitaplığı

**Windows 7 özellikleri.** MFC birçok Windows 7 özelliğini destekler, örneğin, Şerit kullanıcı arabirimi (UI), görev çubuğu, atlama listeleri, sekmeli küçük resimler, küçük resim önizlemeleri, ilerleme çubuğu, simge kaplama ve arama dizini oluşturma. MFC birçok Windows 7 özelliğini otomatik olarak desteklediğinden, var olan uygulamanızı değiştirmeniz gerekebilir. Yeni uygulamalardaki diğer özellikleri desteklemek için, kullanmak istediğiniz işlevselliği belirtmek üzere MFC Uygulama Sihirbazı ' nı kullanın.

**Çok dokunmalı tanıma.** MFC, çok dokunmalı bir kullanıcı arabirimine sahip uygulamaları (örneğin, Microsoft Surface işletim sistemi için yazılmış uygulamaları) destekler. Çok dokunmalı bir uygulama, dokunmatik ileti bileşimleri olan Windows Touch iletilerini ve hareket iletilerini işleyebilir. Uygulamanızı dokunmatik ve hareket olayları için kaydetmeniz yeterlidir ve işletim sistemi, çok dokunmalı olayları olay İşleyicileriniz için yönlendirir.

**Yüksek DPı tanıma.** Varsayılan olarak, MFC uygulamaları artık yüksek DPı özellikli. Bir uygulama yüksek DPı (yüksek nokta/inç başına) kullanıyorsa, işletim sistemi Windows, metin ve diğer kullanıcı arabirimi öğelerini geçerli ekran çözünürlüğüne ölçeklendirebilir. Bu, ölçeklendirilen bir görüntünün doğru düzenlenmesinin ve kırpılmamış ya da pikselleştirileceği anlamına gelir.

**Yöneticiyi yeniden başlatın.** Yeniden başlatma Yöneticisi, belgeleri otomatik olarak kaydeder ve beklenmedik şekilde kapanmışsa veya yeniden başlatılırsa uygulamanızı yeniden başlatır. Örneğin, bir otomatik güncelleştirme tarafından kapatıldıktan sonra uygulamanızı başlatmak için yeniden başlatma Yöneticisi ' ni kullanabilirsiniz. Uygulamanızı yeniden başlatma yöneticisini kullanacak şekilde yapılandırma hakkında daha fazla bilgi için bkz **. nasıl yapılır: Yeniden başlatma Yöneticisi desteği**ekleyin.

**Uygulamaya CTaskDialog.** `CTaskDialog` Sınıfı Standart`AfxMessageBox` ileti kutusu yerine kullanılabilir. `CTaskDialog` Sınıfı, standart ileti kutusu ' na göre daha fazla bilgi görüntüler ve toplar.

#### <a name="safeint-library"></a>SafeInt Kitaplığı

Yeni SafeInt Kitaplığı, tamsayı taşması için bu hesabı güvenli aritmetik işlemler gerçekleştirir. Bu kitaplık, farklı tamsayılar türlerini de karşılaştırır.

#### <a name="new-active-template-library-atl-macros"></a>Yeni etkin şablon kitaplığı (ATL) makroları

PROP_ENTRY_TYPE ve PROP_ENTRY_TYPE_EX işlevlerini genişletmek için ATL 'ye yeni makrolar eklenmiştir. PROP_ENTRY_INTERFACE ve PROP_ENTRY_INTERFACE_EX, geçerli CLSID 'lerin bir listesini eklemenizi sağlar. PROP_ENTRY_INTERFACE_CALLBACK ve PROP_ENTRY_INTERFACE_CALLBACK_EX, bir CLSID 'nin geçerli olup olmadığını belirlemek için bir geri çağırma işlevi belirtmenize izin verir.

#### <a name="analyze-warnings"></a>/Analyze uyarıları

Çoğu `/analyze` (kurumsal kod analizi) uyarıları C çalışma zamanı (CRT), MFC ve ATL kitaplıklarından kaldırılmıştır.

#### <a name="animation-and-d2d-support"></a>Animasyon ve D2D desteği

MFC artık animasyon ve Direct2D grafiklerini desteklemektedir. MFC kitaplığı, bu işlevselliği desteklemeye yönelik çeşitli yeni MFC sınıfları ve işlevleri içerir. Ayrıca, bir D2D nesnesi ve bir animasyon nesnesinin projeye nasıl ekleneceğini göstermek için iki yeni izlenecek yol vardır. İzlenecek yollar şunlardır **: Bir MFC projesine** D2D nesnesi ekleme ve **izlenecek yol: Bir MFC projesine**animasyon ekleme.

### <a name="ide"></a>IDE

**Geliştirilmiş IntelliSense.** Visual C++ için IntelliSense, daha hızlı, daha doğru ve daha büyük projeleri işleyebilecek şekilde tamamen yeniden tasarlanmıştır. Bu geliştirmeyi başarmak için IDE, geliştirici tarafından kaynak kodu görüntüleme ve değiştirme ve IDE 'nin bir çözüm oluşturmak için kaynak kodu ve proje ayarlarını nasıl kullandığı arasında bir ayrım yapar.
Bu görev ayrımı nedeniyle **sınıf görünümü** ve yeni **Git** iletişim kutusu gibi gözatma özellikleri, eski derleme göz atma (. NCB) dosyasının yerini alan yeni bir SQL Server Desktop Database (. sdf) dosyasını temel alan bir sistem tarafından işlenir. Hızlı bilgiler, otomatik tamamlama ve parametre gibi IntelliSense özellikleri yalnızca gerektiğinde çeviri birimlerini ayrıştırmaya yardımcı olur. Yeni **çağrı hiyerarşisi** penceresi gibi karma özellikler, gözatmayla ve IntelliSense özelliklerinin bir birleşimini kullanır.
IntelliSense yalnızca sizin için gerekli olan bilgileri işlediğinden, IDE daha hızlı yanıt verir. Ayrıca, bilgiler daha güncel olduğundan IDE görünümleri ve pencereleri daha doğru. Son olarak, IDE altyapısı daha iyi düzenlenmiştir, daha yetenekli ve daha ölçeklenebilir olduğundan, daha büyük projeleri işleyebilir.

**Geliştirilmiş IntelliSense hataları.** IDE, IntelliSense kaybına neden olabilecek hataları daha iyi algılar ve bunların altındaki kırmızı dalgalı alt çizgileri görüntüler. Ayrıca IDE, IntelliSense hatalarını **hata listesi penceresine**bildirir. Soruna neden olan kodu göstermek için **hata Listesi penceresindeki**hataya çift tıklayın.

**Özelliği otomatik olarak tamamlamayı #include.** IDE, `#include` anahtar sözcüğü için otomatik tamamlamayı destekler. Yazdığınızda `#include`, IDE geçerli üstbilgi dosyalarının açılan liste kutusu oluşturur. Bir dosya adı yazarak devam ederseniz, IDE, girdinizi temel alarak listeye filtre uygular. Herhangi bir noktada, dahil etmek istediğiniz dosyayı listeden seçebilirsiniz. Bu, tam dosya adını bilmeden dosyaları hızlı bir şekilde eklemenizi sağlar.

**Öğesine gidin.** **Git** iletişim kutusu, projenizdeki belirli bir dizeyle eşleşen tüm sembolleri ve dosyaları aramanıza olanak tanır. Arama dizeniz üzerinde ek karakterler yazdığınızda Arama sonuçları hemen düzeltilir. **Sonuçlar** geri bildirim alanı, bulunan öğelerin sayısını söyler ve aramanızı sınırlandırıp sınırlandırmamaya karar vermenize yardımcı olur. **Tür/kapsam**, **konum**ve **Önizleme** geri bildirim alanları, benzer adlara sahip öğelerin belirsizliğini ortadan kaldırmaya yardımcı olur. Ayrıca, bu özelliği diğer programlama dillerini destekleyecek şekilde genişletebilirsiniz.

**Paralel hata ayıklama ve profil oluşturma.** Visual Studio hata ayıklayıcısı Eşzamanlılık Çalışma Zamanı farkındadır ve paralel işleme uygulamalarıyla ilgili sorunları gidermenize yardımcı olur. Uygulamanızın genel davranışını görselleştirmek için yeni eşzamanlılık profil Oluşturucu aracını kullanabilirsiniz. Ayrıca, görevlerin durumunu ve bunların çağrı yığınlarını görselleştirmek için yeni araç pencerelerini de kullanabilirsiniz.

**Şerit Tasarımcısı.** **Şerit Tasarımcısı** , MFC Şeridi Kullanıcı arabirimini oluşturup değiştirmenize olanak tanıyan bir grafik düzenleyicidir. Son şerit kullanıcı arabirimi, XML tabanlı bir kaynak dosyası (. mfcribbon-ms) tarafından temsil edilir. Mevcut uygulamalarda, geçici olarak birkaç satır kod ekleyerek ve ardından **Şerit Tasarımcısını**çağırarak geçerli şerit kullanıcı arabirimini yakalayabilirsiniz. Şerit kaynak dosyası oluşturulduktan sonra, el yazısı Şerit UI kodunuzu, şerit kaynağını yükleyen birkaç deyimle değiştirebilirsiniz.

**Çağrı hiyerarşisi.** **Çağrı hiyerarşisi** penceresi, belirli bir işlev tarafından çağrılan tüm işlevlere veya belirli bir işlevi çağıran tüm işlevlere gitmenize olanak tanır.

### <a name="tools"></a>Araçlar

**MFC sınıf Sihirbazı.** Visual C++ 2010, iyi kabul eden MFC sınıf Sihirbazı aracını geri getirir. MFC sınıf Sihirbazı, kaynak dosya kümelerini el ile değiştirmek zorunda kalmadan bir projeye sınıf, ileti ve değişken eklemenin kolay bir yoludur.

**ATL Denetim Sihirbazı.** ATL Denetim Sihirbazı artık `ProgID` alanı otomatik olarak doldurur. ATL denetiminde `ProgID`yoksa, diğer araçlar ile çalışmayabilir. Denetimlerin `ProgID` , **etkin denetim Ekle** iletişim kutusu olmasını gerektiren bir araç örneği. İletişim kutusu hakkında daha fazla bilgi için bkz. **ActiveX denetimi ekleme Iletişim kutusu**.

### <a name="microsoft-macro-assembler-reference"></a>Microsoft Macro Assembler Başvurusu

Inmmword veri türünün eklenmesi, Intel Gelişmiş vektör Uzantıları (AVX) yönergelerine eklenen 256 bitlik multimedya işlenenlerini destekler.

## <a name="whats-new-for-c-in-visual-studio-2008"></a>Visual Studio 2008 C++ ' deki yenilikler

### <a name="visual-c-integrated-development-environment-ide"></a>Visual C++ tümleşik geliştirme ORTAMı (IDE)

- ATL, MFC ve Win32 uygulamalarında oluşturulan iletişim kutuları artık Windows Vista stil kılavuzlarıyla uyumlu. Visual Studio 2008 kullanarak yeni bir proje oluşturduğunuzda, uygulamanıza eklediğiniz tüm iletişim kutuları Windows Vista stil kılavuzlarıyla uyumlu olacaktır. Visual Studio 'nun önceki bir sürümüyle oluşturduğunuz bir projeyi yeniden derleyebiliyorsanız, var olan iletişim kutuları, daha önce sahip oldukları aynı görünümü korur. Uygulamanıza iletişim kutusu ekleme hakkında daha fazla bilgi için bkz. **iletişim kutusu Düzenleyicisi**.

- **Atl Proje** Sihirbazı artık tüm kullanıcılar için bileşenleri kaydetme seçeneğine sahiptir. Visual Studio 2008 ' den başlayarak, **atl Proje** Sihirbazı tarafından oluşturulan com bileşenleri ve tür kitaplıkları, **tüm kullanıcılar için Kaydet**' i SEÇMEDIĞINIZ takdirde kayıt defterinin HKEY_CURRENT_USER düğümüne kaydedilir.
- **Atl Proje** Sihirbazı artık öznitelikli ATL projeleri oluşturma seçeneği sağlamaz. Visual Studio 2008 ile başlayarak, **atl Proje** Sihirbazı, yeni bir projenin öznitelikli durumunu değiştirme seçeneğine sahip değildir. Sihirbazın oluşturduğu tüm yeni ATL projelerinin artık öznitelik yok.
- Kayıt defterine yazma yeniden yönlendirilebilir. Windows Vista 'nın kullanıma sunulmasıyla, kayıt defterinin belirli bölümlerine yazmak için bir programın Yükseltilmiş modda çalıştırılması gerekir. Visual Studio 'Yu her zaman Yükseltilmiş modda çalıştırmak istenmez. Kullanıcı başına yeniden yönlendirme, hiçbir programlama değişikliği yapmadan HKEY_CLASSES_ROOT kayıt defteri yazma işlemlerini otomatik olarak HKEY_CURRENT_USER 'ye yönlendirir.
- **Sınıf Tasarımcısı** artık yerel C++ kod için sınırlı desteğe sahiptir. Visual Studio 'nun önceki sürümlerinde **Sınıf Tasarımcısı** yalnızca görsel C# ve Visual Basic ile çalıştı. C++Kullanıcılar artık **Sınıf Tasarımcısı**, ancak yalnızca salt okuma modunda kullanabilir. **Sınıf Tasarımcısı** ile birlikte C++kullanma hakkında daha fazla bilgi için, bkz. **Sınıf Tasarımcısı Visual C++ Code ile çalışma**.
- Proje sihirbazının artık C++ SQL Server projesi oluşturma seçeneği yoktur. Visual Studio 2008 ' den başlayarak yeni proje Sihirbazı C++ SQL Server projesi oluşturma seçeneğine sahip değildir. Visual Studio 'nun önceki bir sürümü kullanılarak oluşturulan SQL Server projeler yine de derleyip doğru çalışacaktır.

### <a name="visual-c-libraries"></a>Visual C++ Kitaplıkları

#### <a name="general"></a>Genel

- Uygulamalar, görsel C++ kitaplıkların belirli sürümleriyle bağlantılı olabilir. Bazen bir uygulama, bir sürümden sonra görsel C++ kitaplıklarda yapılan güncelleştirmelere bağlıdır. Bu durumda, önceki kitaplıkların sürümlerini içeren bir bilgisayarda uygulamayı çalıştırmak beklenmeyen davranışlara neden olabilir. Artık, kitaplıkların önceki bir sürümü olan bir bilgisayarda çalıştırılmaması için, bir uygulamayı kitaplıkların belirli bir sürümüne bağlayabilirsiniz.

#### <a name="stlclr-library"></a>STL/CLR Kitaplığı

- Görsel C++ artık STL/CLR kitaplığını içerir. STL/CLR kitaplığı, standart C++ kitaplık KITAPLıĞı (STL), ile C++ kullanım için ve .NET Framework ortak DIL çalışma zamanı (CLR) için bir alt kümesidir. STL/CLR ile artık yönetilen bir ortamda STL 'nin tüm kapsayıcılarını, yineleyicileri ve algoritmalarını kullanabilirsiniz.

#### <a name="mfc-library"></a>MFC Kitaplığı

- Windows Vista ortak denetimleri destekler. 18 yeni veya var olan sınıflarda 150 ' den fazla yöntem Windows Vista 'daki destek özelliklerine eklendi veya geçerli MFC sınıflarında işlevselliği geliştirmek için eklenmiştir.
- Yeni `CNetAddressCtrl` sınıf, IPv4 ve IPv6 adreslerini veya DNS adlarını girmenizi ve doğrulamanızı sağlar.
- Yeni `CPagerCtrl` sınıf, Windows sayfalayıcı denetiminin kullanımını basitleştirir.
- Yeni `CSplitButton` sınıf, varsayılan veya isteğe bağlı bir eylem seçmek için Windows SplitButton denetiminin kullanımını basitleştirir.

#### <a name="c-support-library"></a>C++ Destek Kitaplığı

- C++sıralama kitaplığını tanıtır. Sıralama kitaplığı, yerel ve yönetilen ortamlar arasında veri sıralaması için kolay ve iyileştirilmiş bir yol sağlar. Kitaplık, PInvoke kullanma gibi daha karmaşık ve daha az verimli yaklaşımlar için bir alternatiftir. Daha fazla bilgi için bkz.  **C++ sıralamaya genel bakış** .

#### <a name="atl-server"></a>ATL sunucusu

- ATL sunucusu paylaşılan kaynak proje olarak serbest bırakılır.
- ATL sunucu kodu tabanının çoğu, CodePlex 'te paylaşılan kaynak proje olarak yayımlanmıştır ve Visual Studio 2008 ' in parçası olarak yüklenmez. ATL Server ile ilişkili birçok dosya artık Visual Studio 'nun bir parçası değildir. Kaldırılan dosyaların listesi için bkz. **ATL sunucu dosyalarını kaldırma**.
- Atlenc. h ve yardımcı program işlevleri ve, atlutil. h ve atlpath. h tarafından oluşturulan veri kodlama ve kod çözme sınıfları artık ATL Kitaplığı 'nın bir parçasıdır.
- Microsoft, Visual Studio 'nun bu sürümleri desteklendiği sürece, Visual Studio 'nun önceki sürümlerinde bulunan ATL Server sürümlerini desteklemeye devam edecektir. CodePlex, ATL sunucu kodunun bir topluluk projesi olarak geliştirilmesine devam edecektir. Microsoft, ATL Server 'ın CodePlex sürümünü desteklemez.

### <a name="visual-c-compiler-and-linker"></a>Visual C++ derleyicisi ve bağlayıcı

#### <a name="compiler-changes"></a>Derleyici değişiklikleri

- Derleyici yönetilen artımlı yapıları destekler. Bu seçeneği belirttiğinizde, başvurulan bir derleme değiştiğinde Derleyici kodu yeniden deretmez. Bunun yerine, artımlı bir yapı gerçekleştirir. Dosyalar yalnızca değişiklikler bağımlı kodu etkiliyorsa yeniden derlenir.
- ATL sunucusu ile ilgili öznitelikler artık desteklenmiyor. Derleyici artık doğrudan ATL sunucusuyla ilgili olan birkaç özniteliği desteklememektedir. Kaldırılan özniteliklerin tüm listesi için bkz. son değişiklikler.
- Derleyici Intel Core mikro mimarisini destekler. Derleyici, kod oluşturma sırasında Intel Core mikro mimarisine yönelik ayarlamayı içerir. Varsayılan olarak, bu ayarlama açık ve Pentium 4 ve diğer işlemcilere de yardımcı olduğundan devre dışı bırakılamaz.
- İç yapı daha yeni AMD ve Intel işlemcileri destekler. Birçok yeni iç yönerge, daha yeni AMD ve Intel işlemcilerinde daha fazla işlevselliği destekler. Yeni iç bilgiler hakkında daha fazla bilgi için bkz. **ek Streaming SIMD Extensions 3 yönergeleri**, **Streaming SIMD Extensions 4 yönergeleri**, **SSE4A ve gelişmiş bit Işleme iç**bilgileri, **AES iç** **bilgileri, _mm_clmutapi64_sı128**ve **__rdtscp**.
- `__cpuid` İşlev güncelleştirildi. `__cpuid` ,İşlevleriartıkAMDveIntelişlemcilerinensondüzeltmelerindeki`__cpuidex` birkaç yeni özelliği desteklemektedir. `__cpuidex` İç öğe yenidir ve son işlemcilerle daha fazla bilgi toplar.
- `/MP` Derleyici seçeneği toplam derleme süresini azaltır. Bu `/MP` seçenek, dosyaları aynı anda derleyen birkaç işlem oluşturarak birkaç kaynak dosyayı derlemek için toplam süreyi önemli ölçüde azaltabilir. Bu seçenek, özellikle hiper iş parçacığı, birden çok işlemci veya birden çok çekirdeği destekleyen bilgisayarlarda yararlıdır.
- Derleyici seçeneği ve **__w64** anahtar sözcüğü kullanım dışıdır. `/Wp64` 64-bit taşınabilirlik sorunlarını algılayan derleyiciseçeneğive__w64anahtarsözcüğükullanımdankaldırılmıştırvederleyiciningelecekbirsürümünde`/Wp64` kaldırılacaktır. Bu derleyici seçeneği ve anahtar sözcüğü yerine 64 bitlik bir platformu hedefleyen bir MSVC kullanın.
- `/Qfast_transcendentals`döküm işlevleri için satır içi kod üretir.
- `/Qimprecise_fwaits``/fp:except` derleyici seçeneğini kullandığınızda blokları denemek için iç bekleme komutlarını kaldırır.

### <a name="linker-changes"></a>Bağlayıcı değişiklikleri

- Kullanıcı hesabı denetim bilgileri artık görsel C++ bağlayıcı (LINK. exe) tarafından yürütülebilir dosyalar için bildirim dosyalarına katıştırılır. Bu özellik varsayılan olarak etkindir. Bu özelliği devre dışı bırakma veya varsayılan davranışı değiştirme hakkında daha fazla bilgi için, bkz `/MANIFESTUAC` . (UAC bilgilerini bildirimde bulunan).
- Bağlayıcı artık Windows Vista 'nın `/DYNAMICBASE` adres alanı düzeni rastgele seçme özelliğini etkinleştirme seçeneğine sahiptir. Bu seçenek, uygulamanın yükleme sırasında rastgele olarak yeniden yapılıp yapılmayacağını belirtmek için bir yürütülebilir dosyanın üst bilgisini değiştirir.

## <a name="whats-new-for-c-in-visual-studio-2005"></a>Visual Studio 2005 C++ ' deki yenilikler

Visual C++ 2005 Service Pack 1 ' de aşağıdaki özellikler yenidir:

### <a name="intrinsics-for-x86-and-x64"></a>X86 ve x64 için iç bilgiler

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

### <a name="intrinsics-for-x64-only"></a>Yalnızca x64 için iç yapı

- __vmx_on
- __vmx_vmclear
- __vmx_vmlaunch
- __vmx_vmptrld
- __vmx_vmread
- __vmx_vmresume
- __vmx_vmwrite

### <a name="new-language-keywords"></a>Yeni dil anahtar sözcükleri

__sptr, __uptr

### <a name="new-compiler-features"></a>Yeni derleyici özellikleri

Derleyicinin bu sürümde son değişiklikleri vardır.

- ' 64-bit yerel ve çapraz derleyiciler.
- `/analyze`(Kurumsal kod analizi) derleyici seçeneği eklenmiştir.
- `/bigobj`derleyici seçeneği eklendi.
- `/clr:pure`, `/clr:safe` ve`/clr:oldSyntax` eklendi. (Daha sonra Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de kaldırılmıştır.)
- Kullanım dışı derleyici seçenekleri: Bu sürümde birçok derleyici seçeneği kullanımdan kaldırılmıştır; daha fazla bilgi için bkz. **kullanım dışı derleyici seçenekleri** .
- `/clr` Koddaki çift dönüştürme azaltılmıştır; daha fazla bilgi için bkz. **Double thunking (C++)** .
- `/EH`(Özel durum işleme modeli) `/EHs` veya artık throw dışında bir şeyle oluşturulan bir özel durumu yakalamak için kullanılamaz; kullanın. `/EHa`
- `/errorReport`(Iç derleyici hatalarını bildir) derleyici seçeneği eklenmiştir.
- `/favor`(64 için iyileştirin) derleyici seçeneği eklenmiştir.
- `/FA`, `/Fa` (Listeleme dosyası) derleyici seçeneği eklenmiştir.
- `/FC`(Tanılama 'da kaynak kodu dosyasının tam yolu) derleyici seçeneği eklenmiştir.
- `/fp`(Kayan nokta davranışını belirt) derleyici seçeneği eklenmiştir.
- `/G`(Işlemci için iyileştirme) Seçenekler derleyici seçeneği eklendi.
- `/G`(Işlemci için iyileştirme) Seçenekler derleyici seçeneği eklendi.
- `/G3``/G4` ,,`/G7`,, ve derleyiciseçeneklerikaldırılmıştır`/GB` . `/G6` `/G5` Derleyici artık tüm mimariler için en iyi çıkış dosyasını oluşturmayı deneyen bir "karıştırılan model" kullanır.
- `/Gf`kaldırıldı. Bunun `/GF` yerine (Yinelenen dizeleri ortadan kaldırın) kullanın.
- `/GL`(Tüm program Iyileştirmesi) artık ile `/CLRHEADER`uyumludur.
- `/GR`artık varsayılan olarak açık durumdadır.
- `/GS`(Arabellek güvenlik denetimi) artık güvenlik açığı bulunan işaretçi parametrelerine yönelik güvenlik koruması sağlar. `/GS`artık varsayılan olarak açık durumdadır. `/GS`Artık, `/clr` MSIL 'e (ortak dil çalışma zamanı derlemesi) derlenen işlevlerde de çalışır.
- `/homeparams`(Parametreleri yığına Kaydet) derleyici seçeneği eklenmiştir.
- `/hotpatch`(Düzeltme eki uygulanmış görüntü oluşturma) derleyici seçeneği eklenmiştir.
- Satır içi işlev buluşsal yöntemleri güncelleştirildi; daha fazla bilgi için bkz. **satır içi**, **__inline**, **__forceinline** ve **inline_depth**
- Birçok yeni iç işlev eklenmiştir ve daha önce belgelenmemiş çok sayıda iç yapı artık belgelenmiştir.
- Varsayılan olarak, başarısız olan yeni bir çağrı özel durum oluşturur.
- `/ML`ve `/MLd` derleyici seçenekleri kaldırılmıştır. Görsel C++ artık tek iş parçacıklı, STATIK bağlantılı CRT kitaplığı desteğini desteklememektedir.
- Derleyici `/O1`, ile `/O2` derlerken etkin olan adlandırılmış dönüş değeri iyileştirmesi (boyutu en aza indir, hızı Büyüt), `/Og` (Global iyileştirmeler) ve `/Ox` (tam iyileştirme) öğesini uyguladık.
- `/Oa`derleyici seçeneği kaldırılmıştır, ancak sessizce yok sayılacak; Derleyicinin nasıl diğer `restrict__declspec` ad kullandığını belirtmek için veyadeğiştiricilerinikullanın.`noalias`
- `/Op`derleyici seçeneği kaldırılmıştır. Bunun `/fp` yerine (kayan nokta davranışını belirt) kullanın.
- OpenMP artık görsel C++tarafından destekleniyor.
- `/openmp`(OpenMP 2,0 desteğini etkinleştir) derleyici seçeneği eklenmiştir.
- `/Ow`derleyici seçeneği kaldırılmıştır, ancak sessizce yok sayılacak. Derleyicinin nasıl diğer `restrict__declspec` ad kullandığını belirtmek için veyadeğiştiricilerinikullanın.`noalias`

### <a name="profile-guided-optimizations"></a>Profil Temelli İyileştirmeler

- `/QI0f`kaldırıldı.
- `/QIfdiv`kaldırıldı.
- `/QIPF_B`(B CPU adımlaması için errampa) derleyici seçeneği eklenmiştir.
- `/QIPF_C`(C CPU adımlaması için errampa) derleyici seçeneği eklenmiştir.
- `/QIPF_fr32`(Büyük 96 kayan nokta Yazmaçları kullanmayın) derleyici seçeneği eklenmiştir.
- `/QIPF_noPIC`(Konuma bağımlı kod oluştur) derleyici seçeneği eklenmiştir.
- `/QIPF_restrict_plabels`(Çalışma zamanında hiçbir Işlev Oluşturusız olduğunu varsay) derleyici seçeneği eklenmiştir.

### <a name="unicode-support-in-the-compiler-and-linker"></a>Derleyicide ve Bağlayıcıda Unicode Desteği

- `/vd`(Oluşturma yeniden oluşturmayı devre dışı bırak) artık, oluşturulmakta olan bir nesne üzerinde dynamic_cast Işleci kullanmanıza izin veriyor (/VD2)
- `/YX`derleyici seçeneği kaldırılmıştır. Bunun `/Yc` yerine (önceden derlenmiş üst bilgi dosyası `/Yu` oluştur) veya (önceden derlenmiş üst bilgi dosyası kullan) kullanın. Yapı yapılandırmalardan kaldırırsanız `/YX` ve bunu hiçbir şey ile değiştirirseniz, daha hızlı yapılar oluşmasına neden olabilir.
- `/Zc:forScope`artık varsayılan olarak açık durumdadır.
- `/Zc:wchar_t`artık varsayılan olarak açık durumdadır.
- `/Zd`derleyici seçeneği kaldırılmıştır. Yalnızca satır numarası hata ayıklama bilgileri artık desteklenmiyor. Bunun `/Zi` yerine kullanın (daha fazla bilgi için bkz. **/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)** ).
- `/Zg`Artık, C++ kaynak kodu dosyalarında değil yalnızca C kaynak kodu dosyaları üzerinde geçerlidir.
- `/Zx`(Hata ayıklama için Iyileştirilmiş Itanium kodu) derleyici seçeneği eklenmiştir.

### <a name="new-language-features"></a>Yeni dil özellikleri

- AttributeAttribute artık kullanım dışıdır.
- `appdomain__declspec`değiştirici eklendi.
- `__clrcall`çağırma kuralı eklendi.
- kullanım dışıC++bırakılmış () **declspec** değiştiricisi artık, bir Kullanıcı kullanım dışı bir sınıfa veya işleve erişmeyi denediğinde derleme zamanında görüntülenecek bir dize belirtmenize olanak tanır.
- **dynamic_cast** İşlecin son değişiklikleri yok.
- Yerel numaralandırmalar artık temel türü belirtmenizi sağlar.
- `jitintrinsicdeclspec`değiştirici eklendi.
- `noaliasdeclspec`değiştirici eklendi.
- `process__declspec`değiştirici eklendi.
- **abstract**, **override**ve **Sealed** yerel derlemeler için geçerlidir.
- **__restrict** anahtar sözcüğü eklendi.
- `restrictdeclspec`değiştirici eklendi.
- **__thiscall** artık bir anahtar sözcüktür.
- **__hizalanmamış** anahtar sözcük artık belgelenmiştir.
- **geçici** (C++) iyileştirmelere göre davranış saptadı.

### <a name="new-preprocessor-features"></a>Yeni Önişlemci özellikleri

- __CLR_VER önceden tanımlanmış makrosu eklendi.
- Comment (C/C++) pragma şimdi bir bağlayıcı `/MANIFESTDEPENDENCY` yorumu olarak kabul etmektedir. Comment için exestr seçeneği artık kullanım dışıdır.
- `embedded_idl`öznitelik ( `#import` yönerge) artık isteğe bağlı bir parametre alır.
- `fenv_access`Prag
- `float_control`Prag
- `fp_contract`Prag
- Genel değişkenler, pragma yönetilen, yönetilmeyen ve yönetilmeyen bölümlerde genel değişkenleriniz varsa, bunların bildirildiği sırada başlatılmaz. Bu, örneğin, yönetilmeyen genel bir değişken yönetilen genel değişkenlerle birlikte başlatılmışsa ve tamamen oluşturulmuş bir yönetilen nesne gerekliyse, olası bir son değişiklik budur.
- İnit_seg ile belirtilen bölümler artık salt okunurdur ve önceki sürümlerde okuma/yazma değildir.
- inline_depth varsayılan değer 16 ' dır. Visual C++ .NET 2003 ' de varsayılan 16 ' da etkilidir.
- _INTEGRAL_MAX_BITS önceden tanımlanmış makro eklendi, bkz. önceden tanımlanmış makrolar.
- _M_CEE, _M_CEE_PURE ve _M_CEE_SAFE önceden tanımlanmış makrolar eklendi, bkz. önceden tanımlanmış makrolar.
- _M_IX86_FP önceden tanımlanmış makro eklendi.
- _M_X64 önceden tanımlanmış makro eklendi.
- `make_public`Prag
- `managed`, `unmanaged` pragma sözdizimi güncelleştirildi ( `push` Şu anda ve `pop`)
- mscorlib. dll artık tüm `#using` `/clr` derlemelerde yönerge tarafından örtük olarak başvuruluyor.
- _OPENMP önceden tanımlanmış makrosu eklendi.
- optimize pragma güncelleştirildi, a ve w artık geçerli parametreler değildir.
- no_registry # import özniteliği eklendi.
- `region`, `endregion` pragmalar eklendi
- _VC_NODEFAULTLIB önceden tanımlanmış makrosu eklendi.
- Değişen sayıda makro artık uygulandı.
- `vtordisp`kullanım dışıdır ve sonraki bir görselin C++sürümünde kaldırılacaktır.
- `warning` Pragma artık gizleme belirticisine sahiptir.

### <a name="new-linker-features"></a>Yeni bağlayıcı Özellikleri

- Modüller (derleme olmayan MSIL çıkış dosyaları) artık bağlayıcıya giriş olarak izin verilir.
- `/ALLOWISOLATION`(Bildirim arama) bağlayıcı seçeneği eklendi.
- `/ASSEMBLYRESOURCE`(Yönetilen bir kaynağı katıştırma), şimdi derlemede kaynak adını belirtmenizi ve kaynağın derlemede özel olduğunu belirtmenizi sağlayacak şekilde güncelleştirilmiştir.
- `/CLRIMAGETYPE`(CLR görüntü türünü belirt) bağlayıcı seçeneği eklenmiştir.
- `/CLRSUPPORTLASTERROR`(PInvoke çağrıları için son hata kodunu koru) bağlayıcı seçeneği eklenmiştir.
- `/CLRTHREADATTRIBUTE`(CLR Iş parçacığı özniteliğini ayarla) bağlayıcı seçeneği eklenmiştir.
- `/CLRUNMANAGEDCODECHECK`(SuppressUnmanagedCodeSecurityAttribute ekleyin) bağlayıcı seçeneği eklendi.
- `/ERRORREPORT`(Iç bağlayıcı hatalarını raporla) bağlayıcı seçeneği eklenmiştir.
- `/EXETYPE`bağlayıcı seçeneği kaldırılmıştır. Bağlayıcı artık Windows 95 ve Windows 98 cihaz sürücülerini oluşturmayı desteklemiyor. Bu cihaz sürücülerini oluşturmak için uygun bir DDK kullanın. EXETYPE anahtar sözcüğü artık modül tanım dosyaları için geçerli değildir.
- `/FUNCTIONPADMIN`(Düzeltme eki uygulanmış görüntü oluşturma) bağlayıcı seçeneği eklenmiştir.
- `/LTCG`bağlayıcı seçeneği, ile `/clr`derlenen modüllerde artık desteklenmektedir. `/LTCG`Profil temelli iyileştirmeleri desteklemek için de güncelleştirilmiştir.
- `/MANIFEST`(Yan yana derleme bildirimi oluşturma) bağlayıcı seçeneği eklenmiştir.
- `/MANIFESTDEPENDENCY`(Bildirim Bağımlılıklarını Belirt) bağlayıcı seçeneği eklenmiştir.
- `/MANIFESTFILE`(Ad bildirim dosyası) bağlayıcı seçeneği eklendi.
- `/MAPINFO:LINES`bağlayıcı seçeneği kaldırılmıştır.
- `/NXCOMPAT`(Veri Yürütme Engellemesi ile uyumlu) bağlayıcı seçeneği eklenmiştir.
- `/PGD`(Profil temelli Iyileştirmeler için veritabanını belirt) bağlayıcı seçeneği eklenmiştir.
- `/PROFILE`(Performans araçları profil Oluşturucu) bağlayıcı seçeneği eklenmiştir.
- `/SECTION`(Bölüm özniteliklerini belirt) bağlayıcı seçeneği artık öznitelik olumsuzunu destekliyor ve artık L veya D (VxD ile ilişkili) özniteliklerini desteklemiyor.
- Derleyicide ve Bağlayıcıda Unicode Desteği
- `/VERBOSE`(Ilerleme Iletilerini Yazdır) bağlayıcı seçeneği artık ICF ve REF değerlerini de kabul eder.
- `/VXD`bağlayıcı seçeneği kaldırılmıştır. Bağlayıcı artık Windows 95 ve Windows 98 cihaz sürücülerini oluşturmayı desteklemiyor. Bu cihaz sürücülerini oluşturmak için uygun bir DDK kullanın. VXD anahtar sözcüğü artık modül tanım dosyaları için geçerli değildir.
- `/WS`bağlayıcı seçeneği kaldırılmıştır. `/WS`Windows NT 4,0 için hedeflenen görüntüleri değiştirmek için kullanılmıştır. IMAGECFG. exe-R dosya adı yerine `/WS`kullanılabilir. IMAGECFG. exe, SUPPORT\DEBUG\I386\ıMAGECFGIÇINDEKI Windows NT 4,0 CD-ROM ' da bulunabilir. EXE.
- `/WX`(Bağlayıcı uyarılarını hata olarak işle) bağlayıcı seçeneği artık belgelenmiştir.

### <a name="new-linker-utility-features"></a>Yeni bağlayıcı yardımcı programı özellikleri

- `/ALLOWISOLATION`Editbin seçeneği eklendi
- Açıklama Modülü tanım dosyası AÇıKLAMASı kaldırıldı. Bağlayıcı artık sanal cihaz sürücüleri oluşturmayı desteklemiyor.
- `/ERRORREPORT`seçenek bscmake. exe, dumpbin. exe, Editbin. exe ve lib. exe ' ye eklenmiştir.
- `/LTCG`LIB seçeneği eklendi.
- `/NXCOMPAT`Editbin seçeneği eklendi.
- `/RANGE`dumpbin seçeneği eklendi.
- `/TLS`dumpbin seçeneği eklendi.
- `/WS`Editbin seçeneği kaldırılmıştır. `/WS`Windows NT 4,0 için hedeflenen görüntüleri değiştirmek için kullanılmıştır. IMAGECFG. exe-R dosya adı yerine `/WS`kullanılabilir. IMAGECFG. exe, SUPPORT\DEBUG\I386\ıMAGECFGIÇINDEKI Windows NT 4,0 CD-ROM ' da bulunabilir. EXE.
- /WX [: NO] lib seçeneği eklendi.

### <a name="new-nmake-features"></a>Yeni NMAKE özellikleri

- `/ERRORREPORT`eklendi.
- `/G`eklendi.
- Önceden tanımlanmış kurallar güncelleştirildi.
- Özyineleme makrosunda belgelenen $ (MAKE) makrosu, artık nmake. exe ' nin tam yolunu verir.

### <a name="new-masm-features"></a>Yeni masa özellikleri

- Masd ifadeleri artık 64 bitlik değerlerdir. Önceki sürümlerde Masd ifadeleri 32 bitlik değerlerdir.
- __Asm INT 3 yönergesi şimdi bir işlevin yerel olarak derlenmesine neden oluyor.
- DIĞER ad (Masd) artık belgelenmiştir.
- `/ERRORREPORT`ml. exe ve ml64. exe seçeneği eklenmiştir.
- . Şimdi belgelenmiştir.
- H2INC. exe, Visual C++ 2005 ile birlikte gelmez. H2INC kullanmaya devam etmeniz gerekiyorsa, Visual C++'ın önceki BIR sürümünden H2INC. exe ' yi kullanın.
- ıMAGEREL işleci eklendi.
- operator HıGH32 eklendi.
- operator LOW32 eklendi.
- ml64. exe, x64 mimarisi için bir Masd sürümüdür. X64. asm dosyalarını x64 nesne dosyalarına ayrıştırır. Satır içi derleme dili x64 derleyicisinde desteklenmez. Ml64. exe (x64) için aşağıdaki masa yönergeleri eklenmiştir:
- .ALLOCSTACK
- .ENDPROLOG
- .PUSHFRAME
- .PUSHREG
- .SAVEREG
- .SAVEXMM128
- . SETFRAME Ayrıca, PROC yönergesi yalnızca x64 sözdizimi ile güncelleştirildi.
- MMWORD yönergesi eklendi
- `/omf`(ML. exe komut satırı seçeneği) artık şunları `/c`gösterir. ML. exe, OMF biçim nesnelerinin bağlanmasını desteklemez.
- SEGMENT yönergesi artık ek öznitelikleri desteklemektedir.
- BÖLÜREL işleci eklendi.
- XMMWORD yönergesi eklendi

### <a name="new-crt-features"></a>Yeni CRT özellikleri

- Çeşitli işlevlerin güvenli sürümleri eklendi. Bu işlevler, hataları daha iyi bir şekilde işler ve yaygın güvenlik hatalarından kaçınmak için arabelleklerdeki sıkı denetimleri uygular. Yeni güvenli sürümler **_s** soneki tarafından tanımlanır.
- Birçok işlevin var olan daha az güvenli sürümleri kullanımdan kaldırılmıştır. Kullanımdan kaldırma uyarılarını devre dışı bırakmak için _CRT_SECURE_NO_WARNINGS tanımlayın.
- Varolan birçok işlev artık parametrelerini doğrular ve geçersiz parametre geçirildiğinde geçersiz parametre işleyicisini çağırır.
- Birçok mevcut işlev artık daha `errno` önce olmadıkları yerde ayarlanır.
- Tamsayı türünde `errno_t` typedef eklendi. `errno_t`bir işlev dönüş türü veya parametresi, öğesinden `errno`hata kodlarıyla ilişkili olduğunda kullanılır. `errno_t`değiştirilir `errcode`.
- Yerel ayara bağımlı işlevler artık geçerli yerel ayarı kullanmak yerine yerel ayarı parametre olarak kullanan sürümlere sahiptir. Bu yeni işlevler **_l** sonekine sahiptir. Yerel ayar nesneleriyle çalışacak birkaç yeni işlev eklenmiştir. Yeni işlevler, `_get_current_locale` `_create_locale` ve`_free_locale`içerir.
- Dosya tanıtıcılarının kilitlenmesini ve kilidinin açılmasını desteklemek için yeni işlevler eklenmiştir.
- Önceki sürümlerde olduğu gibi, işlev ailesibaşarıdurumundaerrno,sıfırolaraksıfırlanmaz.`_spawn`
- Bağımsız değişkenlerin kullanılacağı sırayı belirtmenize izin veren işlevlerin ailesisürümleri.`printf`
- Unicode artık desteklenen bir metin biçimidir. İşlevi `_open` _o_textw, _o_utf8 ve _o_utf16 özniteliklerini destekler. `fopen` İşlevi, Unicode biçimi belirtmeye yönelik "CCS = ENCODING" yöntemini destekler.
- Yönetilen kodda (MSIL) oluşturulan CRT kitaplıklarının yeni bir sürümü artık kullanılabilir ve `/clr` (ortak dil çalışma zamanı derlemesi) seçeneğiyle derlenirken kullanılır.
- _fıleınfo kaldırıldı.
- İçin `time_t` varsayılan boyut artık 64 bittir, bu da `time_t` aralığını ve birkaç süreyi de 3000 yılına kadar genişletir.
- CRT artık iş parçacığı başına yerel ayarı ayarlamayı desteklemektedir. İşlev `_configthreadlocale` , bu özelliği desteklemek için eklenmiştir.
- `_statusfp2` Ve`__control87_2` işlevleri, hem x87 hem de SSE2 kayan nokta işlemcisinde kayan nokta denetim sözcüğünün erişimine ve denetime izin vermek için eklenmiştir.
- `_mkgmtime` Ve`_mkgmtime64` işlevleri, saatleri (struct tm) Greenwich Ortalama saatine (GMT) dönüştürme desteği sağlamak için eklenmiştir.
- `swprintf` Ve`vswprintf` standart ile daha iyi uyum sağlamak için değişiklikler yapıldı.
- Yeni bir üst bilgi dosyası, ıNTRIN. H, bazı iç işlevler için prototipler sağlar.
- `fopen` İşlevin şimdi bir N özniteliği vardır.
- `_open` İşlevin şimdi bir _o_noınherit özniteliği vardır.
- İşlev artık INT_MAX döndürüyor ve taşma üzerinde ERANGE olarak ayarlıyor `errno`. `atoi` Önceki sürümlerde, taşma davranışı tanımsızdır.
- İşlev `printf` ailesi,% a ve% a biçim türü belirticileri kullanılarak ANSI C99 standardına göre uygulanan onaltılık kayan nokta çıkışını destekler.
- `printf` Aile artık "ll" (uzun uzun) boyut önekini destekliyor.
- `_controlfp` İşlev daha iyi performans için iyileştirildi.
- Bazı işlevlerin hata ayıklama sürümleri eklendi.
- Eklendi `_chgsignl` ve`_cpysignl` (uzun çift sürümler).
- Tür `_locale_t` tablosuna tür eklendi.
- Bir dizideki `_countof` öğelerin sayısı hesaplanırken yeni makro makrosu eklendi.
- Her bir işlev konusu .NET Framework eşdeğerleri için bir bölüm eklenmiştir.
- Artık birkaç dize işlevi, çıkış arabellekleri çok küçük olduğunda başarısız olması yerine dizeleri kesilme seçeneğine sahiptir; bkz. **_Truncate**.
- `_set_se_translator`Artık `/EHa` derleyici seçeneğinin kullanılmasını gerektirir.
- `fpos_t`Artık **__int64** `/Za` (C kodu için) ve __stdc__ el ile ayarlandığında (kod için C++ ). **Yapı**olarak kullanılır.
- _CRT_DISABLE_PERFCRIT_LOCKS, tek iş parçacıklı programların g/ç performansını iyileştirebilir.
- POSIX adları ISO C++ uyumlu adları (örneğin, yerine kullanım `_getch` `getch`) kullanım dışı bırakılmıştır.
- Yeni bağlantı seçenekleri. obj dosyaları saf modda kullanılabilir
- `_recalloc`, `realloc` ve`calloc`özelliklerini birleştirir.

## <a name="whats-new-for-c-in-visual-studio-2003"></a>Visual Studio 2003 C++ ' deki yenilikler

### <a name="compiler"></a>Derleyici

- Çalışma zamanının önceki bir sürümünde, geçerli sürüm derleyicisi C++ ile oluşturulmuş bir uygulama Için yönetilen uzantıların nasıl çalıştırılacağı hakkında bilgiler.
- Sık sorulan sorular C++ Için yönetilen uzantılar.
- İçin C++yönetilen uzantıları kullanmak üzere mevcut, yerel bir uygulamanın bağlantı noktasının nasıl yapılacağını gösteren bir izlenecek yol eklenmiştir: İzlenecek yol: Mevcut bir yerel C++ uygulamanın .NET Framework bileşenleriyle birlikte çalışmak üzere taşıma.
- Artık bir değer türünün yönteminde bir temsilci oluşturabilirsiniz.
- Derleyicinin C++ standardı ile uyumluluğu, Visual C++ .NET 2003 için önemli ölçüde geliştirilmiştir.
- `/arch`derleyici seçeneği eklenmiştir.
- `/Gf`kullanım dışıdır ve sonraki görsel C++sürümünde kaldırılacaktır.
- `/G7`derleyici seçeneği eklenmiştir.
- Derleyici `/GS` seçeneği, yerel değişkenlerin doğrudan arabellek taşmalarına karşı korunmasına yardımcı olmak için geliştirilmiştir.
- `/noBool` Derleyici seçeneği kaldırılmıştır. Derleyici artık **bool** 'un bir C++ kaynak kod dosyasında yalnızca bir anahtar sözcük (tanımlayıcı değil) olarak görünmesine izin veriyor.
- **Uzun uzun** tür artık bir **__int64** **typedef** olarak kullanılabilir, CRT içinde henüz **uzun süredir** desteklenmeyen bir değer olmadığını unutmayın.
- `/Zm` Derleyici seçeneği artık önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir.
- _InterlockedCompareExchange iç artık belgelenmiş.
- _Interlockedazaltma iç artık belgelenmiş.
- _InterlockedExchange iç artık belgelenmiştir.
- _InterlockedExchangeAdd iç artık belgelenmiştir.
- _InterlockedIncrement iç şimdi belgelenmiştir.
- _Readwriteengel iç eklendi.

### <a name="attributes"></a>Öznitelikler

- `implements`öznitelik artık belgelenmiştir.

### <a name="linker-features"></a>Bağlayıcı Özellikleri

Aşağıdaki bağlayıcı anahtarları eklendi:

- /ASSEMBLYDEBUG
- /ASSEMBLYLINKRESOURCE
- DELAYSIGN
- /KEYFILE
- /KEYCONTAINER
- /SAFESEH

### <a name="masm"></a>MASM

İçin. SAFESEH yönergesi ve `/safeseh` ml. exe seçeneği eklenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)
