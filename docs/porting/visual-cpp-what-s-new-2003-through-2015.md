---
title: Visual C++ ne&#39;s yeni 2003 ile 2015 arasındaki
ms.date: 11/04/2016
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
ms.openlocfilehash: fdd1d2c2183d06defe413340b8aef05c5bd61750
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749158"
---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Visual C++ ne&#39;s yeni 2003 ile 2015 arasındaki

Bu sayfa, Visual Studio 2015'ten tüm "Yenilikler" sayfalar için tüm sürümlerinde Visual C++ 2003'e toplar. Durumda Visual C++'ın önceki sürümlerinden yükseltme sırasında yararlı olabilir, bu bilgileri bir kolaylık olarak sağlanır.

> [!NOTE]
> Visual Studio 2017 hakkında daha fazla bilgi için bkz: [Visual Studio 2017'deki Visual c++ yenilikleri](../what-s-new-for-visual-cpp-in-visual-studio.md) ve [Visual Studio 2017'de Visual c++ uyumluluk geliştirmeleri](../cpp-conformance-improvements-2017.md).

## <a name="whats-new-for-c-in-visual-studio-2015"></a>Visual Studio 2015'te C++ yenilikleri

Visual Studio 2015 ve sonraki sürümlerinde, derleyici uyumluluğu yapılan sürekli geliştirmeler bazen nasıl derleyici mevcut kaynak kodunuzu anlar değiştirebilirsiniz. Bu durumda, derleme veya kodda, daha önce derlenmiş ve düzgün şekilde çalışması için olduğu görülüyor bile davranışsal farklılıklar sırasında yeni veya farklı hata karşılaşabilirsiniz.

Neyse ki, bu farklılıkları çok az kayıpla veya hiç kaynak kodunuzun çoğunu etkisi ve bu farklar ele almak için kaynak kodu veya başka değişiklikler gerektiğinde, düzeltmeleri genellikle küçük ve rahatça. Daha önce kabul edilebilir kaynak kodunun değiştirilmesi gerekebilir birçok örnekler ekledik *(önce)* ve bunları düzeltmeye yönelik düzeltmeler *(sonra)*.

Bu farklılıklar, kaynak kodu veya diğer derleme yapıtlarının etkileyebilir olsa da, bunlar Visual C++ sürümleri için güncelleştirmeler arasında ikili uyumluluğu etkilemez. Değişiklik, daha ciddi bir tür *değişiklik* ikili uyumluluğu etkileyebilir, ancak ikili uyumluluğu sonları bu tür yalnızca önemli Visual C++ sürümü arasında oluşur. Örneğin, Visual C++ 2013 arasında Visual C++ 2015. Visual C++ 2015 ve Visual C++ 2013 arasında gerçekleşen bozucu değişiklikler hakkında daha fazla bilgi için bkz: [Visual C++ değişiklik geçmişi 2003-2015](../porting/visual-cpp-change-history-2003-2015.md).

- [Visual Studio 2015'te uyumluluk geliştirmeleri](#VS_RTM)

- [Visual Studio 2015 güncelleştirme 1'de uyumluluk geliştirmeleri](#VS_Update1)

- [Visual Studio 2015 güncelleştirme 2'de uyumluluk geliştirmeleri](#VS_Update2)

- [Visual Studio 2015 güncelleştirme 3, uyumluluk geliştirmeleri](#VS_Update3)

### <a name="VS_RTM"></a> Visual Studio 2015'te uyumluluk geliştirmeleri

- **/Zc:forScope- option**

   Derleyici seçeneği `/Zc:forScope-` kullanım dışıdır ve gelecek sürümde kaldırılacak.

   ```output
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release
   ```

   Seçeneği, genellikle, standardına göre kapsam dışına sahiplikten noktadan sonra değişkenleri kullanır döngü standart olmayan koda izin ver için kullanıldı. İle derlerken yalnızca gerekli `/Za` beri seçeneği olmadan `/Za`kullanarak bir döngünün sonunu her zaman izin verilir sonra Döngü değişkeninin. (Örneğin, kodunuz için taşınabilir diğer derleyicileri için tasarlanmamıştır) standartları uyumluluğu hakkında İlgilenmiyor, devre dışı `/Za` seçeneği (veya **dil uzantılarını devre dışı** özelliğini **yok** ). Taşınabilir, standartlara uyumlu kod yazma hakkında dikkatli olun, böylece bir noktaya döngü dışında bir tür değişken bildirimi taşıyarak standardına uygun kodunuzu yeniden yazmalıdır.

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

- **ZG derleyici seçeneği.**

   `/Zg` Derleyici seçeneği (işlev prototipleri oluşturma) kullanılabilir artık. Bu derleyici seçeneği önceden kullanım dışı bırakıldı.

- Artık birim testleri C + ile çalıştırabileceğiniz +/ CLI ile mstest.exe komut satırı üzerinden. Bunun yerine, vstest.console.exe kullanın

- **mutable anahtar sözcüğü.**

   **Değişebilir** depolama sınıfı tanımlayıcısı burada daha önce derlenmiş hatasız yerde artık verilir. Şimdi, derleyici hatası C2071 verir (depolama sınıfı). Standardına göre değişebilir tanımlayıcı yalnızca sınıf veri üyeleri adlarına uygulanan ve const veya statik bildirilen adlarına uygulanan ve üyeleri başvurmak için uygulanamaz.

   Örneğin, aşağıdaki kodu düşünün:

   ```cpp
    struct S {
        mutable int &r;
    };
   ```

   Visual C++ derleyicisinin önceki sürümlerinde bu kabul, ancak şimdi derleyici, aşağıdaki hatayı verir:

   ```Output
    error C2071: 'S::r': illegal storage class
   ```

   Hatayı düzeltmek için yedekli kaldırmanız **değişebilir** anahtar sözcüğü.

- **char_16_t ve char32_t**

   Bundan böyle kullanabileceğinizi `char16_t` veya `char32_t` bir typedef adlarda olarak çünkü bu tür artık yerleşik kabul edilir. Kullanıcılar ve tanımlamak için kitaplık yazarları için ortak `char16_t` ve `char32_t` diğer adlarını olarak `uint16_t` ve `uint32_t`sırasıyla.

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

   Kodunuzu güncelleştirmek için kaldırma **typedef** bildirimleri ve bu adları birbiriyle çakışır herhangi bir tanımlayıcıya yeniden adlandırın.

- **Türü olmayan şablon parametreleri**

   Açık şablon bağımsız değişkenleri sağlayın, tür olmayan şablon parametreleri içeren belirli kod artık doğru tür uyumluluğu için denetlenir. Visual C++'ın önceki sürümlerinde hatasız derlenir. Örneğin, aşağıdaki kodu.

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

   Geçerli derleyici şablon parametre türü, şablon bağımsız değişkeni eşleşmediği için doğru bir hata verir. (bir const üye işaretçisi parametredir, ancak const olmayan işlev f):

   ```Output
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'
   ```

   Kodunuzda bu hatayı gidermek için kullandığınız şablon bağımsız değişken türünü bildirilen şablon parametresinin türünü eşleştiğinden emin olun.

- **__declspec(align)**

   Derleyici artık kabul `__declspec(align)` işlevleri. Bu her zaman yoksayıldı, ancak artık, bir derleyici hatası oluşturur.

   ```cpp
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations
   ```

   Bu sorunu gidermek için kaldırın `__declspec(align)` gelen işlev bildirimi. Etkiye sahip olduğundan, kaldırarak her şeyi değiştirmez.

- **Özel durum işleme**

   Birkaç özel durum işleme için değişiklik vardır. İlk olarak, özel durum nesneleri kopyalanabilir ya da taşınabilir olması gerekir. Aşağıdaki kod, Visual Studio 2013'te derlenmiş, ancak Visual Studio 2015'te derleme yapmaz:

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

   Nesne kopyalanamaz, bir özel durum işleme normal kursun olduğu sürece bu nedenle, kopya oluşturucu özel sorunudur. Kopya Oluşturucu bildirildiğinde da aynı şekilde geçerlidir **açık**.

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

   Kodunuzu güncelleştirmek için kopya oluşturucusu, özel durum nesnesi için genel ve işaretlenmemiş olduğundan emin olun **açık**.

   Değere göre bir özel durum yakalama, özel durum nesnesi kopyalanabilir olmasını gerektirir. Aşağıdaki kod, Visual Studio 2013'te derlenmiş, ancak Visual Studio 2015'te derleme yapmaz:

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

   Parametre türü değiştirerek bu sorunu düzeltebilirsiniz **catch** bir başvuru.

   ```cpp
    catch(D& d)
    {
    }
   ```

- **Makroları tarafından izlenen bir dize değişmez değerleri**

   Derleyici kullanıcı tanımlı değişmez değerler artık desteklemektedir. Müdahalede bulunan tüm boşluk olmadan makroları ardından dize değişmez değerleri, hatalar veya beklenmeyen sonuçlar üretebilir kullanıcı tanımlı değişmez değer olarak, sonuç olarak yorumlanır. Örneğin, aşağıdaki kod önceki derleyicilerde başarıyla derlenir:

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

   Derleyici bunun bir dize olarak değişmez değer olarak "hello"var"genişletilir, bir makro tarafından izlenen" yorumlanan ve ardından iki dize değişmez değerleri birine art arda eklenmiş. Visual Studio 2015'te derleyici kullanıcı tanımlı değişmez değer olarak, bu yorumlar, ancak tanımlı hiçbir eşleşen kullanıcı tanımlı değişmez değer _x olduğundan, bir hata verir.

   ```cpp
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found
    note: Did you forget a space between the string literal and the prefix of the following string literal?

   ```

   Bu sorunu gidermek için dize sabit değeri ve makro arasına boşluk ekleyin.

- **Bitişik dize değişmez değerleri**

   Benzer şekilde önceki dize ayrıştırma, ilgili değişiklikleri nedeniyle için herhangi bir boşluk olmadan (ya da geniş veya dar karakter dize sabit değerleri) bitişik dize değişmez değerleri tek bir birleştirilmiş dizeyi Visaul C++'ın önceki sürümlerinde yorumlanan. Visual Studio 2015'te artık iki dizenin arasında boşluk eklemeniz gerekir. Örneğin, aşağıdaki kod değiştirilmelidir:

   ```cpp
    char * str = "abc""def";
   ```

   İki dizenin aralığındaki bir alan eklemeniz yeterlidir.

   ```cpp
    char * str = "abc" "def";
   ```

- **Yerleştirme yeni ve Sil**

   İçin bir değişiklik yapılmadığını **Sil** , C ++ 14 standart ile uyumluluk duruma getirmek için işleci. Standartlar değişiklik ayrıntılarını bulunabilir [C++ boyutlandırılmış ayırmayı kaldırma](http://isocpp.org/files/papers/n3778.html). Genel form değişiklikleri ekleme **Sil** boyutu parametresi alır. işleci. Operatör daha önce kullandıysanız olan değişiklik **Sil** aynı imzayla (karşılayacak şekilde bir **yerleştirme yeni** işleci), bir derleyici hatasına (gerçekleşen C2956, alırsınız bir noktada burada **yerleştirme yeni** kullanılır, derleyici nerede çalışırsa uygun eşleşen tanımlamak için kod konumda olduğundan **Sil** işleci).

   İşlev `void operator delete(void *, size_t)` olduğu bir **yerleştirme silme** karşılık gelen işleci **yerleştirme yeni** işlevi `void * operator new(size_t, size_t)` C ++ 11'de. C ++ 14 ile boyutlandırılmış ayırmayı kaldırma, bu **Sil** işlevi, artık bir *normal ayırmayı kaldırma işlevi* (genel **Sil** işleci). Standart olması durumunda kullanılmasını gerektirir. bir **yerleştirme yeni** karşılık gelen yedekleme arar **Sil** işlevi ve program bir normal ayırmayı kaldırma işlevi hatalı oluşturulmuş bulur.

   Örneğin, kodunuzu hem tanımladığını bir **yerleştirme yeni** ve **yerleştirme silme**:

   ```cpp
    void * operator new(std::size_t, std::size_t);
    void operator delete(void*, std::size_t) noexcept;
   ```

   Sorun, işlev imzaları arasında değiştirme dizininde eşleşmenin nedeniyle oluşur. bir **yerleştirme silme** tanımladığınız işleci ve yeni genel boyutta **Sil** işleci. Farklı bir tür dışında kullanıp kullanmayacağınızı düşünmeniz `size_t` herhangi **yerleştirme yeni** ve **Sil** işleçleri.  Unutmayın türü `size_t` **typedef** derleyici bağımlıdır; bu bir **typedef** için **işaretsiz int** Visual C++'ta. Bunun gibi bir listeden seçimli türü kullanmak iyi bir çözümdür:

   ```cpp
    enum class my_type : size_t {};
   ```

   Ardından, yerleştirme tanımınızı değiştirin **yeni** ve **Sil** bu tür yerine ikinci bağımsız değişkeni olarak kullanılacak `size_t`. Çağrıları güncelleştirin gerekecektir **yerleştirme yeni** yeni türü geçirmek için (kullanarak örneğin, `static_cast<my_type>` tamsayı değerini dönüştürmek için) ve tanımını güncelleştirmek **yeni** ve  **silme** tamsayı türüne dönüştürme yapmak. Kullanmanız gerekmez bir **enum** ; bunun için bir sınıf türü ile bir `size_t` üyesi da çalışır.

   Ortadan kaldırmak mümkün olabilir, alternatif bir çözüm olan **yerleştirme yeni** tamamen. Kodunuzu kullanıyorsa **yerleştirme yeni** burada yerleşimi bağımsız değişken nesnesi olma ayrılmış veya silinmiş boyutudur, ardından boyutlandırılmış ayırmayı kaldırma özelliği, kendi özel bellek havuzu kodunuzu değiştirmek uygun olabilir bir bellek havuzunda uygulamak için yerleştirme işlevlerini kurtulabilirsiniz ve yalnızca kendi iki bağımsız kullanın ve **Sil** yerleştirme işlevleri yerine işleci.

   Kodunuzu hemen güncelleştirmek istemiyorsanız, derleyici seçeneğini kullanarak eski davranışı için döndürebilirsiniz `/Zc:sizedDealloc-`. Bu seçenek, iki bağımsız kullanırsanız **Sil** işlevleri, mevcut olmayan ve bir çakışma ile neden olmaz, **yerleştirme silme** işleci.

- **Birleşim veri üyesi**

   Veri üyeleri birleşimler artık başvuru türlerine sahip olabilir. Aşağıdaki kod, Visual Studio 2013'te başarıyla derlenir, ancak Visual Studio 2015'te bir hata oluşturur.

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

   Yukarıdaki kod, aşağıdaki hatalar oluşturur:

   ```Output
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type
   ```

   Bu sorunu gidermek için başvuru türleri bir işaretçi veya bir değeri değiştirin. Bir işaretçi türü değiştirme birlik alanı kullanan kod değişiklikleri gerektirir. Kod bir değerle değiştirmeyi birleşim türleri alanları aynı bellek paylaşmak için bu durum diğer alanları etkiler birleşimde depolanan verileri değiştirin. Değer boyutuna bağlı olarak, bu Birleşimdeki boyutu değişebilir.

- **Anonim birleşimler**

   Daha fazla uyumlu standart sunulmuştur. Önceki derleyici sürümleri, bir açık oluşturucu ve yıkıcı anonim birleşimler için oluşturulur. Bu, Visual Studio 2015'te silinir.

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

   Yukarıdaki kod, Visual Studio 2015'te aşağıdaki hata oluşturur:

   ```cpp
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here
   ```

   Bu sorunu çözmek için oluşturucu ve/veya yıkıcıya kendi tanımlarını sağlar.

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

- **Anonim yapılar ile birleşimler**

   Standart uymak için anonim yapılar Birleşimlerdeki üye için çalışma zamanı davranışı değişti. Böyle bir birleşim oluşturulduğunda bir birleşim içindeki anonim Yapı üyeleri Oluşturucusu artık örtük olarak çağrılır. Ayrıca, bir birleşim içindeki anonim Yapı üyeleri için yok edici birleşim kapsam dışına çıktığında, artık örtük olarak çağrılır. Aşağıdaki kod, bir birleşim U bir yok Edicisi olan bir adlandırılmış yapısı S olan bir üyeyi içeren anonim bir yapı içeren göz önünde bulundurun.

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

   Birleşim oluşturulur ve işlev f için yığın temizlendiği S yok Edicisi çağrılır Visual Studio 2013'te S için oluşturucu çağrılır. Ancak Visual Studio 2015'te oluşturucu ve yıkıcı değil çağrılır. Derleyici, bu davranış değişikliği hakkında bir uyarı verir.

   ```Output
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called
   ```

   Özgün davranışı geri yüklemek için anonim yapının bir ad verin. Anonim olmayan yapılar çalışma zamanı davranışı, bir derleyici sürümünden bağımsız olarak aynıdır.

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

   Alternatif olarak, yeni işlevler oluşturucunun ve yıkıcının kod taşımayı deneyin ve bu işlevlere aramaların oluşturucusu ve yok edici birleşim için ekleyin.

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

- **Şablonu çözünürlüğü**

   Şablonlar için ad çözümlemesi için değişiklikler yapıldı. Bir ad çözümlemesi için aday değerlendirirken C++'da, bu durum dikkate alınarak olası eşleşme olarak bir veya daha fazla adları geçersiz şablon örneklemesi oluşturur olabilir. Bu geçersiz örneklemeleri normalde SFINAE (değiştirme hatası olduğundan olmayan bir hata) bilinen bir ilkeye derleyici hataları neden olmaz.

   Artık, bir sınıf şablonunun alt uzmanlaşması örneği oluşturmak için derleyicinin SFINAE gerektirir, bu işlem sırasında oluşan hataları derleyici hataları demektir. Önceki sürümlerde, derleyici bu tür hataları yoksayma. Örneğin, aşağıdaki kodu düşünün:

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

   Geçerli bir derleyici ile derleme yaparsanız, aşağıdaki hatayı alıyorsunuz:

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

   İs_base_of noktasında ilk çağrısıysa sınıfı değişeceği budur ' henüz tanımlanmadı.

   Bu durumda, sınıfın tanımlı kadar bu tür nitelikler kullanmayacak şekilde açıklanmıştır. Kod dosyasının başına B ve D tanımlarını taşırsanız, hata çözülür. Tanımları üstbilgi dosyalarında, sorunlu şablonları kullanılmadan önce herhangi bir sınıf tanımı derlenir emin olmak üst bilgi dosyaları dahil etme deyimlerini sırasını denetleyin.

- **Kopya oluşturucuları**

   Bu sınıfın kullanıcı tanımlı taşıma Oluşturucusu ancak hiçbir kullanıcı tanımlı kopya Oluşturucusu varsa Visual Studio 2013 ve Visual Studio 2015 derleyici bir sınıf için kopya Oluşturucu oluşturur. Dev14 içinde bu örtük olarak oluşturulan kopya Oluşturucu ayrıca işaretlenir "silme =".

### <a name="VS_Update1"></a> Visual Studio 2015 güncelleştirme 1'de uyumluluk geliştirmeleri

- **Özel sanal temel sınıflar ve dolaylı devralma**

   Önceki derleyici sürümleri izin türetilmiş bir sınıf üyesi işlevleri çağırmak kendi *dolaylı olarak türetilmiş* `private virtual` temel sınıflar. Bu eski davranışı yanlış ve C++ standartlarına uygun değil. Derleyici artık bu şekilde yazılmış kod kabul eder ve sonuç olarak derleyici hatası C2280 sorunlar.

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

  \-veya -

   ```cpp
    class base;  // as above

    class middle: private virtual base {};
    class top: public virtual middle, private virtual bottom {};

    void destroy(top *p)
    {
        delete p;
    }
   ```

- **Yeni aşırı yüklenmiş bir işleç ve delete işleci**

   Önceki derleyici sürümleri, üye olmayan izin **new işleci** ve üye olmayan **delete işleci** statik bildirilmesi ve dışında genel ad alanlarında bildirilmesi için.  Bu eski davranışı oluşturulan program değil çağırırsınız bir risk **yeni** veya **Sil** sessiz hatalı çalışma zamanı davranışları kaynaklanan Programcı hedeflenen işleci uygulaması. Derleyici artık bu şekilde yazılmış kod kabul eder ve bunun yerine derleyici hatası C2323 sorunlar.

   ```Output
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace.
   ```

   Örnek (önce)

   ```cpp
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323
   ```

   Örnek (sonra)

   ```cpp
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'
   ```

   Ayrıca, derleyici belirli tanılama getirmezse olsa da, yeni satır içi işleci yapılı değerlendirilir.

- **Çağırma ' işleci *türü*() ' (kullanıcı tanımlı dönüştürme) sınıf olmayan türler üzerinde** izin derleyicinin önceki sürümlerini ' işleci *türü*() ' sınıf olmayan türler sessizce sırada çağrılacak Bunu göz ardı ediliyor. Bu eski davranışı sessiz hatalı kod oluşturma, beklenmeyen çalışma zamanı davranışları kaynaklanan riski oluşturuldu. Derleyici artık bu şekilde yazılmış kod kabul eder ve bunun yerine derleyici hatası C2228 sorunlar.

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

   Örnek (sonra)

   ```cpp
    typedef int index_t;

    void bounds_check(index_t index);

    void login(int column)
    {
         bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'
    }
   ```

- **Ayrıntılandırılmış tür tanımlayıcıları, yedekli typename** izin derleyicinin önceki sürümlerini **typename** ayrıntılandırılmış tür tanımlayıcıları; bu şekilde yazılmış kod anlamsal olarak yanlıştır. Derleyici artık bu şekilde yazılmış kod kabul eder ve bunun yerine derleyici hatası C3406 sorunlar.

   ```Output
    error C3406: 'typename' cannot be used in an elaborated type specifier
   ```

   Örnek (önce)

   ```cpp
    template <typename class T>
    class container;
   ```

   Örnek (sonra)

   ```cpp
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case
    class container;
   ```

- **Bir başlatıcı listeden dizilerinin ifadeden tür çıkarma** önceki derleyici sürümleri bir başlatıcı listeden dizi türü kesintisi desteği. Derleyici artık bu tür kesintisi biçimi destekler ve sonuç olarak, başlatıcı listeleri kullanarak işlev şablonları çağrıları artık belirsiz olabilir veya farklı bir aşırı yüklemesini daha önceki bir derleyici sürümlerinde seçilmesi. Bu sorunları çözmek için program artık açıkça Programcı hedeflenen aşırı yük belirtmeniz gerekir.

   Bu yeni davranış eşit geçmiş adayı olarak kadar iyi bir ek aday dikkate alınması gereken aşırı yükleme çözünürlüğü neden olduğunda çağrısı belirsiz hale gelir ve derleyici derleyici hatası C2668 sonucunda verir.

   ```Output
    error C2668: 'function' : ambiguous call to overloaded function.
   ```

   Örnek 1: (Önce) aşırı yüklenmiş işleve belirsiz çağrı

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

   Örnek 1: (sonra) aşırı yüklenmiş işleve belirsiz çağrı

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

   Bu yeni davranış geçmiş aday daha iyi bir eşleşme arama için yeni aday, kesin bir şekilde çözümler olan ek bir aday dikkate alınması gereken aşırı yükleme çözünürlüğü neden olduğunda, programın davranışını bir değişiklik neden büyük olasılıkla farklıdır Programcı yöneliktir.

   Örnek 2: (önce) aşırı yükleme çözünürlüğü Değiştir

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

   Örnek 2: (sonra) aşırı yükleme çözünürlüğü Değiştir

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

- **Switch deyimi uyarıların geri yükleme**

   Derleyicinin önceki bir sürümünü önceden varolan uyarıları ilgili kaldırıldı **geçiş** deyimleri; bunlar uyarı şimdi geri yüklendi. Derleyici artık geri yüklenen uyarı verir ve belirli durumlarda (varsayılan durumda dahil) için ilgili uyarıların artık sorunlu durum içeren satırı yerine switch ifadesinin Son satırda verilir. Sonuç olarak bu uyarılar farklı satırlara geçmişte artık verme, uyarıları önceden gizlenen kullanarak `#pragma warning(disable:####)` artık beklendiği gibi bastırılabilir. Beklendiği gibi bu uyarıları bastırmak için taşımak gerekli olabilir `#pragma warning(disable:####)` ilk harfi büyük olasılıkla sorunlu üzerine bir satır için yönerge. Geri yüklenen uyarılar verilmiştir.

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

   C4063 (önce) örneği

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

   C4063 (sonra) örneği

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

   Geri yüklenen bir uyarı örnekleri kendi belgelerde verilmiştir.

- **#include: ana dizin tanımlayıcısı kullanın '..' pathname içinde** (yalnızca etkiler `/Wall` `/WX`)

   Önceki derleyici sürümleri üst dizini belirticisi kullanımını algılamadı '..' yol adını içinde `#include` yönergeleri. Bu şekilde yazılmış kod, genellikle projenin dışında yanlış proje göreli yollar kullanarak mevcut başlıkları da eklediğinizden yöneliktir. Bu eski davranışı program hedeflenen Programcı değerinden farklı bir kaynak dosyasındaki dahil ederek derlenebilir veya bu göreli yolları diğer yapı ortamları için taşınabilir olmayacaktır bir risk oluşturuldu. Derleyici artık algılar ve bu şekilde yazılmış kod Programcı size bildirir ve etkinleştirilirse C4464, uyarı bir isteğe bağlı derleyici verir.

   ```Output
    warning C4464: relative include path contains '..'
   ```

   Örnek (önce)

   ```cpp
    #include "..\headers\C4426.h"  // emits warning C4464
   ```

   Örnek (sonra)

   ```cpp
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories
   ```

   Derleyici belirli tanılama sağlamazsa ancak Ayrıca, ayrıca, üst dizini belirticisi öneririz "..." Not proje ekleme dizinleri belirtmek için kullanılmalıdır.

- **#pragma optimize() genişletir üstbilgi dosya sonunun** (yalnızca etkiler `/Wall` `/WX`)

   Önceki derleyici sürümleri, bir çeviri birimi içinde bulunan bir üstbilgi dosyası kaçış iyileştirme bayrağı ayarlarında yapılan değişiklikler algılamadı. Derleyici artık algılar ve bu şekilde yazılmış kod Programcı bildirir ve sorunlu konumda C4426 uyarı isteğe bağlı bir derleyici sorunları `#include`, etkin. Değişiklikler çakışma iyileştirme bayrakları derleyici komut satırı bağımsız değişkenleri olarak ayarlarsanız bu uyarı yalnızca görüntülenir.

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

- **#Pragma warning(push) eşleşmeyen** ve **#pragma warning(pop)** (yalnızca etkiler `/Wall` `/WX`)

   Önceki derleyici sürümleri algılamadı `#pragma warning(push)` durum değişikliklerini ile eşleştirilmiş `#pragma warning(pop)` durum nadiren yönelik farklı bir kaynak dosyasındaki değişiklikleri. Bu eski davranışı bir risk, oluşturulan program sessiz hatalı çalışma zamanı davranışını büyük olasılıkla kaynaklanan hazırlanan Programcı etkin uyarıları farklı bir dizi derlenecek. Derleyici artık algılar ve bu şekilde yazılmış kod Programcı bildirir ve eşleşen konumda C5031 uyarı isteğe bağlı bir derleyici sorunları `#pragma warning(pop)`, etkin. Bu uyarı karşılık gelen konum başvuran bir not içeren `#pragma warning(push)`.

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

   Bu şekilde yazılmış kod, bazen genel olmayan ancak kasıtlıdır. Bu şekilde yazılmış kod değişiklikleri için hassas `#include` sırası; mümkün olduğunda, kaynak kodu dosyaları uyarı durumuna bağımsız bir şekilde yönetmenizi öneririz.

- **Eşleşmeyen #pragma warning(push)** (yalnızca etkiler `/Wall` `/WX`)

   Önceki derleyici sürümleri algılamadı eşleşmeyen `#pragma warning(push)` durumu değiştiğinde bir çeviri birimi sonunda. Derleyici artık algılar ve bu şekilde yazılmış kod Programcı bildirir ve eşleşmeyen konumda C5032 uyarı isteğe bağlı bir derleyici sorunları `#pragma warning(push)`, etkin. Çeviri biriminde herhangi bir derleme hatası varsa, bu uyarı yalnızca görüntülenir.

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

   İzlenen derleyicinin önceki sürümlerini `#pragma warning` durumu değiştiğinde yeterince iyi hedeflenen tüm uyarılar verecek. Bu davranış, uyarıları etkili bir şekilde kullanılmaya Programcı farklı durumlarda atlanması, belirli bir risk oluşturuldu. Derleyici artık izler `#pragma warning` durumu daha yerine--özellikle ilgili `#pragma warning` durumu şablonları içinde--değiştirir ve isteğe bağlı olarak istenmeyenkullanımlarıbulunProgramcıyardımcıolmaamacınıtaşımaktadıryeniuyarılarC5031veC5032sorunları`#pragma warning(push)` ve `#pragma warning(pop)`.

   Sonucu olarak geliştirilmiş `#pragma warning` durumunda değişiklik izleme, eski adıyla yanlış gizlenen uyarılar veya önceden misdiagnosed sorunlarıyla ilgili uyarıları artık verilmiş.

- **Erişilemeyen kod daha iyi tanımlama**

   Derleyici belirli kodun ulaşılamaz olduğunu kanıtlamak, C++ Standart Kitaplığı değişiklikleri ve satır içi işlev çağrıları önceki derleyici sürümleri üzerinde geliştirilmiş olanağı sağlayabilir. Bu yeni davranış uyarısı C4720 örneklerini yeni ve daha sık verilen sonuçlanabilir.

   ```Output
    warning C4720: unreachable code
   ```

   Çoğu durumda, bu uyarı yalnızca iyileştirmeler derlenirken verilebilecek, bu yana iyileştirmeleri satır içi daha işlev çağrıları, gereksiz kod ortadan kaldırmak veya aksi halde belirli kodun ulaşılamaz olduğunu belirlemek mümkün kılar. Uyarı C4720 yeni örneklerini içinde sıkça gerçekleşen gözlenmiştir **try/catch** engeller, özellikle kullanımı ile ilgili [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True).

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

### <a name="VS_Update2"></a> Visual Studio 2015 güncelleştirme 2'de uyumluluk geliştirmeleri

- **Kısmi ifade SFINAE desteği sonucunda ek uyarılar ve hatalar verilebilir**

   Önceki derleyici sürümleri ifadelerinin içinde belirli bir türde değil ayrıştırma **decltype** tanımlayıcıları ifade SFINAE desteği eksikliği nedeniyle. Bu eski davranışı yanlış ve C++ standartlarına uygun değil. Derleyici artık bu deyimler ayrıştırır ve kısmi ifade SFINAE sürekli uyumluluk geliştirmeleri nedeniyle desteği vardır. Sonuç olarak, derleyici artık uyarı verir ve derleyicinin önceki sürümlerini değil ayrıştırma ifadelerinde hatalar bulundu.

   Bu yeni davranış ayrıştırmak için ne zaman bir **decltype** sorunları derleyici hatası C2039 sonucunda henüz bildirilmedi, derleyici bir türü içeren bir ifade.

   ```Output
    error C2039: 'type': is not a member of '`global namespace''
   ```

   Örnek 1: bildirilmemiş bir türü (önce) kullanın

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

   Bu yeni davranış ayrıştırmak için ne zaman bir **decltype** gerekli kullanımını eksik ifade **typename** anahtar sözcüğü bir tür, derleyici bağımlı bir ad olduğunu belirtmek için derleyici C4346 uyarı sorunları Derleyici Hatası C2923 birlikte.

   ```Output
    warning C4346: 'S2<T>::Type': dependent name is not a type
   ```

   ```Output
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'
   ```

   Örnek 2: bağımlı adı (önce) bir tür değil.

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

- `volatile` **üye değişkenleri önlemek örtük olarak tanımlı oluşturucular ve atama işleçleri** önceki derleyici sürümleri sahip bir sınıfı izin **geçici** varsayılan üye değişkenleri kopyalama/taşıma oluşturucuları ve otomatik olarak oluşturulan varsayılan kopyalama/taşıma atama işleçleri. Bu eski davranışı yanlış ve C++ standartlarına uygun değil. Derleyici artık otomatik olarak oluşturulan varsayılan uygulamaları bu işleçlerin önleyen Önemsiz oluşturma ve atama işleçleri için geçici üye değişkenlerine sahip bir sınıf olarak kabul eder. Bu tür bir sınıfının bir birleşim (veya bir sınıf içinde anonim birleşim) üyesi olduğunda, kopyalama/taşıma oluşturucuları ve kopyalama/taşıma atama işleçleri union (veya unonymous union içeren sınıfın) örtük olarak silindi olarak tanımlanır. Oluşturmak veya bunları açıkça tanımlamadan UNION (veya anonim birleşim içeren sınıf) kopyalama girişimi hatayla ve derleyici sorunları derleyici hatası C2280 sonuç olarak.

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

- **Statik üye işlevleri cv niteleyicileri desteklemez.**

   Visual C++ 2015'ın önceki sürümlerini cv niteleyicileri sağlamak statik üye işlevlerinde izin. Bu Visual C++ 2015 ve Visual C++ 2015 güncelleştirme 1'teki bir gerileme nedeniyle, davranıştır; Visual C++ 2013 ve Visual C++'ın önceki sürümleri bu şekilde yazılmış kod reddeder. Visual C++ 2015 ve Visual C++ 2015 güncelleştirme 1 davranışını yanlış ve C++ standardı için uygun değil.  Visual Studio 2015 güncelleştirme 2, bu şekilde yazılmış kod reddeder ve bunun yerine derleyici hatası C2511 verir.

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

   Örnek (sonra)

   ```cpp
    struct A
    {
      static void func();
    };

    void A::func() {}  // removed const
   ```

- **Enum İleri dönük bildirimi WinRT kodunda izin verilmiyor** (etkiler `/ZW` yalnızca)

   Windows çalışma zamanı (WinRT) izin vermeyen için derlenmiş kod **enum** türleri için .net yönetilen C++ kodu derlendiğinde İleri, benzer şekilde bildirilmesi için Framework kullanarak `/clr` derleyici anahtarı. Bu, davranıştır boyutu bir numaralandırmanın her zaman bilinen ve doğru şekilde WinRT türü sisteme öngörülen sağlar. Derleyici, bu şekilde yazılmış kod reddeder ve derleyici hatası c2599 arasındaki derleyici hatası C3197 birlikte verir.

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

- **Aşırı yüklenmiş üye olmayan işleç yeni ve delete işleci bildirilemez satır içi** (düzey 1 (`/W1`)-varsayılan)

   Önceki derleyici sürümleri üye olmayan olduğunda bir uyarı verme değil **new işleci** ve **delete işleci** İşlevler, satır içi bildirilir. Bu şekilde yazılmış kodu hatalı oluşturulmuş (tanılama gerekli) ve bellek kaynaklanan sorunlar uyumsuz yeni ve delete tanı koymak güç olabilir (özellikle boyutlandırılmış ayırmayı kaldırma ile birlikte kullanıldığında) işleçleri neden olabilir. Derleyici artık derleyici bu şekilde yazılmış kodu belirlemenize yardımcı olması için C4595 uyarı verir.

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

   Örnek (sonra)

   ```cpp
    void* operator new(size_t sz)  // removed inline
    {
      ...
    }
   ```

   Bu şekilde yazılmış kod çözme operatör tanımlarının dışında bir üstbilgi dosyası ve karşılık gelen bir kaynak dosyasına taşınması gerekebilir.

### <a name="VS_Update3"></a> Visual Studio 2015 güncelleştirme 3, uyumluluk geliştirmeleri

- **Std::is_convertable otomatik atanmasını artık algılar** (standart kitaplığı) önceki sürümlerini `std::is_convertable` türü niteliğine, kopya Oluşturucu silindiğinde bir sınıf türünün otomatik atanmasını veya özel doğru algılamadı. Şimdi, `std::is_convertable<>::value` düzgün ayarlandığından **false** silindiğinde veya özel kopya Oluşturucu sınıf türünde uygulandığında.

   Bu değişiklikle ilişkili hiçbir derleyici tanılama yoktur.

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

   Visual C++ önceki sürümlerinde, çünkü bu örnek altındaki statik onaylar geçirmek `std::is_convertable<>::value` yanlış ayarlandı **true**. Şimdi, `std::is_convertable<>::value` düzgün ayarlandığından **false**, statik bir onayları çökmesine neden olur.

- **Varsayılan veya önemsiz copy silindi ve taşıma oluşturucuları saygı erişim tanımlayıcıları**

   Derleyicinin önceki sürümlerini değil varsayılan yapılmış veya silinmiş bir önemsiz copy erişim belirleyici denetleyin ve bunları çağrılmasına izin vermeden önce taşıma oluşturucuları. Bu eski davranışı yanlış ve C++ standartlarına uygun değil. Bazı durumlarda, bu eski davranışı sessiz hatalı kod oluşturma, beklenmeyen çalışma zamanı davranışları kaynaklanan riski oluşturuldu. Derleyici artık varsayılan olarak ayarlanmış veya silinmiş bir önemsiz copy erişim belirleyici denetler ve taşıma oluşturucuları volat pouze jednou olup olmadığını ve değilse, sonuç olarak C2248 uyarı sorunları derleyici, belirlemek için.

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

- **Öznitelik atanmış ATL kodu desteğini kullanımdan** (düzey 1 (`/W1`)-varsayılan)

   ATL kodu kullanıldığında artık desteklenen derleyicinin önceki sürümlerini öznitelikli. Öznitelik atanmış ATL desteğini kaldırmanın sonraki aşamaya olarak kod [Visual C++ 2008'de başlangıcından](https://msdn.microsoft.com/library/bb384632), öznitelik atanmış ATL kodu kullanıldığında artık kullanımdan kaldırıldı. Derleyici artık derleyici bu tür bir kullanım dışı kod belirlemenize yardımcı olması için C4467 uyarı verir.

   ```Output
    warning C4467: Usage of ATL attributes is deprecated
   ```

   Öznitelik atanmış ATL kodu desteği derleyicinin kaldırılana kadar kullanmaya devam etmek istiyorsanız, bu uyarıyı geçirerek devre dışı bırakabilirsiniz `/Wv:18` veya `/wd4467` ekleyerek veya derleyici komut satırı bağımsız değişkenleri `#pragma warning(disable:4467)` , kaynak kodunuzdaki.

   Örnek 1 (önce)

   ```cpp
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
    class A {};
   ```

   Örnek 1 (sonra)

   ```cpp
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};
   ```

   Bazen gerekir veya bir IDL oluşturmak istediğiniz kullanımı önlemek için aşağıdaki örnek kod gibi ATL öznitelikleri kullanım dışı

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

   İlk olarak, *.idl dosya oluşturun; oluşturulan vc140.idl dosyası almak için kullanılabilir bir \*arabirimleri ve ek açıklamaları içeren .idl dosyası.

   Ardından, C++ arabirim tanımlarını oluşturulduğundan emin olmak için yapınıza MIDL adımı ekleyin.

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

   Ardından, ATL doğrudan uygulama dosyasında, aşağıdaki örnek kod olduğu gibi kullanın.

   Örnek 2 uygulaması (sonra)

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

- **Önceden derlenmiş üst bilgi (PCH) dosyaları ve eşleşmeyen #include** (yalnızca etkiler `/Wall` `/WX`)

   Önceki derleyici sürümleri kabul eşleşmeyen `#include` yönergeleri arasındaki kaynak dosyalarında `-Yc` ve `-Yu` kullanırken derlemeleri önceden derlenmiş üst bilgi (PCH) dosyaları. Bu şekilde yazılmış kod artık derleyici tarafından kabul edilir. Derleyicinin CC4598 belirlemenize yardımcı olması için uyarı sorunları derleyici eşleşmeyen artık `#include` PCH dosyalarını kullanırken yönergeleri.

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

- **Önceden derlenmiş üst bilgi (PCH) dosyaları ve eşleşmeyen ekleme kodu dizinleri** (yalnızca etkiler `/Wall` `/WX`)

   Kabul edilen derleyicinin önceki sürümlerini eşleşmeyen içeren dizin (`-I`) arasındaki derleyici komut satırı bağımsız değişkenleri `-Yc` ve `-Yu` kullanırken derlemeleri önceden derlenmiş üst bilgi (PCH) dosyaları. Bu şekilde yazılmış kod artık derleyici tarafından kabul edilir.   Derleyicinin CC4599 belirlemenize yardımcı olması için uyarı sorunları derleyici eşleşmeyen artık içeren dizin (`-I`) PCH dosyalarını kullanırken komut satırı bağımsız değişkenleri.

   ```Output
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position
   ```

   Örnek (önce)

   ```ms-dos
    cl /c /Wall /Ycc.h -I.. X.cpp
    cl /c /Wall /Yuc.h Z.cpp
   ```

   Örnek (sonra)

   ```ms-dos
    cl /c /Wall /Ycc.h -I.. X.cpp
    cl /c /Wall /Yuc.h -I.. Z.cpp
   ```

## <a name="whats-new-for-c-in-visual-studio-2013"></a>C++, Visual Studio 2013'teki yenilikler

### <a name="improved-iso-cc-standards-support"></a>Geliştirilmiş ISO C/C++ standartları desteği

#### <a name="compiler"></a>Derleyici

Microsoft Visual C++ derleyicisi, şu ISO C ++ 11 dil özelliklerini destekler:

- İşlev şablonları için varsayılan şablon bağımsız değişkenleri.
- Oluşturucuları temsilci olarak görevlendirme
- Açık dönüştürme işleçleri.
- Başlatıcı Listeleri ve Tekdüzen başlatma.
- Ham dize değişmez değerleri.
- Variadic şablonları.
- Diğer ad şablonları.
- Silinmiş işlevler.
- Statik olmayan veri üyesi başlatıcıları (Nsdmıs).
- Varsayılan işlevler. \*
- Şu ISO C99 dil özelliklerini destekler:
- _Bool
- Birleşik değişmez değerler.
- Belirtilen başlatıcılar.
- Bildirimleri kod ile karıştırma.
- Dize değiştirilebilir değerlere dönüştürme yeni derleyici seçeneğini kullanarak izin verilmeyen `/Zc:strictStrings`. C ++ 98, değişmez dize dönüştürme `char*` (ve geniş dize değişmez değerleri için `wchar_t*`) kullanım dışı bırakıldı. C ++ 11'de, dönüştürme tamamen kaldırıldı. Derleme kesinlikle standarda olsa da, bunun yerine sağladığı `/Zc:strictStrings` böylece dönüştürmeyi denetleyebilirsiniz seçeneği. Varsayılan olarak, seçenek kapalıdır. Bu seçenek hata ayıklama modunda kullanırken, STL'nin derlenmeyeceğine olduğunu unutmayın.
- rvalue/lvalue başvuru atamaları. Rvalue başvurularıyla C ++ 11 lvalues ve rvalues arasında NET bir şekilde ayırt edebilir. Daha önce Derleyici bunu belirli atama senaryolarında sağlamıyordu. Yeni bir derleyici seçeneği `/Zc:rvalueCast`, C++ dili çalışma Paper(see section 5.4, [expr.cast]/1) ile derleyici uyumlu hale getirmek üzere eklendi. Bu seçenek belirtilmediğinde varsayılan davranış, Visual Studio 2012 olduğu gibi aynıdır.

> [!NOTE]
> Kullanılan varsayılan işlevler için = varsayılan üye tabanlı taşıma oluşturucuları ve taşıma atama işleçleri desteklenmez.

### <a name="c99-libraries"></a>C99 kitaplıkları

Bu üst bilgileri eksik işlevler için bildirimler ve uygulamaları eklenir: math.h, ctype.h, wctype.h, stdıo.h, stdlıb.h ve wchar.h. Ayrıca eklenen yeni üstbilgi complex.h stdbool.h, fenv.h ve inttypes.h ve tüm işlevler için uygulamalar içinde bildirilen olan. Ve diğer birçok (ccomplex, cfenv, cinttypes, ctgmath)'de yeni C++ sarmalayıcı üstbilgileri vardır (ccomplex cctype, clocale, cmath, cstdint, cstdio, cstring, cwchar ve cwctype) güncelleştirildi.

### <a name="standard-template-library"></a>Standart Şablon Kitaplığı

C ++ 11 açık dönüştürme işleçleri, başlatıcı listeleri, kapsamlı numaralandırmalar ve değişen sayıda bağımsız değişken şablonlar için destek.
Tüm kapsayıcılar şimdi C ++ 11 ince detaylı öğe gereksinimlerini destekler.
Bu C ++ 14 özellikleri için destek:

- "Saydam işleç işlev nesneleri" <>, büyük <> artı <>, daha az <> vb. çarpar.
- make_unique<T>(args...) ve make_unique < T [] > (n)
- cbegin()/cend() rbegin()/rend() ve crbegin()/crend() üye harici işlevleri.
- \<atomik > çeşitli performans geliştirmeleri aldı.
- \<type_traits > ana sabitlemeyi ve kod düzeltmelerini aldı.

### <a name="breaking-changes"></a>Yeni Değişiklikler

Bu geliştirilmiş ISO C/C++ standartları desteği, C ++ 11 ile uyumlu olması ve Visual Studio 2013'te Visual C++'ta doğru derlendiğinden mevcut kodunda değişiklik yapılmasını gerektirebilir.

### <a name="visual-c-library-enhancements"></a>Visual C++ Kitaplık geliştirmeleri

- C++ REST SDK eklenir. Bu REST hizmetlerinin modern C++ uygulamasına sahiptir.
- C++ AMP doku desteği geliştirilmiştir. Artık, Mipmap ve yeni örnekleme modları için destek içerir.
- PPL görevleri birden fazla zamanlama teknolojisini ve zaman uyumsuz hata ayıklama desteği. Yeni API'lar normal sonuçlar ve özel durum koşulları için PPL görevlerinin oluşturulmasına etkinleştirin.

### <a name="c-application-performance"></a>C++ uygulama performansı

- Artık otomatik vektör hale getirici tanır ve kodunuzu daha hızlı çalışır hale getirmek için daha fazla C++ deseni en iyi duruma getirir.
- ARM platformu ve Atom mikro-mimarisi kod kalitesi geliştirmeleri.
- __vectorcall çağırma kuralı eklenir. Vektör türü bağımsız değişkenleri __vectorcall çağırma kuralını kullanarak vektör kayıt defterlerine geçirin.
- Yeni bağlayıcı seçenekleri. `/Gw` (Derleyici) ve `/Gy` (assembler) anahtarları bağlayıcı iyileştirmelerine yalın ikili dosyalar üretmesine olanak etkinleştirin.
- C++ AMP paylaşılan bellek desteği, azaltın veya verileri CPU ile GPU arasında kopyalama ortadan kaldırmak için.

### <a name="profile-guided-optimization-pgo-enhancements"></a>Profil temelli iyileştirme (PGO) geliştirmeleri

- Performans iyileştirmeleri PGO kullanılarak en iyi uygulamaları çalışma kümesi.
- Yeni PGO için Windows çalışma zamanı uygulama geliştirme.

### <a name="windows-runtime-app-development-support"></a>Windows çalışma zamanı uygulaması geliştirme desteği

- **Destek için değerde korumalı türler yapılar.**

   Şimdi, null olabilecek alanları kullanarak değer türlerini tanımlayabilirsiniz — Örneğin, `IBox<int>^` başlangıcı yerine sonundan **int**. Bu alanları bir değere sahip olması veya eşit olması gerektiğini anlamına gelir **nullptr**.

- **Daha zengin özel durum bilgileri.**

   C + +/ CX, uygulama ikili arabiriminde (ABI) yakalanması ve yayılmasını zengin özel durum bilgileri sağlayan yeni Windows hata modelini destekler Bu çağrı yığınları ve özel ileti dizelerini içerir.

- **Nesne:: ToString() sanal sunulmuştur.**

   Şimdi, kullanıcı tanımlı Windows Runtime başvuru türlerinde ToString geçersiz kılabilirsiniz.

- **Kaldırılmış API'ler için destek.**

   Ortak Windows çalışma zamanı API'leri artık kullanım dışı olarak ve belirli bir yapı uyarısı olarak özel bir ileti işaretlenebilir ve Geçiş Kılavuzu sağlayabilir.

- **Hata ayıklayıcı geliştirmeleri.**

   Yerel/JavaScript birlikte çalışma hata ayıklama, Windows çalışma zamanı özel durumu tanılama ve zaman uyumsuz kod (Windows çalışma zamanı ve PPL) hata ayıklama desteği.

> [!NOTE]
> C++ diline özgü özelliklere ve bu bölümde açıklanan geliştirmeleri ek olarak, Visual Studio'daki diğer geliştirmeler de daha iyi Windows çalışma zamanı uygulamaları yazmanıza yardımcı olabilir.

### <a name="diagnostics-enhancements"></a>Tanılama geliştirmeleri

- Hata ayıklayıcı geliştirmeleri. Zaman uyumsuz hata ayıklama ve yalnızca kendi kodum'hata ayıklama desteği.
- Kod çözümlemesi kategorileri. Artık, kod kusurlarını düzeltilmesine yardımcı olmak için kod Çözümleyicisi kategorilere ayrılmış çıktısını da görüntüleyebilirsiniz.
- XAML tanılama. UI yanıtlama hızı anda tanılayabilirsiniz ve pil kullanım sorunlarını, XAML içinde.
- Grafikler ve GPU hata ayıklama geliştirmeleri.
- Uzaktan yakalama ve kayıttan yürütme gerçek cihazlar üzerinde.
- Eşzamanlı C++ AMP ve CPU hata ayıklaması.
- Geliştirilmiş C++ AMP çalışma zamanı tanılaması.
- HLSL Compute gölgelendiricileri hata ayıklamayı izler.

### <a name="3-d-graphics-enhancements"></a>3-D grafik geliştirmeleri

- Görüntü içeriği ardışık düzeni desteği için ön çarpımlı alfa DDS biçimlendirin.
- Görüntü Düzenleyicisi, dahili olarak ön çarpımlı alfa kullanır ve böylece koyu haleler gibi işleme yapılarını önler.
- Görüntü ve Model düzenleyicileri Kullanıcı tanımlı filtre oluşturma artık Resim Düzenleyicisi ve Model Düzenleyicisi gölgelendirici Tasarımcısı'nda desteklenmektedir.

### <a name="ide-and-productivity"></a>IDE ve verimlilik

**Kod biçimlendirme deneyimi İyileştirildi**. C++ kodunuza daha fazla biçimlendirme ayarı uygulayabilirsiniz. Bu ayarları kullanarak, küme ayraçları ve anahtar sözcükler, girinti, boşluk ve satır kaydırma yeni satırdaki yerleşimini denetleyebilirsiniz. Deyimleri ve blokları tamamladığınızda ve bir dosyaya kod yapıştırdığınızda, kod otomatik olarak biçimlendirilir.

**Küme ayracı tamamlama.** C++ kodu şimdi otomatik olarak bu açılış karakterlerine karşılık gelen kapanış karakterlerini tamamlar:

- {(küme ayracı)
- [(köşeli parantez)
- ((parantez)
- ' (tek tırnak işareti)
- "(çift tırnak)

**Ek C++ otomatik tamamlama özellikleri.**

- Sınıf türleri için noktalı virgül ekler.
- Ham dize değişmez değerleri için parantezleri tamamlar.
- Çok satırlı açıklamaları tamamlar (/\* \*/)

**Tüm başvuruları Bul** artık otomatik olarak çözer ve metin eşleşmelerinin listesini görüntüledikten sonra başvuruları arka planda filtreler.

**Bağlam tabanlı üye listesini filtreleme.** Erişilemeyen üyeler IntelliSense üye listesinde filtrelenir. Örneğin, türü uygulayan kod değiştirmediğiniz sürece özel üyeler üye listesinde görüntülenmez. Üye listesi açıkken, basabilirsiniz **Ctrl**+**J** bir filtre düzeyini kaldırmak için (yalnızca geçerli üye listesi penceresi için geçerlidir). Basabilirsiniz **Ctrl**+**J** yeniden metin filtresini kaldırmak ve tüm üyeleri göstermek için.

**Parametre Yardımı kaydırma.** Artık yalnızca rasgele bir imza gösterip bunu geçerli bağlam temelinde güncellememek yerine, değişiklikler, aslında yazdığınız parametrelerin sayısını temel alarak parametre Yardım araç ipucunda görüntülenen işlev imzası. Parametre Yardımı da düzgün, iç içe işlevlerde görüntülendiğinde çalışmaz.

**İki durumlu başlık/kod dosyası.** Artık bir üstbilgi ve kod dosyası arasında bir komut kısayol menüsünü veya klavye kısayolunu kullanarak geçiş yapabilirsiniz.

**Yeniden boyutlandırılabilir C++ proje özellikleri penceresi**

**Otomatik olarak oluşturulmasını, olay işleyici kodunun C + +/ CX ve C + +/ CLI.**  Yazdığınızda kod bir olay işleyicisi ekleme C + +/ CX veya C + +/ CLI kod dosyasında Düzenleyici temsilci örneğini ve olay işleyici tanımını otomatik olarak oluşturabilirsiniz. Olay işleyici kodu otomatik olarak oluşturulan bir araç ipucu penceresi görünür.

**DPI tanıma geliştirme.** Uygulama bildirim dosyalarının DPI tanıma ayarı artık "her izleyici yüksek DPI tanıma" ayarını destekler.

**Daha hızlı yapılandırma geçişi.** Büyük uygulamalar için yapılandırmaları değiştirmek — özellikle sonraki işlemleri değiştirmek — çok daha hızlı bir şekilde yürütün.

**Yapı zamanı verimliliği.** Çok sayıda en iyi duruma getirme ve çok çekirdekli kullanım yapıların özellikle büyük projeler için daha hızlı olun. C++ uygulamaları için C++ Winmd'ye başvuran artımlı derlemeler çok daha hızlıdır.

## <a name="whats-new-for-c-in-visual-studio-2012"></a>Visual Studio 2012'de C++ için Yenilikler

### <a name="improved-c11-standards-support"></a>Geliştirilmiş C ++ 11 standartları destekler

#### <a name="standard-template-library"></a>Standart Şablon Kitaplığı

- Yeni STL üst bilgileri için destek: \<atomik >, \<chrono >, \<condition_variable >, \<filesystem >, \<gelecekteki >, \<mutex >, \<oranı >, ve \< iş parçacığı >.
- Bellek kaynağı kullanımı en iyi duruma getirmek için artık daha küçük kapsayıcılardır. İçinde x86 modu varsayılan ayarlarla, örneğin, sürüm `std::vector` 16 bayt Visual Studio 2010'dan Visual Studio 2012'de 12 bayt küçültülebilir ve `std::map` Visual Studio'da 16 bayt'dan Visual Studio 2012'de 2010 için 8 bayt küçültülebilir.
- İzin verilen ancak C ++ 11 standart tarafından gerekli değil, SCARY yineleyiciler uygulanmıştır.

#### <a name="other-c11-enhancements"></a>Diğer C ++ 11 geliştirmeleri

- Aralık tabanlı for döngüleri. Diziler, STL kapsayıcıları ve Windows çalışma zamanı koleksiyonları formunda çalışma daha güçlü döngüler yazabilirsiniz (için aralığı-bildirimi: ifade). Bu çekirdek dil desteğinin bir parçasıdır.
- Boş lambda introducer [] ile başlayın ve yerel değişken yakalayan kod bloklarını olan durum bilgisiz lambdalar artık işlev işaretçilerine C ++ 11 standart tarafından gerekli olarak örtük olarak dönüştürülebilir.
- Kapsamlı numaralandırmalar destekler. C++ sabit listesi sınıfı enum anahtarının artık desteklenmektedir. Aşağıdaki kod bu enum anahtarı önceki enum davranış farkı gösterir.

   ```cpp
  enum class Element { Hydrogen, Helium, Lithium, Beryllium };
  void func1(Element e);
  func1(Hydrogen); // error C2065: 'Hydrogen' : undeclared identifier
  func1(Element::Helium); // OK
   ```

### <a name="windows-runtime-app-development-support"></a>Windows çalışma zamanı uygulaması geliştirme desteği

- **Yerel XAML tabanlı UI modeli**. Windows çalışma zamanı uygulamaları için yeni yerel XAML tabanlı UI modeli kullanabilirsiniz.
- **Visual C++ bileşen uzantıları**. Bu uzantılar, Windows çalışma zamanı uygulamalarını gerekli bir parçası olan Windows çalışma zamanı nesnelerinin tüketimini basitleştirin. Daha fazla bilgi için [C++ kullanan Windows Runtime için yol haritası uygulamaları](../windows/universal-windows-apps-cpp.md) ve [Visual C++ Dil Başvurusu (C + +/ CX)](../cppcx/visual-c-language-reference-c-cx.md)
- **DirectX oyunları**. Windows çalışma zamanı uygulamaları için yeni destek DirectX kullanarak etkileyici oyunlar geliştirme yapabilirsiniz.
- **XAML/DirectX Interop**. Artık hem XAML hem de DirectX kullanan Windows çalışma zamanı uygulamaları verimli bir şekilde çalışmak.
- **Windows çalışma zamanı DLL bileşeni geliştirme**. Bileşen DLL geliştirme, Genişletilebilir Windows çalışma zamanı ortamı sağlar.

### <a name="compiler-and-linker"></a>Derleyici ve bağlayıcı

- **Otomatik vektör hale getirici**. Derleyici kod döngüleri analiz eder ve yayar, mümkün olduğunda vektör kullanma yönergeleri için kaydeder ve tüm modern işlemciye mevcut olan yönergeler. Bu, döngüleri, daha hızlı çalışmasını sağlar. (İşlemci yönergeleri Akış SIMD uzantıları için SSE bilinir). Etkinleştirmek veya otomatik olarak uygulandığından, bu en iyi duruma getirme istek gerekmez.
- **Otomatik paralel hale getirici**. Derleyici, kodunuzda döngüler çözümleyebilir ve birden çok çekirdek veya işlemci hesaplamaları yayılan yönergeleri yayma. Bu, daha hızlı çalışmasını döngüler yapabilirsiniz. Varsayılan olarak etkin olmadığından bu en iyi duruma getirme istemeniz gerekir. Eklenecek yardımcı çoğu durumda, bir `#pragma loop(hint_parallel(N))` kodunuzda hemen istediğiniz paralel döngüler önce.
- Otomatik paralel hale getirici ve otomatik vektör hale getirici birlikte hesaplamalar birden çok çekirdek arasında yayılır ve kodu her çekirdek kullanır, vektör kayıt çalışabilir.

### <a name="new-in-visual-studio-2012-update-1"></a>Yeni Visual Studio 2012 güncelleştirme 1

C++ kodunuzu derlerken Windows XP hedefleyin.
Visual C++ derleyicisi ve kitaplıklarında hedef Windows XP ve Windows Server 2003 için kullanabilirsiniz.

#### <a name="parallel-programming-support"></a>Paralel Programlama Desteği

##### <a name="c-accelerated-massive-parallelism-amp"></a>C++ hızlandırılmış yoğun paralellik (AMP)

C++ AMP ayrı ekran kartı GPU'da normalde mevcut olan veri-paralel donanımlardan yararlanarak C++ kod yürütülmesini hızlandırır. C++ AMP programlama modeli çok boyutlu diziler, dizin oluşturma, bellek aktarımı, döşeme ve bir matematiksel işlev kitaplığını içerir. C++ AMP dil uzantılarını ve derleyici kısıtlamaları'ı kullanarak nasıl verilerin CPU'dan GPU'ya ve geri taşındığını kontrol edebilirsiniz.

**Hata ayıklama.** Hata ayıklama deneyimini GPU hedeflemek için C++ AMP kullanan uygulamalar için yalnızca diğer C++ uygulamaları için hata ayıklama gibi ' dir. Bu, daha önce bahsedilen eklemeleri hata ayıklama yeni paralel içerir.

**Profil oluşturma.** Var. Şimdi C++ AMP ve diğer Direct3D tabanlı programlama modellerine göre GPU etkinliği için profil oluşturma desteği.

#### <a name="general-parallel-programming-enhancements"></a>Genel Paralel Programlama geliştirmeleri

Çok çekirdekli ve çok çekirdekli mimarileri için taşıma donanımlar sayesinde geliştiricilerin tek çekirdek saati hızlarını sürekli artan artık güvenebilirsiniz. Eşzamanlılık Çalışma zamanı desteği programlama paralel, geliştiricilerin bu yeni mimarileri yararlanmak sağlar.
Visual Studio 2010'da, paralel desenler kitaplığı gibi güçlü C++ paralelleştirme kitaplıkları sunulan, karmaşık veri akışı ardışık düzenleri ifade tarafından eşzamanlılık yararlanmak için özelliklerle birlikte. Visual Studio 2012'de, bu kitaplıkları, geliştiricilerin çoğu ihtiyaç için paralel desenleri daha iyi performans, daha fazla denetim ve daha zengin destek sağlamak için genişletilmiştir. Teklif kapsamını artık içerir:

- Faaliyetler ve devamlılıklar destekleyen bir zengin görev-tabanlı programlama modeli.
- Paralel algoritmalar çatal birleştirme paralellik (parallel_for, benzeşim, parallel_for_each, parallel_sort, parallel_reduce, parallel_transform parallel_for) destekler.
- Eşzamanlılık açısından güvenli kapsayıcılar, iş parçacığı açısından güvenli sürümleri std priority_queue, kuyruk, vektör ve harita gibi veri yapıları sağlayın.
- Zaman uyumsuz aracılar geliştiriciler doğal olarak eş zamanlı birimlerine ayırmak veri akışı ardışık düzenleri ifade etmek için kullanabileceğiniz kitaplığı.
- Bu listedeki desenleri kesintisiz oluşumunu kolaylaştırmak için bir özelleştirilebilir Zamanlayıcı ve Kaynak Yöneticisi.

##### <a name="general-parallel-debugging-enhancements"></a>Genel Paralel hata ayıklama geliştirmeleri

Ek olarak **Paralel Görevler** penceresi ve **Paralel Yığınlar** penceresi, Visual Studio 2012 sunar, yeni bir **paralel izleme** penceresi değerlerini inceleyebilirsiniz. böylece bir ifadesi tüm iş parçacıklarını yönlendirebilir ve işler ve sıralama ve filtreleme sonucuna gerçekleştirin. Kendi görselleştiriciler penceresini genişletmek için de kullanabilirsiniz ve tüm araç pencereleri arasında yeni çok işlemli destekten yararlanabilirsiniz.

### <a name="ide"></a>IDE

**Visual Studio şablonları destekler.** Artık Visual Studio şablonları teknolojisine Yazar C++ proje ve öğe şablonları kullanabilirsiniz.

**Zaman uyumsuz çözüm yükü.** Projeleri artık yüklenir zaman uyumsuz olarak — çözümünün temel parçalarına ilk; böylece daha hızlı bir şekilde çalışmaya başlayabilir.

**Uzaktan hata ayıklama için otomatik dağıtım.** Visual C++'da uzaktan hata ayıklama dosyalarının dağıtım basitleştirilmiştir. **Dağıt** proje bağlam menüsü seçeneği otomatik olarak hata ayıklama yapılandırma özelliklerinde belirtilen dosyaları uzak bilgisayara kopyalar. Dosyaları uzak bilgisayara el ile kopyalama artık gerekli değildir.

**C + +/ CLI IntelliSense.** C + +/ CLI artık tam IntelliSense desteği vardır. IntelliSense özellikleri gibi hızlı bilgi, parametre Yardımı, listesi üyeleri ve otomatik tamamlama için C + çalıştığını +/ CLI. Ayrıca, bu belgede listelenen diğer IntelliSense ve IDE geliştirmeleri de C + için çözüm +/ CLI.

**Daha zengin IntelliSense araç ipuçları.** C++ IntelliSense hızlı bilgi araç ipuçları, daha zengin XML belgeleri yorumları artık stil bilgilerini gösterir. Bir Kitaplığı'ndan bir API kullanıyorsanız — Örneğin, C++ AMP — XML belge açıklamaları olan ve IntelliSense araç ipucu bildirimi daha fazla bilgi gösterir. Ayrıca, kodunuzu XML belge açıklamaları varsa, IntelliSense araç ipuçları daha zengin bilgi gösterir.

**C++ kodu oluşturur.** İskelet kod if-else, döngü ve üyeleri listeleme aşağı açılan listesinde diğer temel kod yapıları için anahtar için kullanılabilir. Kod parçasını kodunuza ekleyin ve ardından gerekli mantık doldurmak için listeden seçin. Kendi özel parça kullanmak için Kod Düzenleyicisi'nde de oluşturabilirsiniz.

**Liste üyelerini geliştirmeleri.** **Üyeleri Listele** açılır listede otomatik olarak kod düzenleyicisine kod yazdığınız gibi görünür. Sonuçları filtrelenir ve böylece yalnızca ilgili üyeleri yazdığınız sırada görüntülenir. Üye listesi tarafından kullanılan filtreleme mantığı türünü denetleyebilirsiniz — içinde **seçenekleri** iletişim kutusunun altında **metin düzenleyici** > **C/C++**  >  **Gelişmiş**.

**Semantik renklendirme.** Artık türler, numaralandırmalar, makroları ve diğer C++ belirteçleri renklendirme, varsayılan olarak sahiptir.

**Başvuru vurgulama.** Artık bir simge seçerek geçerli dosyadaki simgenin tüm örnekleri vurgular. Tuşuna **Ctrl**+**Shift**+**yukarı ok** veya **Ctrl**+**kaydırma**  + **Aşağı ok** vurgulanan başvurulara arasında taşımak için. Bu özellik, kapatabilirsiniz **seçenekleri** iletişim kutusunun **metin düzenleyici** > **C/C++** > **Gelişmiş**.

### <a name="application-lifecycle-management-tools"></a>Uygulama yaşam döngüsü Yönetim Araçları

#### <a name="static-code-analysis"></a>Statik kod analizi

C++ için statik analizi daha zengin hata bağlam bilgileri, daha fazla çözümleme kurallarını sağlamak için güncelleştirildi ve daha iyi analiz sonuçları. Yeni Kod Analizi penceresi iletileri anahtar sözcüğü, proje ve önem derecesine göre filtreleyebilirsiniz. Bir ileti penceresinde seçtiğinizde, ileti tetiklendiği kod satırında Kod Düzenleyicisi'nde vurgulanır. Belirli C++ uyarıları, uyarı müşteri adayları yürütme yolunu gösteren kaynak satırları ileti listeler. karar noktaları ve belirli bir yol alma nedeni vurgulanır.
Kod Analizi çoğu Visual Studio 2012 sürümlerinde bulunur. Tüm kurallar, Professional, Premium ve Ultimate sürümleri dahil edilir. Windows 8 ve Windows Phone için Express sürümlerinde, yalnızca en kritik uyarılar dahil edilir. Kod Analizi, Web için Express sürümünde bulunmamaktadır.
Bazı bir kod analizi geliştirmeler şunlardır:

- Yeni eşzamanlılık uyarıları, çok iş parçacıklı C/C++ programlarında doğru kilitleme uzmanlık kullanarak sağlayarak eşzamanlılık hataları önlemenize yardımcı. Çözümleyici olası yarış durumlarını, kilit sırası inversions, çağıran/çağrılan kilitleme sözleşmenin ihlali, eşleşmeyen eşitleme işlemleri ve diğer eşzamanlılık hataları algılar.
- Kural kümeleri kullanarak Analiz çalışmaları kod uygulamak istediğiniz C++ kuralları belirtebilirsiniz.
- İçinde **Kod Analizi** penceresi, kaynak koda seçili uyarı bastırılır bir pragma ekleyebilirsiniz.
- Bir işlev, BT'nin bunları ve garantiler kılar varsayımların parametrelerinin nasıl kullandığını tanımlamak için yeni Microsoft kaynak kodu ek açıklama dili (SAL) sürümünü kullanarak statik kod analizi tamlığını ve doğruluğunu artırabilirsiniz tamamlandığında yapar.
- C++ projeleri için 64 bit desteği.

#### <a name="updated-unit-test-framework"></a>Güncelleştirilmiş birim testi çerçevesi

Yeni C++ birim testi çerçevesi Visual Studio'da C++ birim testleri yazmak için kullanın. Yeni bir birim test projesi var olan C++ çözümünüze yeni proje iletişim kutusunda C++ Birim Test projesi şablonu Visual C++ kategori altında bularak ekleyin. Birim testleriniz içinde oluşturulan TEST_METHOD kod saplama Unittest1.cpp dosyasına yazmayı başlatır. Test kodu yazıldığında çözümü oluşturun. Testleri çalıştırmak istediğiniz açtığınızda bir **Birim Test Gezgini** penceresini seçerek **görünümü** > **diğer Windows** > **birim testi Explorer**ve ardından istediğiniz test çalışması için kısayol menüsünden seçin **seçilen test çalıştırması**. Bittiğinde test çalıştırdıktan sonra test sonuçları ve ek yığın izleme bilgileri aynı penceresinde görüntüleyebilirsiniz.

#### <a name="architecture-dependency-graphs"></a>Mimari bağımlılık grafikleri

Kodunuzu daha iyi anlamak için artık ikili, ad alanı, sınıf için bağımlılık grafikleri oluşturmak ve bir çözümde dosyaları içerir. Menü çubuğunda, **mimarisi** > **bağımlılık grafiği Oluştur**, ardından **çözüm** veya **dahil etme dosyası**bir bağımlılık grafiği oluşturmak için. Grafik oluşturma tamamlandığında, her düğümünü genişleterek keşfedin, düğümler arasında taşıyarak bağımlılık ilişkilerini öğrenin ve seçerek kaynak koda göz atma **içeriğini görüntüle** bir düğümü için kısayol menüsünde. Kısayol menüsünde dahil etme dosyaları için bağımlılık grafiği oluşturmak için bir \*.cpp kaynak kodu dosyası veya \*.h başlık dosyası, seçin **oluşturmak grafiği, dosyaları içerir**.

#### <a name="architecture-explorer"></a>Mimari Gezgini

Kullanarak **Mimari Gezgini**, C++ çözüm, proje veya dosya varlıklar keşfedebilirsiniz. Menü çubuğunda, **mimarisi** > **Windows** > **Mimari Gezgini**. Bir düğüm, ilgilendiğiniz, örneğin, seçtiğiniz **sınıf görünümü**. Bu durumda, araç penceresinin sağ tarafındaki ad alanlarının bir listesini genişletilir. Bir ad seçerseniz, yeni bir sütun bu ad alanındaki sınıflar, yapılar ve numaralandırmalar listesini gösterir. Bu varlıklar keşfedin veya sütuna en solda başka bir sorgu başlatmak için dönün devam edebilirsiniz. Bkz: **Mimari Gezgini ile kod bulma**.

#### <a name="code-coverage"></a>Kod Kapsamı

Kod Kapsamı aracı ikili çalışma zamanında dinamik olarak güncelleştirildi. Bu yapılandırma ek yükü azaltır ve daha iyi performans sağlar. C++ uygulamaları için birim testleri kod kapsamı verileri de toplayabilir. C++ birim testleri oluştururken kullanabileceğiniz **Birim Test Gezgini** çözümünüzdeki testleri bulmak için. Birim testleri çalıştırmak ve kod kapsamı verilerini kendileri için içinde toplamak için **Birim Test Gezgini**, seçin **kod kapsamı analizi**. Kod kapsamı sonuçları inceleyebilirsiniz **kod kapsamı sonuçlarını** penceresi; menü çubuğunda, **Test** > **Windows**  >   **Kod kapsamı sonuçlarını**.

## <a name="whats-new-for-c-in-visual-studio-2010"></a>C++, Visual Studio 2010'daki yenilikler

### <a name="c-compiler-and-linker"></a>C++ Derleyici ve bağlayıcı

**Auto anahtar sözcüğü.** **Otomatik** anahtar sözcüğü yeni bir amacı vardır. Varsayılan anlamını kullanın **otomatik** türü bir değişken bildirmek için anahtar sözcüğü değişkenin bildirimi başlatma ifadesinden atanan. `/Zc:auto` Derleyici seçeneği, yeni veya önceki anlamını çağırır **otomatik** anahtar sözcüğü.

**decltype türü tanımlayıcısı.** **Decltype** tür belirticisi belirtilen ifade türünü döndürür. Kullanım **decltype** tür tanımlayıcısı ile birlikte **otomatik** derleyici için yalnızca bilinen ya da karmaşık bir türü bildirmek için anahtar sözcüğü. Örneğin, dönüş türü şablon bağımsız değişkenlerinin türlerine bağlıdır bir şablon işlevi bildirmek için birlikte kullanın. Veya başka bir işlevi çağırır ve sonra çağrılan işlevin dönüş türü döndüren bir şablon işlevi bildirmek.

**Lambda Expressions.** Lambda işlevleri bir işlev gövdesinin ancak ad var. Lambda işlevi, en iyi özelliklerini işlev işaretçilerini ve işlev nesnelerini birleştirin. Bir lambda işlevi tek başına veya birlikte bir işlev nesnesi yerine bir şablon işlevi parametre olarak kullanın **otomatik** türü bir değişken bildirmek için anahtar sözcüğü bir lambdadır.

**Rvalue başvuru.** Rvalue başvuru bildirimcisi (& &) bir rvalue başvuru bildirir. Kullandığınız bir rvalue başvurusu sağlar, semantiği ve daha verimli Oluşturucular, işlevleri ve şablon yazmak için kusursuz iletme taşıyın.

**static_assert Declaration.** A **static_assert** bildirimi derleme zamanında çalışma zamanında test diğer onaylama mekanizmaları aksine bir yazılım onayını sınar. Onaylama başarısız olursa, derleme başarısız olur ve belirtilen hata iletisi verilir.

**nullptr ve __nullptr anahtar sözcükler.** Visual C++ derleyicisi kullanmanıza olanak tanıyan **nullptr** yerel kod veya yönetilen kod ile anahtar sözcüğü. **Nullptr** anahtar sözcüğü bir nesne tanıtıcısı, iç işaretçi veya yerel bir işaretçi türü bir nesneye göstermiyor gösterir. Derleyici, Yorumlar **nullptr** olmasını kullandığınızda yönetilen kod `/clr` derleyici seçeneği ve kullandığınızda, yerel kod `/clr` seçeneği.
Microsoft'a özgü **__nullptr** anahtar sözcüğü sahip aynı anlamı **nullptr**, ancak yalnızca yerel kod için geçerlidir. Yerel C/C++ kod kullanarak derlerseniz `/clr` derleyici seçeneği, derleyicinin belirleyemiyor olmadığını **nullptr** anahtar sözcüğü, bir yerel veya yönetilen bir terim. Amacınız, derleyicinin Temizle hale getirmek için yönetilen terimi belirtmek için nullptr anahtar sözcüğü kullanın ve **__nullptr** yerel terimi belirtmek için.

**/ ZC: trigraphs derleyici seçeneği.** Varsayılan olarak, desteği trigrafları devre dışı. Kullanım `/Zc:trigraphs` trigrafları desteğini etkinleştirmek için derleyici seçeneği.
Bir trigraf iki ardışık soru benzersiz bir üçüncü karakter işareti (?) oluşur. Derleyici, bir trigraf karşılık gelen noktalama karakteri ile değiştirir. Örneğin, derleyici değiştirir?? # (sayı işareti) karakteri ile trigraf =. Trigrafları, bazı noktalama karakterleri içermeyen bir karakter kümesini kullandırır C kaynak dosyalarında kullanın.

**Yeni profil temelli iyileştirme seçeneği.** PogoSafeMode uygulamanızı en iyi duruma getirdiğinizde, güvenli mod veya hızlı mod kullanılıp kullanılmayacağını belirlemenizi sağlayan yeni bir profil temelli iyileştirme seçeneğidir. Güvenli mod iş parçacığı açısından güvenlidir ancak hızlı mod yavaştır. Hızlı mod varsayılan davranıştır.

**Yeni ortak dil çalışma zamanı (CLR) seçeneği using'ler.** Yeni bir seçenek için eklenen `/clr` (ortak dil çalışma zamanı derlemesi). Aynı kitaplıkların farklı sürümleri varsa, bir derleme hatası verilir. Yeni seçenek programınız belirtilen sürümü kullanabilmesi için varsayılan CLR kitaplıkları dışlamanıza olanak sağlar.

**Yeni pragma yönergesi detect_mismatch.** Pragma yönergesi detect_mismatch, bir etiketi, aynı ada sahip diğer etiketler dosyalarınızda karşılaştırılır yerleştirmenizi sağlar. Bağlayıcı, aynı adı için birden çok değer varsa bir hata verir.

**XOP yapı içleri FMA4 İç bilgileri ve LWP İç bilgileri.** Yeni İç işlevleri XOP yapı içleri eklenen Visual Studio 2010 SP1, yapı içleri FMA4 İç eklenen için Visual Studio 2010 SP1 ve yapı içleri LWP eklenen için Visual Studio 2010 SP1 işlemci teknolojileri için desteklemek için eklendi. __Cpuid, belirli bir bilgisayarda hangi işlemci teknolojileri desteklendiğini belirlemek üzere __cpuidex kullanın.

### <a name="visual-c-projects-and-the-build-system"></a>Visual C++ projeleri ve yapı sistemi

**MSBuild.** Visual C++ çözümler ve projeler artık VCBuild.exe değiştiren MSBuild.exe kullanarak oluşturulur. MSBuild ve diğer Visual Studio dilleri ve proje türleri tarafından kullanılan aynı esnek, Genişletilebilir, XML tabanlı yapı aracıdır. Bu değişiklik nedeniyle Visual C++ proje dosyaları artık bir XML dosyası biçimini kullanmak ve .vcxproj dosya adı uzantısına sahip. Visual Studio'nun önceki sürümlerinde Visual C++ proje dosyalarından otomatik olarak yeni bir dosya biçimine dönüştürülür.

**VC ++ dizinleri.** VC ++ dizinleri ayarlama artık iki yerde bulunur. VC ++ dizinleri her proje değerlerini ayarlamak için proje özellik sayfalarını kullanın. Kullanım **özellik Yöneticisi** ve genel ayarlamak için bir özellik sayfası başına yapılandırma değerleri için VC ++ dizinleri.

**Proje ve proje bağımlılıkları.** Önceki sürümlerde, projeler arasında tanımlanan bağımlılıklar çözüm dosyasında saklanır. Bu çözümler yeni proje dosya biçimine dönüştürülür, bağımlılıkları, projeden projeye başvurular dönüştürülür. Çözüm bağımlılıklarını ve projeden projeye başvurular farklı olduğundan bu değişiklik, uygulamaları etkileyebilir.

**Makrolar ve ortam değişkenleri.** Yeni _ıterator_debug_level makrosu yineleyicileri için hata ayıklama desteği çağırır. Eski _SECURE_SCL ve _HAS_ITERATOR_DEBUGGING makroları yerine bu makroyu kullanın.

### <a name="visual-c-libraries"></a>Visual C++ Kitaplıkları

**Eşzamanlılık Çalışma zamanı kitaplıkları.** Eşzamanlılık Çalışma zamanı framework uygulamaları ve aynı anda çalışan bileşenleri destekler ve eş zamanlı uygulamalarında Visual C++ programlama çerçevesidir. Uygulama eşzamanlı programlamayı desteklemek için paralel desenler kitaplığı (PPL) genel amaçlı kapsayıcılar ve algoritmaları hassas paralellik gerçekleştirilmesi için sağlar. Zaman uyumsuz aracılar kitaplığı, bir aktör tabanlı programlama modeli ve ileti geçirme arabirimler için parçalı veri akışı ve ardışık düzen oluşturma görevleri sağlar.

**Standart C++ Kitaplığı.** Aşağıdaki listede birçok standart C++ Kitaplığı'na yapılan değişiklikleri açıklar.

- Yeni bir rvalue başvurusu C++ dil özelliğidir, taşıma semantiği ve kusursuz iletme birçok işlev için standart Şablon Kitaplığı'nda uygulamak için kullanılır. Taşıma semantiği ve kusursuz iletme tahsis edin ya da değişken ya da parametrelerinin atama işlemlerinin performansını büyük ölçüde geliştirebilirsiniz.
- Rvalue başvuruları yeni uygulamak için de kullanılır `unique_ptr` daha güvenli bir akıllı işaretçi türü olan bir sınıf daha `auto_ptr` sınıfı. `unique_ptr` Sınıf güvenliği etkilemeden katı sahipliği semantiğini uygular, ancak kopyalanabilir, taşınabilir olduğundan ve de rvalue başvuruları farkında kapsayıcılar ile çalışır. `auto_ptr` Sınıfı kullanım dışı bırakılmıştır.
- Örneğin, on beş yeni işlevleri `find_if_not`, `copy_if`, ve `is_sorted`, eklenmiş \<algoritma > Üstbilgi.
- İçinde \<bellek > üst bilgi, yeni make_shared işlevi olan bir nesne için paylaşılan bir işaretçi nesnesi oluşturulduğunda, aynı anda yapmak için kullanışlı, sağlam ve verimli bir şekilde.
- Tarafından desteklenen tek bağlı listeler \<forward_list > Üstbilgi.
- Yeni `cbegin`, `cend`, `crbegin`, ve `crend` üye işlevleri sağlayan bir `const_iterator` , taşır ileriye veya geriye doğru üzerinden bir kapsayıcının.
- \<System_error > Üstbilgi ve ilgili şablonları alt düzey sistem hatalarının işlenmesini destekler. Üyeleri `exception_ptr` sınıfı, özel durumları iş parçacıkları arasında taşıma için kullanılabilir.
- \<Codecvt > üst bilgi, diğer kodlamaları için çeşitli Kodlamalar Unicode karakter dönüştürme destekler.
- \<Ayırıcılar > Üstbilgi ayırma ve serbest bellek blokları düğümünü tabanlı kapsayıcılar için yardımcı çeşitli şablonları tanımlar.
- Çok sayıda güncelleştirme vardır \<rastgele > Üstbilgi.

### <a name="microsoft-foundation-class-mfc-library"></a>Microsoft Foundation Class (MFC) kitaplığı

**Windows 7 özellikleri.** MFC, örneğin, Şerit kullanıcı arabirimini (UI), görev, bağlantı listeleri, sekmeli küçük, küçük resim önizlemeleri, ilerleme çubuğu, simge katmanını ve arama dizini oluşturma çok sayıda Windows 7 özellikleri destekler. MFC otomatik olarak çok sayıda Windows 7 özellikleri desteklediğinden, mevcut uygulamanızı değiştirmek sahip. İçinde yeni uygulamalar diğer özellikleri desteklemek için kullanmak istediğiniz işlevi belirtmek için MFC Uygulama Sihirbazı'nı kullanın.

**Çok noktalı dokunma tanıma.** MFC, bir çok noktalı dokunma kullanıcı arabirimine sahip uygulamalar gibi Microsoft Surface işletim sistemi için yazılan uygulamaları destekler. Çok noktalı dokunma uygulama Windows dokunma iletileri ve dokunma iletileri birleşimleridir hareket iletileri işleyebilir. Yalnızca uygulamanız için dokunma kaydedin ve hareket olayları ve işletim sistemi çok noktalı dokunma olayları, olay işleyicileri için yönlendirir.

**Yüksek DPI tanıma.** Varsayılan olarak, MFC uygulamaları artık yüksek-DPI kullanan uygulamalardır. Yüksek DPI (yüksek nokta / inç) kullanan bir uygulama ise, işletim sistemi, windows, metin ve diğer kullanıcı Arabirimi öğeleri için geçerli ekran çözünürlüğü ölçeklendirebilirsiniz. Bu ölçeklendirilmiş bir görüntü doğru düzenlendiği ve değil kırpılarak olma olasılığı daha yüksektir anlamına gelir veya pixelated.

**Yeniden başlatma Yöneticisi.** Yeniden başlatma Yöneticisi'ni otomatik olarak belgeleri kaydeder ve beklenmedik bir şekilde kapatılır veya yeniden başlatır, uygulamanızı yeniden başlatır. Örneğin, bir otomatik güncelleştirme tarafından kapatıldıktan sonra uygulamanızı başlatmak için yeniden başlatma Yöneticisi'ni kullanabilirsiniz. Uygulamanızı yeniden başlatma Yöneticisi'ni kullanacak şekilde yapılandırma hakkında daha fazla bilgi için bkz. **nasıl yapılır: Yeniden başlatma Yöneticisi desteği ekleme**.

**CTaskDialog.** `CTaskDialog` Sınıfı yerine standart kullanılabilir `AfxMessageBox` ileti kutusu. `CTaskDialog` Sınıfı standart bir ileti kutusu sağladığından daha fazla bilgi toplar ve görüntüler.

#### <a name="safeint-library"></a>SafeInt Kitaplığı

Yeni SafeInt Kitaplığı, tamsayı taşma için bu hesabın güvenli aritmetik işlemleri gerçekleştirir. Bu kitaplık, farklı tamsayı türleri de karşılaştırır.

#### <a name="new-active-template-library-atl-macros"></a>Yeni Etkin Şablon kitaplığı (ATL) makroları

Yeni makroları PROP_ENTRY_TYPE ve PROP_ENTRY_TYPE_EX işlevlerini genişletmek için ATL için eklenmiştir. PROP_ENTRY_INTERFACE ve PROP_ENTRY_INTERFACE_EX geçerli CLSID listesini eklemenize olanak sağlar. PROP_ENTRY_INTERFACE_CALLBACK ve PROP_ENTRY_INTERFACE_CALLBACK_EX CLSID geçerli olup olmadığını belirlemek için bir geri çağırma işlevini belirtmenizi sağlar.

#### <a name="analyze-warnings"></a>/ analyze uyarıları

Çoğu `/analyze` (Kurumsal kod çözümleme) uyarıları C çalışma zamanı (CRT), MFC ve ATL kitaplıklarından kaldırıldı.

#### <a name="animation-and-d2d-support"></a>Animasyon ve D2D desteği

MFC, animasyon ve Direct2D grafikler artık desteklemektedir. MFC Kitaplığı, birkaç yeni MFC sınıfları ve bu işlevselliği desteklemek için işlevleri vardır. D2D nesnesi ve bir animasyon nesne bir projeye ekleme göstermek için iki yeni izlenecek yollar vardır. Bu izlenecek olan **izlenecek yol: Bir MFC projesine D2D nesnesi ekleme** ve **izlenecek yol: Bir MFC projesine animasyon ekleme**.

### <a name="ide"></a>IDE

**Geliştirilmiş IntelliSense.** Visual c++ IntelliSense, tamamen daha hızlı, daha doğru ve daha büyük projelerle baş etmek mümkün olacak şekilde tasarlanmıştır. Bu geliştirme elde etmek için IDE nasıl bir geliştirici görünümleri ve kaynak kodunu değiştirir ve nasıl bir çözümü oluşturmak için kaynak kodu ve proje ayarları IDE kullandığı arasında bir ayrım yapar.
Bu görevler ayrımı nedeniyle özellikleri gibi gözatma **sınıf görünümü** ve yeni **gitmek için** iletişim kutusu işlenir yeni bir SQL Server tabanlı bir sistem tarafından Masaüstü Veritabanı (.sdf) dosyası eski derleme Gözat (.ncb) dosya değiştirir. Hızlı bilgi, otomatik tamamlama ve parametre Yardımı gibi IntelliSense özellikleri yalnızca gerekli olduğunda çeviri birimleri ayrıştırılamıyor. Gibi yeni karma Özellikler **çağrı hiyerarşisi** penceresini göz atma ve IntelliSense özelliklerini kullanın.
IntelliSense yalnızca şu anda ihtiyaç duyduğunuz bilgileri işlediğinden, daha hızlı yanıt veren bir ıde'dir. Bilgi daha güncel olduğundan, ayrıca, IDE Görünüm ve daha doğru. Son olarak, IDE altyapı, daha iyi düzenlenmiş, daha yetenekli ve daha ölçeklenebilir olduğundan, daha büyük projeleri işleyebilir.

**Geliştirilmiş IntelliSense hataları.** IDE daha iyi IntelliSense kaybına neden olabilecek hataları algılar ve bunları altında kırmızı dalgalı alt çizgiler görüntüler. Buna ek olarak, IDE IntelliSense hataları için raporları **Hata Listesi penceresi**. Soruna neden olan kodunu görüntülemek için hataya çift tıklayın **Hata Listesi penceresi**.

**#include Otomatik Tamamlama özelliği.** Otomatik Tamamlama için IDE'yi destekler `#include` anahtar sözcüğü. Yazdığınızda `#include`, IDE bir açılan liste kutusunda geçerli bir üst bilgi dosyaları oluşturur. Bir dosya adı yazarak devam ederseniz, IDE üzerinde giriş listeye filtre uygular. Herhangi bir noktada dahil etmek istediğiniz dosyanın listeden seçim yapabilirsiniz. Bu tam dosya adını bilmeden dosyaları kolayca eklemenize olanak sağlar.

**Gidin.** **Gitmek için** tüm simgeleri ve belirtilen bir dizeyle Eşleştir projenizdeki dosyaları için arama iletişim kutusu sağlar. Ek karakterler, arama dizesinde yazarken arama sonuçlarını hemen düzeltilir. **Sonuçları** geri bildirim alan bulunan öğe sayısını belirten ve arama sınırlamak karar vermenize yardımcı olur. **Türü/kapsam**, **konumu**, ve **Önizleme** geri bildirim alanları benzer adlara sahip öğeleri belirsizliğinin ortadan kaldırılmasını yardımcı olur. Ayrıca, bu özellik, diğer programlama dillerini destekleyecek şekilde genişletebilirsiniz.

**Paralel hata ayıklama ve profil oluşturma.** Visual Studio hata ayıklayıcısını eşzamanlılık çalışma zamanı kullanan ve Paralel işleme uygulamalarını gidermenize yardımcı olur. Yeni eşzamanlılık Profil Oluşturucu aracı, uygulamanızın genel davranışını görselleştirmek için kullanabilirsiniz. Ayrıca, görevleri ve çağrı yığınlarıyla durumunu görselleştirmek için yeni araç pencerelerini kullanabilirsiniz.

**Şerit Tasarımcısı.** **Şerit Tasarımcısı** oluşturmak ve bir MFC değiştirmenize olanak tanıyan bir grafik düzenleyici Şerit kullanıcı arabirimini olduğu. Son Şerit UI'si bir XML tabanlı kaynak dosyası (ms .mfcribbon) tarafından temsil edilir. Var olan uygulamalar için geçerli bir Şerit UI'si geçici olarak birkaç satır kod ekleyerek ve ardından çağırma yakalayabilirsiniz **Şerit Tasarımcısı**. Şerit kaynak dosyası oluşturulduktan sonra el yazısı, Şerit kullanıcı arabirimini kod Şerit kaynağı yükleme birkaç deyim ile değiştirebilirsiniz.

**Çağrı hiyerarşisi.** **Çağrı hiyerarşisi** penceresinde belirli bir işlev tarafından çağrılan tüm işlevleri veya belirli bir işlevi çağırmayı tüm işlevlere gitmek olanak tanır.

### <a name="tools"></a>Araçlar

**MFC Sınıf Sihirbazı.** Visual C++ 2010 iyi regarded MFC Sınıf Sihirbazı Aracı'nı geri getirir. MFC Sınıf Sihirbazı, sınıflar, iletileri ve değişkenler el ile kaynak dosyaları kümesini değiştirmek zorunda kalmadan bir projeye eklemek için kullanışlı bir yoldur.

**ATL denetimi Sihirbazı.** ATL Denetim Sihirbazı'nı artık otomatik olarak doldurur `ProgID` alan. ATL denetimi yoksa bir `ProgID`, diğer araçlar ile çalışmayabilir. Denetimleri olmasını gerektiren bir aracı örneği bir `ProgID` olduğu **etkin denetim Ekle** iletişim kutusu. İletişim kutusu hakkında daha fazla bilgi için bkz. **ActiveX denetimi Ekle iletişim kutusu**.

### <a name="microsoft-macro-assembler-reference"></a>Microsoft Macro Assembler Başvurusu

Intel Gelişmiş vektör Uzantıları (AVX) yönergeleri dahil olan 256 bit multimedya işlenenler YMMWORD veri türünü destekler.

## <a name="whats-new-for-c-in-visual-studio-2008"></a>Visual Studio 2008'de C++ için Yenilikler

### <a name="visual-c-integrated-development-environment-ide"></a>Visual C++ tümleşik geliştirme ortamı (IDE)

- ATL, MFC ve Win32 uygulamaları artık oluşturulan iletişim kutuları, Windows Vista stil kılavuzları ile uyumlu. Visual Studio 2008'i kullanarak yeni bir proje oluşturduğunuzda, uygulamanıza eklediğiniz tüm iletişim kutularını, Windows Vista stil kılavuzuyla uyacaktır. Visual Studio'nun önceki bir sürümüyle oluşturulmuş bir projeyi yeniden derleyin, var olan herhangi bir iletişim kutusu, daha önce sahip oldukları aynı konum tutacaktır. İletişim kutuları uygulamanıza ekleme hakkında daha fazla bilgi için bkz. **iletişim kutusu Düzenleyicisi**.

- **ATL projesi** Sihirbazı artık tüm kullanıcılar için bileşenleri kaydetmek için bir seçenek vardır. Visual Studio 2008, COM bileşenleri ve tarafından oluşturulan tür kitaplıklarını başlayarak **ATL projesi** Sihirbazı işaretlemediyseniz kayıt defterinin HKEY_CURRENT_USER düğümünde kayıtlı **kaydı bileşeni tüm kullanıcılar için**.
- **ATL projesi** Sihirbazı artık sağlar öznitelikli ATL projeleri oluşturmak için bir seçenek. Visual Studio 2008'den itibaren **ATL projesi** Sihirbazı yeni bir proje öznitelikli durumunu değiştirmek için bir seçenek yok. Sihirbaz tüm yeni ATL projeleri artık, unattributed.
- Kayıt defterine yazma yönlendirilebilir. Windows Vista sunulmasıyla birlikte, yükseltilmiş modda çalıştırmak için bir program belirli kayıt defteri alanı yazılmasını gerektirir. Her zaman Visual Studio'nun yükseltilmiş modda çalıştırmak için uygun değil. Bağımsız kullanıcı yönlendirmesi kayıt defterinde HKEY_CLASSES_ROOT HKEY_CLASSES_ROOT gelen HKEY_CURRENT_USER için programlama herhangi bir değişiklik yapılmadan otomatik olarak yönlendirir.
- **Sınıf Tasarımcısı** artık yerel C++ kodu için destek sınırlıdır. Visual Studio'nun önceki sürümlerinde **Sınıf Tasarımcısı** yalnızca Visual C# ve Visual Basic ile çalıştım. C++ kullanıcılar artık kullanabilir **Sınıf Tasarımcısı**, ancak yalnızca salt okunur modda. Nasıl kullanılacağı hakkında daha fazla bilgi için **Sınıf Tasarımcısı** C++ ile bkz **sınıf tasarımcısında Visual C++ kodu ile çalışma**.
- Proje Sihirbazı artık bir C++ SQL sunucusu projesi oluşturma seçeneğiniz vardır. Visual Studio 2008'den itibaren Yeni Proje Sihirbazı'nı bir SQL Server C++ projesi oluşturmak için bir seçenek yok. Visual Studio'nun önceki bir sürümü kullanılarak oluşturulmuş SQL Server projeleri hala derleyin ve düzgün çalışır.

### <a name="visual-c-libraries"></a>Visual C++ Kitaplıkları

#### <a name="general"></a>Genel

- Uygulamalar için Visual C++ kitaplıklarını belirli sürümlerine bağlı olabilir. Bazen bir uygulama için Visual C++ kitaplıklarının sürümünden sonra yapılan güncelleştirmeler bağlıdır. Bu durumda, uygulama kitaplıkları önceki sürümlerinde bulunan bir bilgisayarda çalışan beklenmeyen davranışlara neden olabilir. Böylece kitaplıkları'nın önceki bir sürümü olan bir bilgisayarda çalışmaz kitaplıkları belirli bir sürümünü uygulama artık bağlayabilirsiniz.

#### <a name="stlclr-library"></a>STL/CLR Kitaplığı

- Visual C++ artık STL/CLR kitaplığı içerir. STL/CLR kitaplığı bir paketleme, standart Şablon kitaplığı (STL), standart C++ Kitaplığı, C++ ve .NET Framework ortak dil çalışma zamanı (CLR) ile kullanım için bir alt kümesi olan. STL/CLR ile artık tüm kapsayıcıları, Yineleyiciler ve stl algoritmaları yönetilen bir ortamda kullanabilirsiniz.

#### <a name="mfc-library"></a>MFC Kitaplığı

- Windows Vista ortak denetimleri destekler. 150'den fazla yöntemleri 18 sınıflarında yeni veya var olan Windows Vista'da özelliklerini desteklemek üzere veya geçerli MFC sınıfları işlevleri geliştirmek için eklendi.
- Yeni `CNetAddressCtrl` sınıfı, giriş ve IPv4 ve IPv6 adresleri veya DNS adları doğrulama olanak tanır.
- Yeni `CPagerCtrl` sınıfı Windows sayfalama denetimi kullanılmasını basitleştirir.
- Yeni `CSplitButton` sınıfı bir varsayılan veya isteğe bağlı bir eylem seçmek için Windows splitbutton denetim kullanımını kolaylaştırır.

#### <a name="c-support-library"></a>C++ Destek Kitaplığı

- C++ sıralama kitaplığı tanıtır. Sıralama kitaplığı, yerel ve yönetilen ortamlar arasında verileri sıralamak için kolay ve en iyi duruma getirilmiş bir yol sağlar. Kitaplığı, PInvoke kullanma gibi daha karmaşık ve daha az verimli yaklaşımları alternatiftir. Bkz: **Overview of Marshaling c++** daha fazla bilgi için.

#### <a name="atl-server"></a>ATL Sunucu

- ATL Sunucu bir paylaşılan kaynak proje olarak yayımlanır.
- ATL Sunucu kod tabanı çoğunu Codeplex'te bir paylaşılan kaynak proje olarak yayımlanmıştır ve Visual Studio 2008'in bir parçası olarak yüklü değil. ATL Sunucu ile ilişkilendirilen çeşitli dosyalar artık, Visual Studio'nun bir parçası değildir. Kaldırılan dosyalar listesi için bkz: **ATL Sunucusu dosyaları kaldırıldı**.
- Kodlama ve sınıflardan atlenc.h ve yardımcı işlevleri ve sınıfları atlutil.h ve atlpath.h kod çözme veri artık ATL kitaplığı bir parçasıdır.
- Microsoft Visual Studio'nun bu sürümleri desteklenir sürece, Visual Studio'nun önceki sürümlerinde bulunan ATL sunucu sürümleri desteklemeye devam edecektir. CodePlex, ATL sunucu kodu geliştirilmesini topluluk projesi olarak devam eder. Microsoft, ATL Sunucu CodePlex sürümünü desteklemiyor.

### <a name="visual-c-compiler-and-linker"></a>Visual C++ Derleyici ve bağlayıcı

#### <a name="compiler-changes"></a>Derleyici değişiklikleri

- Derleyicinin yönetilen artımlı derlemeleri destekler. Bu seçeneği belirttiğinizde, derleyicinin kod başvurulan derleme değiştiğinde derlemeniz yok. Bunun yerine, artımlı derleme gerçekleştirir. Yalnızca bağımlı kod değişiklikleri etkilerse dosyaları derlenir.
- ATL sunucusuyla ilgili öznitelikler artık desteklenmemektedir. Derleyici, artık ATL sunucusu ile doğrudan ilgili çeşitli özniteliklerini de destekler. Kaldırılan öznitelikler tam bir listesi için bozucu değişiklikler bakın.
- Derleyici çekirdekli Intel mikro mimarisi destekler. Derleyicinin kod oluşturma sırasında çekirdekli Intel mikro mimarisi için ayarlama içerir. Varsayılan olarak, bu ayar açıktır ve Pentium 4 ve diğer işlemciler de yardımcı olduğundan devre dışı bırakılamaz.
- Yapı içleri yeni AMD ve Intel işlemcileri destekler. Birkaç yeni iç yönergeleri daha yeni AMD ve Intel işlemcileri işlevselliği destekler. Yeni yapı içleri hakkında daha fazla bilgi için bkz: **ek Akış SIMD uzantıları 3 yönergeler**, **Akış SIMD uzantıları 4 yönergeler**, **SSE4A ve Gelişmiş Bit İşleme iç**, **AES yapı içleri**, **_mm_clmulepi64_si128**, ve **__rdtscp**.
- `__cpuid` İşlevi güncelleştirilir. `__cpuid`, `__cpuidex` İşlevleri artık birkaç yeni özelliklerden en son düzeltmeler AMD ve Intel işlemci desteği. `__cpuidex` İç yenidir ve son işlemcileri'nden daha fazla bilgi toplar.
- `/MP` Derleyici seçeneği, toplam derleme zamanı azaltır. `/MP` Seçeneği dosyaları aynı anda derlemek çeşitli işlemleri oluşturarak birkaç kaynak dosyalarını derlemek için toplam süreyi önemli ölçüde azaltabilirsiniz. Bu seçenek, hiper iş parçacığı, birden çok işlemciye veya birden çok çekirdek destekleyen bilgisayarlarda özellikle yararlıdır.
- `/Wp64` Derleyici seçeneği ve **__w64** anahtar sözcüğü kullanım dışı bırakılmıştır. `/Wp64` Derleyici seçeneği ve **__w64** 64-bit taşınabilirlik sorunlarını algıla, kullanım dışıdır ve derleyici gelecek bir sürümünde kaldırılacak anahtar sözcüğü. Bu derleyici seçeneği ve anahtar sözcüğü yerine, Visual C++ derleyicisi, 64 bit hedef platform kullanın.
- `/Qfast_transcendentals` aşkın işlevleri için satır içi kod oluşturur.
- `/Qimprecise_fwaits` kullandığınızda try blokları için fwaıt komutları iç kaldırır `/fp:except` derleyici seçeneği.

### <a name="linker-changes"></a>Bağlayıcı değişiklikleri

- Kullanıcı hesabı denetimi bilgileri artık yürütülebilir dosyalar için bildirim dosyalarını içine Visual C++ bağlayıcı (link.exe) eklenir. Bu özellik varsayılan olarak etkindir. Bu özellik devre dışı bırakma veya varsayılan davranışı değiştirme hakkında daha fazla bilgi için bkz. `/MANIFESTUAC` (bildirimdeki UAC bilgilerini katıştırır).
- Bağlayıcı artık var `/DYNAMICBASE` Windows Vista'nın rastgele adres alanı düzenini özelliğini etkinleştirmek için seçenek. Bu seçenek, uygulama rastgele yükleme zamanında ReBase işlemi gerçekleştirildi olup olmadığını belirtmek için bir yürütülebilir dosya üstbilgisi değiştirir.

## <a name="whats-new-for-c-in-visual-studio-2005"></a>Visual Studio 2005'te C++ yenilikleri

Visual C++ 2005 Service Pack 1'yeni aşağıdaki özellikleri:

### <a name="intrinsics-for-x86-and-x64"></a>Yapı içleri x86 ve x64

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

### <a name="intrinsics-for-x64-only"></a>Yalnızca x64 için iç bilgileri

- __vmx_on
- __vmx_vmclear
- __vmx_vmlaunch
- __vmx_vmptrld
- __vmx_vmread
- __vmx_vmresume
- __vmx_vmwrite

### <a name="new-language-keywords"></a>Yeni dil anahtar sözcükleri

__sptr, __uptr

### <a name="new-compiler-features"></a>Yeni derleme özellikleri

Derleyici, bu sürümdeki bozucu değişiklikler var.

- ' 64 bit yerel ve çapraz derleyiciler.
- `/analyze` (Kurumsal kod çözümleme) derleyici seçeneği eklenmiştir.
- `/bigobj` derleyici seçeneği eklenmiştir.
- `/clr:pure`, `/clr:safe`, ve `/clr:oldSyntax` sürümüne eklenmiştir. (Daha sonra Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de kaldırılan.)
- Derleyici seçenekleri kullanım dışı: Bu sürüm; birçok derleyici seçeneği kullanım dışı bırakıldı bkz: **kullanım dışı derleyici seçenekleri** daha fazla bilgi için.
- İçindeki çift dönüştürme `/clr` kod azaltılır; bkz **çift dönüştürme (C++)** daha fazla bilgi için.
- `/EH` (Özel durum işleme modeli) veya `/EHs` kullanın; artık bir throw dışında bir şey ile oluşturulan bir özel durum yakalamak için kullanılabilir `/EHa`.
- `/errorReport` (Dahili derleme hatalarını raporla) derleyici seçeneği eklenmiştir.
- `/favor` (64 için İyileştir) derleyici seçeneği eklendi.
- `/FA`, `/Fa` (Listeleme dosyası) derleyici seçeneği eklendi.
- `/FC` (Tam yol, kaynak kodu dosyasında tanılama) derleyici seçeneği eklenmiştir.
- `/fp` Derleyici seçeneği (Floating-Point davranışını belirt) eklendi.
- `/G` (İşlemci için İyileştir) Seçenekleri derleyici seçeneği eklenmiştir.
- `/G` (İşlemci için İyileştir) Seçenekleri derleyici seçeneği eklenmiştir.
- `/G3`, `/G4`, `/G5`, `/G6`, `/G7`, ve `/GB` derleyici seçenekleri kaldırılmıştır. Derleyici artık "tüm mimariler için en iyi çıkış dosyasını oluşturma girişimi şu Harmanlanmış bir modeli" kullanır.
- `/Gf` kaldırıldı. Kullanım `/GF` (yinelenen dizeleri ortadan) bunun yerine.
- `/GL` (Bütün Program iyileştirmesi) ile uyumlu, artık `/CLRHEADER`.
- `/GR` artık varsayılan olarak açıktır.
- `/GS` (Arabellek güvenlik denetimi) artık savunmasız işaretçi parametreleri için bir güvenlik koruması sağlar. `/GS` artık varsayılan olarak açıktır. `/GS` Şimdi de için MSIL ile derlenen işlevlerde çalışır `/clr` (ortak dil çalışma zamanı derlemesi).
- `/homeparams` (Kayıt parametrelerini yığına Kopyala) derleyici seçeneği eklenmiştir.
- `/hotpatch` (Düzeltme eki eklenebilen görüntü oluşturma) derleyici seçeneği eklendi.
- Satır içi işlev buluşsal yöntemler güncelleştirilip güncelleştirilmediğini; bkz: **satır içi**, **__inline**, **__forceinline** ve **inline_depth** daha fazla bilgi için
- Çok sayıda yeni iç işlevleri eklenmiş olan ve daha önce belgelenmemiş birçok yapı içleri artık belgelenmiştir.
- Varsayılan olarak, başarısız olan her çağrı yeni bir özel durum oluşturur.
- `/ML` ve `/MLd` derleyici seçenekleri kaldırılmıştır. Visual C++ artık tek iş parçacıklı, statik olarak bağlı CRT kitaplık desteği de destekler.
- Adlı dönüş değeri ile derleme yaparken, etkinleştirilen iyileştirme, derleyici uygulanan `/O1`, `/O2` (boyutu en aza indirmek, hızı en üst düzeye) `/Og` (Global iyileştirmeler) ve `/Ox` (tam iyileştirme).
- `/Oa` derleyici seçeneği kaldırıldı ancak sessizce yoksayılır; kullanma `noalias` veya `restrict__declspec` derleyici yumuşatma nasıl yaptığını belirtmek için değiştiriciler.
- `/Op` derleyici seçeneğini kaldırdık. Kullanım `/fp` (Bunun yerine kayan nokta davranışını belirt).
- OpenMP artık Visual C++ tarafından desteklenmektedir.
- `/openmp` (OpenMP 2.0 desteğini etkinleştir) derleyici seçeneği eklenmiştir.
- `/Ow` derleyici seçeneği kaldırıldı ancak sessizce yoksayılır. Kullanım `noalias` veya `restrict__declspec` derleyici yumuşatma nasıl yaptığını belirtmek için değiştiriciler.

### <a name="profile-guided-optimizations"></a>Profil Temelli İyileştirmeler

- `/QI0f` kaldırıldı.
- `/QIfdiv` kaldırıldı.
- `/QIPF_B` (B CPU adımlaması için errata) derleyici seçeneği eklenmiştir.
- `/QIPF_C` (C CPU adımlaması için errata) derleyici seçeneği eklenmiştir.
- `/QIPF_fr32` (Değil kullanımı üst 96 kayan noktası kaydeder yapın) derleyici seçeneği eklendi.
- `/QIPF_noPIC` (Konuma bağlı kod üret) derleyici seçeneği eklendi.
- `/QIPF_restrict_plabels` (Hayır işlevleri oluşturulan çalışma zamanında olduğunu varsayın) derleyici seçeneği eklendi.

### <a name="unicode-support-in-the-compiler-and-linker"></a>Derleyicide ve Bağlayıcıda Unicode Desteği

- `/vd` (Oluşturma yer değiştirmelerini devre dışı) artık oluşturulmuş bir nesne üzerinde dynamic_cast işleci kullanmanıza olanak tanır (/ vd2)
- `/YX` derleyici seçeneği kaldırılmıştır. Kullanım `/Yc` (önceden derlenmiş üst bilgi dosyası oluştur) veya `/Yu` (önceden derlenmiş üst bilgi dosyasını kullanma) bunun yerine. Kaldırırsanız `/YX` , yapı yapılandırmalarını ve Değiştir, hiçbir şey, bunu daha hızlı derlemeler neden olabilir.
- `/Zc:forScope` artık varsayılan olarak açıktır.
- `/Zc:wchar_t` artık varsayılan olarak açıktır.
- `/Zd` derleyici seçeneği kaldırılmıştır. Satır numarası yalnızca hata ayıklama bilgileri artık desteklenmiyor. Kullanım `/Zi` bunun yerine (bkz **/z7, / zi, /zı (hata ayıklama bilgileri biçimi)** daha fazla bilgi için).
- `/Zg` artık yalnızca kaynak kodu dosyaları C ve C++ kaynak kodu dosyaları üzerinde geçerlidir.
- `/Zx` (En iyi duruma getirilmiş Itanium kodu hata ayıklama) derleyici seçeneği eklenmiştir.

### <a name="new-language-features"></a>Yeni dil özellikleri

- Attributeattribute artık kullanım dışı bırakılmıştır.
- `appdomain__declspec` değiştiricisi eklendi.
- `__clrcall` çağırma kuralı eklendi.
- (C++) kullanım dışı **declspec** değiştiricisi artık bir kullanıcı bir kullanım dışı sınıfta veya işlevde erişim çalıştığında derleme zamanında gösterilecek bir dize belirtmenize olanak verir.
- **dynamic_cast** işleci olan yeni değişiklikler.
- Yerel numaralandırmalar artık, temel alınan türü belirtmenizi sağlar.
- `jitintrinsicdeclspec` değiştiricisi eklendi.
- `noaliasdeclspec` değiştiricisi eklendi.
- `process__declspec` değiştiricisi eklendi.
- **soyut**, **geçersiz kılma**, ve **korumalı** yerel derlemeler için geçerlidir.
- **__restrict** anahtar sözcüğü eklendi.
- `restrictdeclspec` değiştiricisi eklendi.
- **__thiscall** artık bir anahtar sözcüktür.
- **__unaligned** anahtar sözcüğü artık belgelenmiştir.
- **volatile** (C++) en iyi duruma getirme ile ilgili davranışı güncelleştirdi.

### <a name="new-preprocessor-features"></a>Yeni önişlemci özellikleri

- __CLR_VER önceden tanımlanmış makro eklendi.
- Açıklama (C/C++) pragmayı artık kabul `/MANIFESTDEPENDENCY` bağlayıcı yorum olarak. Açıklama exestr seçeneği kullanım dışı bırakıldı.
- `embedded_idl` öznitelik ( `#import` yönergesi) artık isteğe bağlı bir parametre alır.
- `fenv_access` Pragması
- `float_control` Pragması
- `fp_contract` Pragması
- Genel değişkenler pragması yerleştirebilirsiniz yönetilmeyen hem de yönetilmeyen bölümler, yönetilen, genel değişkenler varsa bildirildikleri sırada başlatılmayacak. Bu olası bir değişiklik olur, örneğin, yönetilen bir genel değişkenlerle bir yönetilmeyen genel değişkeni başlatılır ve oluşturulmuş tam olarak yönetilen bir nesnenin gereklidir.
- İnit_seg ile belirtilen bölümler artık salt okunur ve okuma/önceki sürümlerinde olduğu gibi yazma değil.
- inline_depth varsayılan artık 16'dır. Visual C++ .NET 2003'te geçerli bir varsayılan değer 16 ayrıca oldu.
- _Integral_max_bıts önceden tanımlanmış makro eklendi, önceden tanımlanmış makrolar bakın.
- _M_CEE _M_CEE_PURE ve _M_CEE_SAFE önceden tanımlanmış makrolar eklendi, önceden tanımlanmış makrolar bakın.
- _M_ıx86_fp önceden tanımlanmış makro eklendi.
- _M_X64 önceden tanımlanmış makro eklendi.
- `make_public` Pragması
- `managed`, `unmanaged` pragma söz dizimi güncelleştirildi (artık `push` ve `pop`)
- mscorlib.dll artık örtük olarak tarafından başvuruluyor `#using` tüm yönerge `/clr` derlemeleri.
- _OPENMP önceden tanımlanmış makro eklendi.
- en iyi duruma getirme pragma güncelleştirildi ve w artık geçerli parametrelerdir.
- #import no_registry özniteliği eklendi.
- `region`, `endregion` pragmaları eklendi
- _Vc_nodefaultlıb önceden tanımlanmış makro eklendi.
- Variadic makrolar artık uygulanır.
- `vtordisp` kullanım dışı ve Visual C++'ın gelecek sürümde kaldırılacak.
- `warning` Pragma bastır belirticisi artık sahiptir.

### <a name="new-linker-features"></a>Yeni bağlayıcı Özellikleri

- Bağlayıcı girişi olarak modülleri (derleme olmayan MSIL Çıkış dosyalarını) artık izin verilir.
- `/ALLOWISOLATION` (Bildirim arama) bağlayıcı seçeneği eklendi.
- `/ASSEMBLYRESOURCE` (Yönetilen kaynağı katıştır) artık derlemede kaynağın adını belirtin ve kaynak derlemesinde özel olduğunu belirtmek için izin verecek şekilde güncelleştirildi.
- `/CLRIMAGETYPE` (CLR görüntü türünü belirt) bağlayıcı seçeneği eklendi.
- `/CLRSUPPORTLASTERROR` (Son hata kodunu Koru PInvoke çağrıları için) bağlayıcı seçeneği eklendi.
- `/CLRTHREADATTRIBUTE` (CLR iş parçacığı özniteliğini Ayarla) bağlayıcı seçeneği eklendi.
- `/CLRUNMANAGEDCODECHECK` (SuppressUnmanagedCodeSecurityAttribute ekleme), bağlayıcı seçeneği eklendi.
- `/ERRORREPORT` (Dahili bağlayıcı hatalarını raporla) bağlayıcı seçeneği eklendi.
- `/EXETYPE` bağlayıcı seçeneği kaldırılmıştır. Bağlayıcı artık oluşturma Windows 95 ve Windows 98 aygıt sürücülerini destekler. Bu cihaz sürücüleri oluşturmak için uygun bir DDK kullanın. EXETYPE anahtar sözcüğü artık modül tanımı dosyaları için geçerli değil.
- `/FUNCTIONPADMIN` (Düzeltme eki eklenebilen görüntü oluşturma) bağlayıcı seçeneği eklendi.
- `/LTCG` bağlayıcı seçeneği ile derlenmiş modüller üzerinde desteklenen artık `/clr`. `/LTCG` Ayrıca Profil temelli iyileştirmeler desteklemek için güncelleştirildi.
- `/MANIFEST` (Yan yana derleme bildirimi oluşturma) bağlayıcı seçeneği eklendi.
- `/MANIFESTDEPENDENCY` (Bildirim bağımlılıklarını belirt) bağlayıcı seçeneği eklendi.
- `/MANIFESTFILE` (Bildirim dosyasını Adlandır) bağlayıcı seçeneği eklendi.
- `/MAPINFO:LINES` bağlayıcı seçeneği kaldırılmıştır.
- `/NXCOMPAT` (Veri yürütme önlemesi ile uyumlu) bağlayıcı seçeneği eklendi.
- `/PGD` (Permutasyonları iyileştirmeler için veritabanını belirt) bağlayıcı seçeneği eklendi.
- `/PROFILE` (Performans araçları Profiler) bağlayıcı seçeneği eklendi.
- `/SECTION` (Bölüm özniteliklerini belirt) bağlayıcı seçeneği artık özniteliği olumsuzlama ve artık L ya da D (VxD ilgili) öznitelikleri destekler.
- Derleyicide ve Bağlayıcıda Unicode Desteği
- `/VERBOSE` Şimdi (ilerleme iletilerini Yazdır) bağlayıcı seçeneği de ICF ve REF kabul eder.
- `/VXD` bağlayıcı seçeneği kaldırılmıştır. Bağlayıcı artık oluşturma Windows 95 ve Windows 98 aygıt sürücülerini destekler. Bu cihaz sürücüleri oluşturmak için uygun bir DDK kullanın. VXD anahtar sözcüğü artık modül tanımı dosyaları için geçerli değil.
- `/WS` bağlayıcı seçeneği kaldırılmıştır. `/WS` Windows NT 4.0 için hedeflenen görüntülerini değiştirmek için kullanıldı. IMAGECFG.exe -R dosya adı yerine kullanılabilir `/WS`. Windows NT 4.0 CD-ROM sürücüsüne SUPPORT\DEBUG\I386\IMAGECFG IMAGECFG.exe ulaşabilirsiniz. EXE.
- `/WX` (Bağlayıcı uyarılarını hata olarak) bağlayıcı seçeneği artık belgelenmiştir.

### <a name="new-linker-utility-features"></a>Yeni bağlayıcı yardımcı programı özellikleri

- `/ALLOWISOLATION` editbin seçeneği eklendi
- Açıklama modül tanım dosyası deyimi kaldırılır. Bağlayıcı artık sanal cihaz sürücüleri oluşturmayı da destekler.
- `/ERRORREPORT` bscmake.exe, dumpbin.exe ve lib.exe editbin.exe seçeneği eklenmiştir.
- `/LTCG` LIB seçeneği eklenmiştir.
- `/NXCOMPAT` editbin seçeneği eklenmiştir.
- `/RANGE` dumpbin seçeneği eklenmiştir.
- `/TLS` dumpbin seçeneği eklenmiştir.
- `/WS` editbin seçeneği kaldırılmıştır. `/WS` Windows NT 4.0 için hedeflenen görüntülerini değiştirmek için kullanıldı. IMAGECFG.exe -R dosya adı yerine kullanılabilir `/WS`. Windows NT 4.0 CD-ROM sürücüsüne SUPPORT\DEBUG\I386\IMAGECFG IMAGECFG.exe ulaşabilirsiniz. EXE.
- /WX [: NO] LIB seçeneği eklendi.

### <a name="new-nmake-features"></a>NMAKE yenilikleri

- `/ERRORREPORT` eklendi.
- `/G` eklendi.
- Önceden tanımlanmış kurallar güncelleştirildi.
- Özyineleme makroları belgelenen $(MAKE) makrosu, artık nmake.exe için tam yolunu sağlar.

### <a name="new-masm-features"></a>Yeni MASM özellikleri

- MASM ifadeleri artık 64-bit değerlerdir. Önceki sürümlerde MASM ifadeleri 32-bit değerleri yoktu.
- Yönerge __asm int 3 artık bir işlev doğal olarak derlenmesine neden olur.
- Diğer ad (MASM) artık belgelenmiştir.
- `/ERRORREPORT` ML.exe ve ml64.exe seçeneği eklendi.
- . FPO artık belgelenmiştir.
- Visual C++ 2005'te H2INC.exe gelmeyecektir. H2INC kullanmaya devam etmeniz gerekiyorsa, Visual C++'ın önceki bir sürümden H2INC.exe kullanın.
- IMAGEREL işleci eklendi.
- işleç hıgh32 eklendi.
- işleç LOW32 eklendi.
- ml64.exe x64 için MASM sürümüdür mimarisi. X64 çeviren x64 .asm dosyasına nesne dosyaları. Satır içi derleme dili x64 içinde desteklenmeyen derleyici. Aşağıdaki MASM yönergeleri (x64) ml64.exe için eklenmiştir:
- .ALLOCSTACK
- .ENDPROLOG
- .PUSHFRAME
- .PUSHREG
- .SAVEREG
- .SAVEXMM128
- . SETFRAME yanında PROC yönergesi ile yalnızca x64 söz dizimi güncelleştirildi.
- MMWORD yönergesi eklenmiştir.
- `/omf` (ML.exe komut satırı seçeneği) artık gelir `/c`. OMF biçimi nesnelerini bağlamanın ML.exe desteklemez.
- SEGMENT yönergesi artık ek öznitelikler destekler.
- SECTIONREL işleci eklendi.
- XMMWORD yönergesi eklenmiştir.

### <a name="new-crt-features"></a>CRT yenilikleri

- Çeşitli işlevlerin güvenli sürümleri eklendi. Bu işlevler, hataları daha iyi bir şekilde işlemek ve ortak güvenlik açıklarını önlemeye yardımcı olmak için arabellek daha sıkı denetimler uygular. Yeni Güvenli sürümleri tarafından tanımlanan **_Yanları** soneki.
- Çok daha az güvenli sürümlerinin mevcut işlevler kullanım dışı bırakıldı. Kullanımdan kaldırma uyarıları devre dışı bırakmak için _crt_secure_no_warnıngs tanımlayın.
- Artık birçok mevcut işlevleri kendi parametrelerini doğrular ve geçersiz bir parametre geçirildiğinde, geçersiz parametre işleyicisini çağırır.
- Birçok var olan işlev kümesini şimdi `errno` burada yaptıkları işlemin önce değil.
- Typedef `errno_t` tamsayı türü ile eklenmiştir. `errno_t` Her bir işlevin dönüş türü veya parametresi ilgilenen hata kodları ile kullanılan `errno`. `errno_t` değiştirir `errcode`.
- Yerel ayara bağlı işlevleri artık yerel ayar bir parametre geçerli yerel ayarı kullanmak yerine alan sürümleri vardır. Bu yeni işlevler sahip **_l** soneki. Çeşitli yeni işlevler, yerel nesnelerle çalışmayı eklendi. Yeni işlevler eklemek `_get_current_locale`, `_create_locale` ve `_free_locale`.
- Yeni işlevlerin kilitlenmesini ve kilidinin açılmasını dosya tanıtıcıları desteği eklendi.
- `_spawn` İşlevler ailesini sıfırlama başarılı olduğunda sıfır errno önceki sürümlerde olduğu gibi.
- Sürümleri `printf` ailesindeki işlevlerin bağımsız değişkenlerin kullanıldığı sırayı kullanılabilir belirtmenizi sağlar.
- Unicode desteklenen metin biçimi sunulmuştur. İşlev `_open` _O_TEXTW ve _O_UTF8 _O_UTF16 özniteliklerini de destekler. `fopen` İşlevi destekler "ccs ENCODING =" Unicode biçiminde belirtme yöntemi.
- Yönetilen kodda (MSIL) yerleşik CRT kitaplığı yeni bir sürümü kullanıma sunulmuştur ve ile derleme yapılırken kullanılan `/clr` (ortak dil çalışma zamanı derlemesi) seçeneği.
- _fileinfo kaldırıldı.
- Varsayılan boyutu `time_t` aralığını genişletir, 64 bit sunulmuştur `time_t` ve birkaç saat işlevlerini 3000 yıl.
- CRT artık bir başına iş parçacığı başına yerel ayar destekliyor. İşlev `_configthreadlocale` bu özelliği desteği eklendi.
- `_statusfp2` Ve `__control87_2` işlevleri, erişim ve kayan nokta denetim sözcüğünü hem x87 üzerinde ve SSE2 kayan noktalı denetim noktası işlemci izin vermek için eklendi.
- `_mkgmtime` Ve `_mkgmtime64` işlevleri (GMT) Greenwich saati (yapı tm) dönüştürme için destek sağlamak üzere eklendi.
- Değişiklikler yapıldı `swprintf` ve `vswprintf` standarda daha iyi uyacak şekilde.
- Yeni başlık dosyası, INTRIN. H, bazı iç işlevleri için prototipler sağlar.
- `fopen` İşlevi artık N özniteliğe sahip.
- `_open` İşlevi artık _O_NOINHERIT özniteliğe sahip.
- `atoi` İşlevi artık INT_MAX ve kümelerini `errno` ERANGE taşma için. Önceki sürümlerde taşma davranışı tanımlanmamış.
- `printf` Ailesi, kayan nokta işlevleri destekler onaltılı çıkış uygulanan biçim türü belirteçleri kullanarak ANSI C99 standardı göre %a ve %A.
- `printf` Ailesi, artık "l" (long long) boyut öneki destekler.
- `_controlfp` İşlevi daha iyi performans için iyileştirilmiştir.
- Bazı işlevlerin hata ayıklama sürümleri eklendi.
- Eklenen `_chgsignl` ve `_cpysignl` (uzun çift sürümleri).
- Eklenen `_locale_t` türü için tablo.
- Yeni makrosu `_countof` makrosu, bir dizideki öğelerin sayısını bilgi işlem için eklendi.
- Her işlev konuda, .NET Framework eşdeğerleri bir bölüm eklenmiştir.
- Birçok dize işlevleri artık çıkış arabelleği çok küçük olduğunda başarısız yerine dize kesilmesi seçeneğiniz vardır; bkz: **_TRUNCATE**.
- `_set_se_translator` artık gerektirir `/EHa` derleyici seçeneği.
- `fpos_t` artık **__int64** altında `/Za` (için C kodu) ve ne zaman __STDC__ (C++ kodunu) el ile ayarlayın. Eskiden olduğu bir **yapı**.
- _Crt_dısable_perfcrıt_locks tek iş parçacıklı programlar g/ç performansını artırabilir.
- POSIX adları yerine ISO C++ uyumlu adları kullanımdan kaldırıldı (örneğin, `_getch` yerine `getch`).
- Yeni bağlantı seçenekleri .obj dosyaları pure modunda için kullanılabilir
- `_recalloc` özelliklerini birleştiren `realloc` ve `calloc`.

## <a name="whats-new-for-c-in-visual-studio-2003"></a>Visual Studio 2003'te C++ yenilikleri

### <a name="compiler"></a>Derleyici

- Yönetilen Uzantılar'ile güncel sürümün derleyici çalışma zamanının önceki bir sürümünde oluşturulan C++ uygulama için çalıştırma hakkında bilgiler.
- Sık sorulan sorular C++ için Yönetilen Uzantılar.
- C++ için Yönetilen Uzantılar'ı kullanmak için mevcut, yerel bir uygulama bağlantı noktası gösteren bir anlatım eklenmiştir: İzlenecek yol: .NET Framework bileşenleri ile çalışmak için var olan bir yerel C++ uygulama taşıma.
- Bu gibi durumlarda, bir temsilci artık bir değer türünün bir yöntem oluşturabilirsiniz.
- C++ standardı ile uyum derleyicinin için Visual C++ .NET 2003 önemli ölçüde geliştirilmiştir.
- `/arch` derleyici seçeneği eklendi.
- `/Gf` kullanım dışı ve Visual C++'ın bir sonraki sürümde kaldırılacak.
- `/G7` derleyici seçeneği eklendi.
- `/GS` Derleyici seçeneği, yerel değişkenler doğrudan arabellek taşmalarına korumaya yardımcı olmak için geliştirilmiştir.
- `/noBool` Derleyici seçeneği kaldırılmıştır. Derleyici artık tanır **bool** yalnızca bir anahtar sözcüğü (ve bir tanımlayıcı değil) bir c++ kaynak kod dosyasını görüntülenir.
- **Uzun uzun** türü olarak kullanıma sunuldu bir **typedef** , **__int64** unutmayın henüz destek **uzun uzun** CRT'deki.
- `/Zm` Artık derleyici seçeneği önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir.
- _Interlockedcompareexchange iç artık belgelenmiştir.
- _Interlockeddecrement iç artık belgelenmiştir.
- _Interlockedexchange iç artık belgelenmiştir.
- _Interlockedexchangeadd iç artık belgelenmiştir.
- _Interlockedıncrement iç artık belgelenmiştir.
- _ReadWriteBarrier içi eklendi.

### <a name="attributes"></a>Öznitelikler

- `implements` öznitelik şimdi belgelenmiştir.

### <a name="linker-features"></a>Bağlayıcı özellikleri

Aşağıdaki bağlayıcı anahtarlarını eklenmiştir:

- / ASSEMBLYDEBUG
- / ASSEMBLYLINKRESOURCE
- DELAYSIGN
- / KEYFILE
- / KEYCONTAINER
- / SAFESEH

### <a name="masm"></a>MASM

. SAFESEH yönergesi ve `/safeseh` ml.exe seçeneği eklendi.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)
