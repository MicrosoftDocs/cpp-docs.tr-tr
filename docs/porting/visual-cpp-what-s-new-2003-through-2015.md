---
title: Visual C++ ne&#39;s 2015 aracılığıyla yeni 2003 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9778a9d456ebd0fed6bc36c2c631849bcbfe11d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705611"
---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Visual C++ ne&#39;s 2015 aracılığıyla yeni 2003

Bu sayfayı tüm "Yenilikler" sayfalar için Visual C++'in tüm sürümleri, Visual Studio 2015'ten 2003'e toplar. Visual C++ önceki sürümlerinden yükseltme yaparken yararlı olabilir durumunda bu bilgiler kolaylık sağlanır.

**Not** Visual Studio 2017 hakkında daha fazla bilgi için bkz: [Visual Studio 2017'de Visual C++ yenilikleri](../what-s-new-for-visual-cpp-in-visual-studio.md) ve [uygunluk Visual Studio 2017'de Visual C++ yenilikleri](../cpp-conformance-improvements-2017.md).

## <a name="whats-new-for-c-in-visual-studio-2015"></a>C++, Visual Studio 2015'te Yenilikler

Visual Studio 2015 ve daha sonra devam eden iyileştirmeler derleyici uyumluluğu bazen derleyici mevcut kaynak kodunuzu nasıl anlar değiştirebilirsiniz. Bu gerçekleştiğinde, yapı veya önceden oluşturulmuş ve düzgün çalışmasına görünüyor kodu dahi davranış farklılıkları sırasında yeni ya da farklı hatalarla karşılaşabilirsiniz.

 Neyse ki, bu farklılıklar çok az kayıpla veya hiç kaynak kodunuzu çoğunu üzerinde etkisi ve kaynak kodu veya başka değişiklikler bu farklılıklar gidermenin gerekli olduğunda, düzeltmeleri genellikle küçük ve düz ilet. Birçok değiştirilmesi gerekebilir önceden kabul edilebilir kaynak kod örnekleri dahil ettiğiniz *(önce)* ve bunları düzeltmek için düzeltmeler *(sonra)*.

 Bu farklılıklar, kaynak kodu veya diğer yapı yapıları etkileyebilir karşın, bunların Visual C++ sürümleri için güncelleştirmeler arasında ikili uyumluluğu etkilemez. Değişiklik, daha ciddi bir tür *değişiklik çiğnemekten* ikili uyumluluğu etkileyebilir, ancak bu tür bir ikili uyumluluğu sonlarını yalnızca Visual C++ ana sürümleri arasında oluşur. Örneğin, Visual C++ 2013 ve Visual C++ 2015 arasında. Visual C++ 2013 ve Visual C++ 2015 arasında oluştu önemli değişiklikler hakkında daha fazla bilgi için bkz: [Visual C++ değişiklik geçmişini 2003 2015](../porting/visual-cpp-change-history-2003-2015.md).

- [Visual Studio 2015'te uygunluk geliştirmeleri](#VS_RTM)

- [Visual Studio 2015 güncelleştirme 1 uygunluk yenilikleri](#VS_Update1)

- [Visual Studio 2015 güncelleştirme 2 uygunluk yenilikleri](#VS_Update2)

- [Visual Studio 2015 güncelleştirme 3 uygunluk yenilikleri](#VS_Update3)

### <a name="VS_RTM"></a> Visual Studio 2015'te uygunluk geliştirmeleri

- **/ZC:forScope-seçeneği** derleyici seçeneği **/Zc:forScope-** kullanım dışıdır ve gelecek sürümde kaldırılacak.

   ```output
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release
   ```

   Seçeneği genellikle kullanır, burada, standart göre kullanıcılar fazlası kapsam dışında noktadan sonra değişkenleri döngü standart olmayan kod izin vermek üzere kullanıldı. /Za bu yana /Za seçeneğiyle derlediğiniz zaman yalnızca gerekli kullanarak bir döngü sonundan her zaman izin sonra döngü değişkeni için. (Örneğin, kodunuzu diğer derleyiciler için taşınabilir tasarlanmamıştır) standartları uyumluluğu hakkında önemli değil, /Za seçeneğini devre dışı bırakın (veya dil uzantılarını devre dışı bırakma özelliğini Hayır olarak ayarlayın). Taşınabilir, standartlara uygun kod yazma hakkında dikkat edin, böylece bu değişkenleri bildirimi döngü dışında bir nokta taşıyarak standardına uygun kodunuzu yeniden yazma.

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

- **ZG derleyici seçeneği.** /Zg derleyici seçeneği (işlev prototipleri oluşturma), artık mevcut değil. Bu derleyici seçeneği önceden kullanımdan kaldırılmıştır.

- Artık birim testleri C + ile çalıştırabilirsiniz +/ CLI mstest.exe ile komut satırından. Bunun yerine, vstest.console.exe kullanın

- **mutable anahtar sözcüğü.** `mutable` Depolama sınıfı tanımlayıcısı burada önceden derlenmiş hatasız yerlerde artık verilir. Derleyici Hatası C2071 şimdi verir (geçersiz depolama sınıfı). Standart göre değişebilir tanımlayıcı yalnızca sınıfı veri üyesi adlarına uygulanabilir ve const veya statik bildirilen adlarına uygulanamaz ve üyeleri başvurmak için uygulanamaz.

   Örneğin, aşağıdaki kodu göz önünde bulundurun:

   ```cpp
    struct S {
        mutable int &r;
    };
   ```

   Visual C++ derleyicisi önceki sürümlerinde bu kabul ancak şimdi derleyici aşağıdaki hata verir:

   ```Output
    error C2071: 'S::r': illegal storage class
   ```

   Hatayı düzeltmek için basitçe yedekli mutable anahtar sözcüğü kaldırın.

- **char_16_t ve char32_t** artık kullanabilirsiniz `char16_t` veya `char32_t` bir typedef adlarda olarak çünkü bu türleri artık yerleşik kabul edilir. Kullanıcılar ve tanımlamak için kitaplık yazarları için ortak `char16_t` ve `char32_t` diğer adlarını olarak `uint16_t` ve `uint32_t`sırasıyla.

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

   Kodunuzu güncelleştirmek için typedef bildirimleri kaldırın ve bu adları birbiriyle çakışır diğer tanımlayıcıları yeniden adlandırın.

- **Tür olmayan şablon parametreleri** bağımsız açık şablon sağladığınızda tür olmayan şablon parametreleri içeren belirli bir kod artık doğru türü uyumluluk için kontrol edilir. Visual C++'ın önceki sürümlerinde hatasız derlenmiş Örneğin, aşağıdaki kodu.

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

   Şablon parametresi türü şablon bağımsız değişken eşleşmediği için geçerli derleyici doğru bir hata verir (const üyesi için bir işaretçi parametredir, ancak const olmayan işlev f):

   ```Output
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'
   ```

   Kodunuzda bu hatayı gidermek için kullandığınız şablon bağımsız değişken türü şablon parametresi türü eşleştiğinden emin olun.

- **__declspec(align)** derleyici artık kabul `__declspec(align)` işlevlerde. Bu her zaman gözardı edildi ancak şimdi bir derleyici hatası oluşturur.

   ```cpp
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations
   ```

   Bu sorunu gidermek için kaldırın `__declspec(align)` işlev bildirimi gelen. Herhangi bir etkisi sahip olduğundan, kaldırarak herhangi bir şeyi değiştirmez.

- **Özel durum işleme** birkaç özel durum işleme için değişiklik vardır. İlk olarak, özel durum nesneleri copyable veya taşınabilir olması gerekir. Aşağıdaki kod derlenmiş [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], ancak içinde derlenmiyor [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:

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

   Nesne bir özel durum işleme normal seyrinde olduğu sürece kopyalanamaz şekilde kopya oluşturucu özel sorunudur. Kopya Oluşturucu bildirilmişse aynı durum geçerlidir `explicit`.

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

   Kodunuzu güncelleştirmek için özel durum nesnesi kopya Oluşturucu ortak ve işaretlenmemiş olduğundan emin olun `explicit`.

   Değere göre bir özel durum yakalama özel durum nesnesi copyable olmasını gerektirir. Aşağıdaki kod derlenmiş [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], ancak içinde derlenmiyor [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:

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

   İçin parametre türü değiştirerek bu sorunu gidermek `catch` bir başvuru.

   ```cpp
    catch(D& d)
    {
    }
   ```

- **Dize değişmez değerleri makroları tarafından izlenen** derleyici artık kullanıcı tanımlı değişmez değerler destekler. Dize değişmez değerleri müdahalede bulunan tüm boşluk olmadan makroları ve ardından hataları veya beklenmeyen sonuçlara neden, kullanıcı tanımlı değişmez değerler, sonuç olarak yorumlanır. Örneğin, aşağıdaki kod önceki derleyicileri başarıyla derlenmiş:

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

   Derleyici bu bir dize olarak değişmez değer olarak "hello"yok"genişletilir bir makro tarafından izlenen" yorumlanır ve iki dize değişmez değerleri birine ardından birleştirilmiş. İçinde [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]derleyici bu kullanıcı tanımlı bir sabit değer olarak yorumlar, ancak tanımlı hiçbir eşleşen kullanıcı tanımlı değişmez değer _x olduğundan, bir hata verir.

   ```cpp
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found
    note: Did you forget a space between the string literal and the prefix of the following string literal?

   ```

   Bu sorunu gidermek için dize sabit değeri ile makrosu arasında bir boşluk ekleyin.

- **Bitişik dize değişmez değerleri** benzer şekilde önceki, dizesini ayrıştırma, ilgili değişiklikler nedeniyle hiçbir boşluk olmadan bitişik dize değişmez değerleri (ya da geniş veya dar karakteri dize değişmez değerleri) tek bir birleştirilmiş dize olarak yorumlanan Visaul C++ önceki sürümleri. İçinde [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], artık iki dizeyi arasında boşluk eklemeniz gerekir. Örneğin, aşağıdaki kodu değiştirilmelidir:

   ```cpp
    char * str = "abc""def";
   ```

   Bir alanı arasında iki dize eklemeniz yeterlidir.

   ```cpp
    char * str = "abc" "def";
   ```

- **Yeni yerleştirme ve delete** bir değişiklik delete işleci ilkelerinizle uyumlu C ++ 14 getirmek için standart yapılmadı. Standartlar değişiklik ayrıntılarını bulunabilir [C++ boyutta ayırmayı kaldırma](http://isocpp.org/files/papers/n3778.html). Değişiklikleri boyutu parametresi alan genel delete işleci biçiminde ekleyin. (Yerleştirme yeni işleciyle karşılık gelecek şekilde) aynı imzayla daha önce bir delete işleci kullanıyorsanız, derleyici hatası alırsınız sonu değişikliktir (burada yeni yerleştirme kullanılır, beri noktada oluşur C2956 o kod derleyici burada uygun eşleşen tanımlamayı dener konumda delete işleci).

   İşlev `void operator delete(void *, size_t)` edildi yerleştirme yeni işlev için karşılık gelen bir yerleştirme delete işleci "void \* new işleci (size_t, size_t)" C ++ 11. C ++ 14 boyutlu ayırmayı kaldırma ile bu silme işlevi sunulmuştur bir *normal ayırmayı kaldırma işlevi* (genel delete işleci). Standart bir yerleştirme yeni kullanımını karşılık gelen bir silme işlevini arar ve her zamanki ayırmayı kaldırma işlevi bulur, program hatalı oluşturulmuş olmasını gerektirir.

   Örneğin, kodunuzu yeni bir yerleştirme ve yerleştirme delete tanımlar varsayın:

   ```cpp
    void * operator new(std::size_t, std::size_t);
    void operator delete(void*, std::size_t) noexcept;

   ```

   Sorun, tanımladığınız yerleştirme delete işleci yeni küresel ölçekli delete işleci arasındaki işlevi imzaları eşlemesinde nedeniyle oluşur. Farklı bir tür size_t dışındaki tüm yerleştirme için yeni kullanmak ve delete işleçleri olup olmadığını göz önünde bulundurun.  Size_t typedef türünü derleyici bağımlı olduğunu unutmayın; Visual C++'ta imzasız int için typedef olur. Bu gibi bir enum türü kullanmak iyi bir çözümdür:

   ```cpp
    enum class my_type : size_t {};

   ```

   Ardından, yerleştirme yeni tanımınız değiştirebilir ve bu tür size_t yerine ikinci bağımsız değişken olarak kullanmak için silebilirsiniz. Ayrıca yeni türü geçirmek için yeni yerleştirme çağrıları güncelleştirmeniz gerekir (kullanarak örneğin, `static_cast<my_type>` tamsayı değerini dönüştürmek için) ve tanımını yeni güncelleştirme ve tamsayı türüne yayınlanamıyor silin. Bunun için bir numaralandırma kullanmanız gerekmez; sınıf türü size_t üyesi ile de çalışır.

   Bir alternatif yeni yerleştirme tamamen ortadan kaldırmak mümkün olabilir çözümüdür. Kodunuzu yerleştirme yeni burada yerleştirme bağımsız değişkeni olan nesne boyutunu tahsis edilen veya silinen, sonra boyutlu ayırmayı kaldırma özelliği, kendi özel bellek havuzu kodunuzu değiştirmek uygun olabilir ve, elden çıkarabilirsiniz bellek havuzundaki uygulamak için kullanıyorsa, yerleştirme işlevler ve yalnızca kendi iki bağımsız değişken delete işleci yerine yerleştirme işlevlerini kullanın.

   Kodunuzu hemen güncelleştirmek istemiyorsanız, derleyici seçeneği /Zc:sizedDealloc-kullanarak eski davranışa geri dönebilirsiniz. Bu seçeneği kullanırsanız, iki bağımsız değişken silme işlevleri mevcut değil ve yerleştirme delete operatörünüze ile bir çakışma neden olmaz.

- **Birleşim veri üyeleri**

   Veri üyeleri birleşimler artık başvuru türleri olabilir. Başarıyla derlenen aşağıdaki kod [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], ancak bir hata üretir [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].

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

   Yukarıdaki kod aşağıdaki hatalar üretir:

   ```Output
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type
   ```

   Bu sorunu gidermek için başvuru türleri bir işaretçi veya bir değeri değiştirin. Bir işaretçi türü değiştirilmesi birleşim alan kullanan kodu değişiklikleri gerektirir. Kod bir değer ile değiştirmek birleşim türlerini alanları aynı bellek paylaşmak olduğundan, diğer alanlar etkileyen birleşim içinde depolanan verileri değiştirirsiniz. Değer boyutuna bağlı olarak, bu da UNION boyutu değişebilir.

- **Anonim birleşimler** standart için daha fazla uyumluluğunu sunulmuştur. Derleyici önceki sürümlerini bir açık oluşturucu ve yıkıcı anonim birleşimler için oluşturulur. Bunlar de silinir [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].

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

   Yukarıdaki kod aşağıdaki hatası oluşturur [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:

   ```cpp
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here
   ```

   Bu sorunu çözmek için kendi tanımları oluşturucusu ve/veya yıkıcı sağlayın.

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

- **Anonim yapılar ile birleşimler** standarda uygun olması için çalışma zamanı davranışı Birleşimlerdeki anonim yapılar üyeleri için değişmiştir. Bu tür bir birleşim oluşturulduğunda UNION anonim yapısı üyeleri Oluşturucusu artık dolaylı olarak adlandırılır.   Ayrıca, UNION kapsam dışına çıktığında yıkıcı bir birleşim anonim yapısı üyeler için artık dolaylı olarak adlandırılır. UNION U yıkıcı sahip adlandırılmış bir yapı S olan bir üyeyi içeren bir anonim yapısı içeren aşağıdaki kod, göz önünde bulundurun.

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

   İçinde [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], S Oluşturucusu UNION oluşturulduğunda ve işlev f yığınının Temizlenen S yıkıcı denir denir. Ancak [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], oluşturucusu ve yıkıcı değil olarak adlandırılır. Derleyici bu davranış değişikliği hakkında bir uyarı verir.

   ```Output
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called
   ```

   Özgün davranışını geri yüklemek için anonim yapısı bir ad verin. Anonim olmayan yapılar çalışma zamanı davranışını derleyici sürümü bağımsız olarak aynıdır.

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

   Alternatif olarak, yeni işlevler oluşturucusu ve yıkıcı kodu taşımayı deneyin ve bu işlevler oluşturucusu ve UNION yıkıcı çağrıları ekleyin.

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

- **Şablon çözümleme** şablonları için ad çözümlemesi için değişiklikler yapıldı. Bir ad çözümlemesi için aday değerlendirirken C++'da, göz önünde bulundurarak olası eşleşmeler olarak bir veya daha fazla adlarla geçersiz şablonu örneklemesi üreten durumda olabilir. Bu geçersiz örneklemesi normalde derleyici hataları, SFINAE (değiştirme hatası olmayan bir hata) bilinen bir ilkeye neden olmaz.

   Şimdi, bir sınıf şablonu uzmanlaşması örneği oluşturmak için derleyici SFINAE gerektirir, bu işlem sırasında oluşan hataları derleyici hataları demektir. Önceki sürümlerde derleyici böyle hataları yoksayma. Örneğin, aşağıdaki kodu göz önünde bulundurun:

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

   Geçerli derleyicisi ile derleme yaparsanız, aşağıdaki hatayı alıyorsunuz:

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

   İs_base_of ilk çağırma noktasında sınıfı kullandığınız olmasıdır ' henüz tanımlanmamış.

   Bu durumda, düzeltme sınıf tanımlanan kadar böyle tür özellikleri kullanmamaktır. Kod dosyasının başlangıcına B ve D tanımlarını taşırsanız, hata çözümlenir. Tanımları üstbilgi dosyalarında değilse, sorunlu şablonları kullanılmadan önce herhangi bir sınıf tanımları derlenmiş emin olmak üst bilgi dosyaları Include deyimleri sırasını denetleyin.

- **Kopyalama oluşturucular** hem de [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] ve Visual Studio 2015 derleyici oluşturan bir sınıf için bir kopya Oluşturucu bu sınıfın bir kullanıcı tarafından tanımlanan taşıma oluşturucusuna ancak hiçbir kullanıcı tarafından tanımlanan kopya Oluşturucu varsa. Dev14 içinde bu örtük olarak oluşturulmuş kopya Oluşturucu de işaretlenmiş "delete =".

### <a name="VS_Update1"></a> Visual Studio 2015 güncelleştirme 1 uygunluk yenilikleri

- **Özel sanal taban sınıflar ve dolaylı devralma** Derleyici önceki sürümlerinden izin üye işlevlerini çağırın türetilmiş bir sınıf kendi *dolaylı olarak türetilmiş* `private virtual` temel sınıflar. Bu eski davranış yanlış ve C++ Standart uygun değil. Derleyici artık bu şekilde yazılan kod kabul eder ve derleyici hatası C2280 sonuç olarak verir.

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

  veya

   ```cpp
    class base;  // as above

    class middle: private virtual base {};
    class top: public virtual middle, private virtual bottom {};

    void destroy(top *p)
    {
        delete p;
    }
   ```

- **New işleci ve delete işleci aşırı** Derleyici önceki sürümlerinden izin üyesi olmayan `operator new` ve üye olmayan `operator delete` statik bildirilmesi ve ad alanları genel ad alanı dışında bildirilmesi için.  Bu eski davranış oluşturulan program çağrılmayan risk `new` veya `delete` sessiz hatalı çalışma zamanı davranışını elde edilen Programcı hedeflenen işleci uygulama. Derleyici artık bu şekilde yazılan kod kabul eder ve bunun yerine derleyici hatası C2323 sorunları.

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

      Additionally, although the compiler doesn't give a specific diagnostic, inline operator new is considered ill-formed.

- **Çağırma ' işleci *türü*() ' (kullanıcı tanımlı dönüştürme) sınıfı olmayan türlerinde** izin Derleyici önceki sürümlerini ' işleci *türü*() ' sınıfı olmayan türlerinde sessizce sırasında çağrılabilir Bunu yoksayılıyor. Bu eski davranış sessiz hatalı kod oluşturmasına, öngörülemeyen çalışma zamanı davranışını kaynaklanan riski oluşturulmuş. Derleyici artık bu şekilde yazılan kod kabul eder ve bunun yerine derleyici hatası C2228 sorunları.

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

- **Yedek typename ayrıntılandırılmış tür tanımlayıcıları olarak** izin Derleyici önceki sürümlerini `typename` ayrıntılandırılmış tür tanımlayıcıları; bu şekilde yazılan kod anlamsal olarak geçersiz. Derleyici artık bu şekilde yazılan kod kabul eder ve bunun yerine derleyici hatası C3406 sorunları.

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

- **Türü bir başlatıcı listesinden dizi kesintisi** Derleyici önceki sürümlerinden bir başlatıcı listesinden dizi türü kesintisi desteği. Derleyici şimdi türü kesintisi bu biçimini destekler ve sonuç olarak, başlatıcı listeleri kullanarak işlev şablonları çağrıları şimdi belirsiz olabilir veya farklı bir aşırı daha Derleyici önceki sürümlerde seçilmesi. Bu sorunları gidermek için program şimdi açıkça Programcı hedeflenen aşırı belirtmeniz gerekir.

   Bu yeni davranış eşit geçmiş aday olarak kadar iyi ek bir aday dikkate alınması gereken aşırı yükleme çözünürlüğü neden olduğunda çağrısı belirsiz haline gelir ve derleyici derleyici hatası C2668 sonuç olarak yayımlar.

   ```Output
    error C2668: 'function' : ambiguous call to overloaded function.
   ```

   Örnek 1: Aşırı yüklenmiş işlevi (önce) belirsiz çağrısı

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

   Örnek 1: aşırı yüklenmiş işlevi (sonra) belirsiz çağrısı

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

   Bu yeni davranış çağrı belirsizliğe yer bırakmadan yeni adayı sürümüne çözümler geçmiş adayı daha iyi bir eşleşme olan ek bir aday dikkate alınması gereken aşırı yükleme çözünürlüğü neden olduğunda program davranışı bir değişiklik neden büyük olasılıkla farklıdır Programcı amaçlar.

   Örnek 2: aşırı çözünürlük (önce) değiştirme

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

   Örnek 2: aşırı çözünürlük (sonra) değiştirme

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

- **Switch deyimi uyarıları geri** derleyici bir önceki sürümü kaldırılıyor önceden varolan uyarılarla ilgili `switch` deyimleri; bunlar uyarılar şimdi geri yüklendi. Derleyici şimdi geri yüklenen uyarıları sorunları ve belirli durumlarda (varsayılan durumu dahil) ilgili uyarılar şimdi soruna neden olan durum içeren satırı yerine switch deyimi son satırının verilir. Sonuç olarak bu uyarılar farklı satırlarındaki geçmişte şimdi veren, uyarıları daha önce gizlenen kullanarak `#pragma warning(disable:####)` tasarlandığı gibi artık gizlenen. Bu uyarılar tasarlandığı gibi gizlemek için bu taşımak gerekli olabilir `#pragma warning(disable:####)` ilk olası sorunlu çalışması üstüne bir çizgi yönergesi. Geri yüklenen uyarılar verilmiştir.

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

   (Önce) C4063 örneği

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

   (Sonra) C4063 örneği

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

- **#include: üst dizini tanımlayıcısı kullanın '..' pathname içinde** (yalnızca wln /WX etkiler)

     Derleyici önceki sürümlerini üst dizini belirleyici kullanımını algılamadı '..' yol adı olarak `#include` yönergeleri. Bu şekilde yazılan kod genellikle yanlış proje göreli yollar kullanılarak dışında projesi mevcut üstbilgileri dahil etmek için tasarlanmıştır. Bu eski davranış program hedeflenen Programcı farklı bir kaynak dosyasından dahil ederek derlenmiş veya bu göreli yollar diğer yapı ortamlar için taşınabilir olmayacaktır riski oluşturulur. Derleyici şimdi algılar ve bu şekilde yazılan kod Programcı bildirir ve etkinleştirilirse isteğe bağlı bir derleyici C4464, uyarı verir.

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

   Derleyici belirli bir tanılama sağlamaz, ancak buna ek olarak, ayrıca, üst dizini belirleyici öneririz "..." Not projenizin içeren dizinleri belirtmek için kullanılmalıdır.

- **#pragma optimize() genişletir üstbilgi dosyası sonunun** (yalnızca wln /WX etkiler)

   Derleyici önceki sürümlerinde bulunan bir çeviri birimi bulunan bir üstbilgi dosyası kaçış iyileştirme bayrağı ayarlarında yapılan değişiklikler algılamadı. Derleyici şimdi algılar ve bu şekilde yazılan kod Programcı bildirir ve C4426 sorunlu konumda uyarı isteğe bağlı bir derleyici sorunları `#include`, etkinleştirilirse. En iyi duruma getirme bayraklarla değişiklikleri çakışma derleyici komut satırı bağımsız değişkenleri olarak ayarlarsanız bu uyarı yalnızca görüntülenir.

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

- **#Pragma warning(push) eşleşmeyen** ve **#pragma warning(pop)** (yalnızca wln /WX etkiler)

   Derleyici önceki sürümlerini algılamadı `#pragma warning(push)` durumu değişir ile eşleştirilmiş `#pragma warning(pop)` durum nadiren kullanılmaya farklı bir kaynak dosyasındaki değişiklikleri. Bu eski davranışı bir risk, oluşturulan program hazırlanan Programcı etkin uyarıları büyük olasılıkla sessiz hatalı çalışma zamanı davranışını elde edilen farklı bir dizi derlenecek. Derleyici şimdi algılar ve bu şekilde yazılan kod Programcı bildirir ve eşleşen konumda C5031 uyarı isteğe bağlı bir derleyici sorunları `#pragma warning(pop)`, etkinleştirilirse. Bu uyarı, karşılık gelen #pragma warning(push) konumunu başvuran Not dahildir.

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

   Bu şekilde yazılan kod bazen seyrek olsa kasıtlıdır. Bu şekilde yazılan kod değişikliklere hassas `#include` mümkün olduğunda, kaynak kodu dosyaları kendi içinde bulunan bir biçimde uyarı durumunu yönetme öneririz; sırası.

- **Eşleşmeyen #pragma warning(push)** derleyici (yalnızca etkiler wln /WX) önceki sürümlerinden algılamadı eşleşmeyen `#pragma warning(push)` durum değişiklikleri çeviri birim sonunda. Derleyici şimdi algılar ve bu şekilde yazılan kod Programcı bildirir ve C5032 eşleşmeyen #pragma warning(push) konumda uyarı isteğe bağlı bir derleyici etkinleştirilirse sorunları. Bu uyarı, yalnızca çeviri biriminde hiç derleme hatası olması durumunda görüntülenir.

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

- **Ek uyarı sonucu olarak geliştirilmiş #pragma uyarı durumu izleme verilen** Derleyici önceki sürümlerinden iyi sorunu için yeterince uyarı yönelik tüm uyarıları durum değişiklikleri #pragma izlenir. Bu davranış, uyarıları etkin hedeflenen Programcı farklı durumlarda atlanması, belirli bir risk oluşturulur. Derleyici şimdi #pragma uyarısı durumunu daha yerine--#pragma uyarısı durum değişiklikleri şablonları içinde--özellikle ilgili izler ve isteğe bağlı olarak istenmeyenkullanımlarınıbulunProgramcıyardımcıolmaküzeretasarlanmıştıryeniuyarılarC5031veC5032sorunları`#pragma warning(push)` ve `#pragma warning(pop)`.

   Sonucu olarak geliştirilmiş #pragma durumu değişiklik izleme, eskiden yanlış gizlenen uyarılar veya önceden misdiagnosed sorunlarıyla ilgili uyarılar uyarı artık verilebilir.

- **Geliştirilmiş ulaşılamaz kod tanımlaması** C++ Standart Kitaplığı değiştirir ve satır içi işlev çağrılarını Derleyici önceki sürümlerini üzerinden geliştirilmiş yeteneği belirli kod ulaşılamaz olduğunu kanıtlamak derleyici izin. Bu yeni davranış yeni ve daha sık uyarı C4720 örneklerini verilen sonuçlanabilir.

   ```Output
    warning C4720: unreachable code
   ```

   Çoğu durumda, bu uyarı, yalnızca iyileştirmeler etkinleştirilerek derlerken verilebilecek, bu yana iyileştirmeler satır içi daha işlev çağrıları, yedekli kod ortadan kaldırmak veya aksi halde belirli kod erişilemiyor belirlemek mümkün kılar. Biz uyarı C4720 yeni örneklerini try/catch blokları, kullanım için özellikle ilişkisi içinde sık gerçekleşen gözlenen [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True).

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

### <a name="VS_Update2"></a> Visual Studio 2015 güncelleştirme 2 uygunluk yenilikleri

- **Ek uyarıları ve hataları verilen kısmi ifade SFINAE desteği sonucunda** Derleyici önceki sürümlerinden ifadelerinin içinde belirli bir türde değil ayrıştırma `decltype` tanımlayıcıları ifade için destek eksikliği nedeniyle SFINAE. Bu eski davranış yanlış ve C++ Standart uygun değil. Derleyici şimdi bu deyimler ayrıştırır ve kısmi ifade SFINAE devam eden uygunluk geliştirmeleri nedeniyle desteği sahiptir. Sonuç olarak, derleyici uyarıları şimdi sorunları ve derleyici önceki sürümleri olmayan incelenemedi ifadelerinde hatalar bulundu.

   Bu yeni davranış zaman ayrıştırır bir `decltype` henüz bildirilmedi, bir tür derleyici içeren deyim derleyici hatası C2039 sonuç olarak verir.

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

   Bu yeni davranış zaman ayrıştırır bir `decltype` gerekli kullanımını eksik ifade `typename` bağımlı bir ad yazın, derleyici olduğunu belirtmek için anahtar sözcüğü derleyici C4346 derleyici hatası C2923 birlikte uyarı verir.

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

- `volatile` **üye değişkenleri önlemek örtük olarak tanımlanan oluşturucuları ve atama işleçleri** Derleyici önceki sürümlerinden izin olan bir sınıfı `volatile` varsayılan üye değişkenleri copy/move oluşturucular ve copy/move varsayılan Atama İşleçleri otomatik olarak oluşturulur. Bu eski davranış yanlış ve C++ Standart uygun değil. Derleyici artık otomatik olarak oluşturulan varsayılan uygulamaları bu işleçlerinin önleyen volatile üye değişkenleri Önemsiz olmayan yapım ve atama işleçleri sahip olan bir sınıfı göz önünde bulundurur.  Böyle bir sınıfın UNION (veya bir sınıf içinde anonim bir birleşimi) bir üyesi olduğunda, copy/move oluşturucuları ve kopya/taşıma atama işleçleri UNION (veya unonymous UNION içeren sınıf) örtük olarak silindi olarak tanımlanır. Oluşturmak veya bunları açıkça tanımlamadan UNION (veya anonim UNION içeren sınıf) kopyalamak çalışırken bir hata derleyici sorunları derleyici hatası C2280 sonucunda ise.

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

- **Statik üye işlevleri MS niteleyicileri desteklemez.** Visual C++ 2015 önceki sürümlerini MS niteleyicileri sağlamak statik üye işlevleri izin verilir. Visual C++ 2015 ve Visual C++ 2015 güncelleştirme 1'teki bir gerileme nedeniyle bu davranışı değildir; Visual C++ 2013 ve Visual C++'ın önceki sürümlerinde bu şekilde yazılan kod reddeder. Visual C++ 2015 ve Visual C++ 2015 güncelleştirme 1 davranışını yanlış ve standart C++ için uygun değil.  Visual Studio 2015 güncelleştirme 2 Bu şekilde yazılan kod reddeder ve bunun yerine derleyici hatası C2511 verir.

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

- **Enum ileriye dönük bildirimi WinRT kodu izin verilmeyen** (/ZW yalnızca etkiler) Windows çalışma zamanı (WinRT) izin vermediği için derlenmiş kod `enum` yönetilen C++ kodu için .net derlendiğinde İleri, benzer şekilde belirtilecek türleri Framework / CLR derleyici anahtar kullanılarak. Bu davranış olduğu numaralandırma boyutu her zaman bilinir ve doğru şekilde WinRT türü sisteme öngörülen sağlar. Derleyici bu şekilde yazılan kod reddeder ve derleyici hatası C2599 derleyici hatası C3197 birlikte verir.

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

- **Aşırı yüklenmiş üye olmayan işleci yeni ve delete işleci bildirilmemiş satır içi** (düzey 1 (/ W1) üzerinde tarafından-varsayılan) derleyici önceki sürümleri olmayan sorun bir uyarı satır içi yeni üye olmayan işleci ve işleci silme işlevleri bildirirken . Bu şekilde yazılan kodu bozuk biçimli (tanılama gerekli) ve kaynaklanan sorunlar yeni eşleşmeyen ve tanılamak zor olabilir (özellikle boyutlu ayırmayı kaldırma ile birlikte kullanıldığında) işleçleri silmek bellek neden olabilir.   Derleyici şimdi derleyici C4595 bu şekilde yazılan kod tanımlamaya yardımcı olmak üzere Uyarı yayınlar.

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

   Bu şekilde yazılan kod çözme işleç tanımları üstbilgi dosyası dışında ve karşılık gelen bir kaynak dosyasına taşınmasına gerektirebilir.

### <a name="VS_Update3"></a> Visual Studio 2015 güncelleştirme 3 uygunluk yenilikleri

- **Std::is_convertable otomatik atanmasını artık algılar** (standart kitaplığı) önceki sürümlerini `std::is_convertable` türü ayırdedici nitelik kopya kurucusu silindiğinde bir sınıf türünün otomatik atanmasını veya özel doğru algılamadı. Şimdi, `std::is_convertable<>::value` doğru bir şekilde ayarlamak `false` bir sınıf türü silindiğinde veya özel kopya Oluşturucu ile uygulandığında.

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

   Visual C++ önceki sürümlerinde, çünkü bu örnek altındaki statik onaylar geçirmek `std::is_convertable<>::value` yanlış ayarlandı `true`. Şimdi, `std::is_convertable<>::value` doğru şekilde ayarlandığından `false`, statik onaylar başarısız olmasına neden olur.

- **Varsayılan veya önemsiz kopya silinir ve oluşturucular saygı erişim tanımlayıcıları taşımak** Derleyici önceki sürümlerinden değil varsayılan veya silinen Önemsiz kopyasının erişim belirticisi denetleyin ve bunları çağrılmasına izin vermeden önce oluşturucular taşıyın. Bu eski davranış yanlış ve C++ Standart uygun değil. Bazı durumlarda, bu eski davranış sessiz hatalı kod oluşturmasına, öngörülemeyen çalışma zamanı davranışını kaynaklanan riski oluşturulur. Derleyici şimdi varsayılan veya silinen Önemsiz kopyasının erişim belirticisi denetler ve onu çağrılabilir olup olmadığını ve değilse, C2248 sonucunda uyarı sorunları derleyici olmadığını belirlemek için oluşturucular taşıyın.

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

- **Öznitelik atanmış ATL kodu desteğini kullanımdan** (düzey 1 (/ W1) üzerinde tarafından-varsayılan) desteklenen Derleyici önceki sürümlerini öznitelikli ATL kodu. Öznitelik atanmış ATL desteğini kaldırmanın sonraki aşaması olarak, kod [Visual C++ 2008'de başlangıcından](https://msdn.microsoft.com/library/bb384632\(v=vs.90\).aspx), öznitelik atanmış ATL kodu kullanım dışı bırakıldı. Derleyici şimdi derleyici C4467 bu tür kullanım dışı kodu tanımlamaya yardımcı olmak üzere Uyarı yayınlar.

   ```Output
    warning C4467: Usage of ATL attributes is deprecated
   ```

   Destek derleyiciden kaldırılana kadar atanmış ATL kodu kullanarak devam etmek istiyorsanız, bu uyarı ileterek devre dışı bırakabilirsiniz `/Wv:18` veya `/wd4467` komut satırı bağımsız değişkenleri derleyici ya da ekleyerek `#pragma warning(disable:4467)` kaynak kodunuzdaki.

   Örnek 1 (önce)

   ```cpp
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
    class A {};
   ```

   Örnek 1 (sonra)

   ```cpp
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};

   ```

   Bazen, veya ihtiyacınız olabilir bir IDL oluşturmak istediğiniz dosya kullanmaktan kaçının ATL öznitelikler, aşağıdaki örnek kod olduğu gibi kullanım dışı

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

   Önce *.idl dosyası oluşturun; oluşturulan vc140.idl dosyası elde etmek için kullanılabilir bir \*arabirimleri ve ek açıklamaları içeren .idl dosyası.

   Ardından, bir MIDL adımı C++ Arabirim tanımları oluşturulan emin olmak için derleme ekleyin.

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

   Ardından, aşağıdaki örnek kod olduğu gibi uygulama dosyasındaki doğrudan ATL kullanın.

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

- **Önceden Derlenmiş Üstbilgi (PCH) dosyaları ve uyumsuzluğu # yönergeleri include** derleyici (yalnızca etkiler wln /WX) önceki sürümlerinden kabul eşleşmeyen `#include` arasındaki kaynak dosyalarında yönergeleri `-Yc` ve `-Yu` önceden derlenmiş üst bilgi (PCH) dosyaları kullanırken derlemeleri. Bu şekilde yazılan kod artık derleyici tarafından kabul edilir.   Tanımlamaya yardımcı olmak üzere CC4598 uyarı sorunları derleyici eşleşmeyen artık derleyici `#include` PCH dosyalarını kullanırken yönergeleri.

   ```Output
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position
   ```

   (Önce) örnek:

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

- **Önceden Derlenmiş Üstbilgi (PCH) dosyaları ve uyumsuzluğu içeren dizinler** eşleşmeyen (yalnızca etkiler wln /WX) önceki sürümlerini kabul derleyici içeren dizin (`-I`) arasındakiderleyicikomutsatırıbağımsızdeğişkenleri`-Yc`ve `-Yu` kullanırken derlemeleri önceden derlenmiş üstbilgi (PCH) dosyaları. Bu şekilde yazılan kod artık derleyici tarafından kabul edilir.   Tanımlamaya yardımcı olmak üzere CC4599 uyarı sorunları derleyici eşleşmeyen artık derleyici içeren dizin (`-I`) PCH dosyalarını kullanırken komut satırı bağımsız değişkenleri.

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

## <a name="whats-new-for-c-in-visual-studio-2013"></a>Visual Studio 2013'te C++ yenilikler

### <a name="improved-iso-cc-standards-support"></a>Geliştirilmiş ISO C/C++ standartları desteği

#### <a name="compiler"></a>Derleyici

Microsoft Visual C++ derleyicisi bu ISO C ++ 11 dil özellikleri destekler:

- Şablon şablonları varsayılan bağımsız değişkenleri işlevi.
- Oluşturucular için temsilci seçme
- Açık dönüşüm işleçleri.
- Başlatıcı Listeleri ve tek düzen başlatma.
- Ham dize değişmez değerleri.
- Variadic şablonları.
- Diğer ad şablonları.
- Silinen işlevler.
- Statik olmayan veri üyesi başlatıcıları (NSDMIs).
- Varsayılan işlevler. *
- Bu ISO C99 dil özellikleri destekler:
- _Bool
- Bileşik değişmez değerler.
- Belirlenen başlatıcıları.
- Kod bildirimlerle karıştırma.
- Dize değişmez değer dönüştürme değiştirilebilir değerlere yeni derleyici seçeneğini kullanarak izin verilmeyen **/ZC: strictstrings**. C ++ 98, dize değişmez değerleri dönüştürmeye char\* (ve geniş, değişmez değerleri wchar_t için dize\*) kullanımdan kaldırılmıştır. C ++ 11'de, dönüştürme tamamen kaldırıldı. Derleyici kesinlikle standardına uygun ancak yerine sağlar **/ZC: strictstrings** dönüştürme denetimini seçeneği. Varsayılan olarak, seçeneği kapalıdır. Bu seçenek hata ayıklama modunda kullanırken, STL derlenmez olduğunu unutmayın.
- rvalue/lvalue başvuru atamaları. Rvalue başvuru ile C ++ 11 açıkça lvalues ve rvalues arasında ayırt edebilirsiniz. Daha önce derleyici bu belirli atama senaryolarda sağlamadı. Yeni bir derleme seçeneği **/Zc:rvalueCast**, C++ dili çalışma Paper(see section 5.4, [expr.cast]/1) ile derleyici uyumluluğu sağlamak için eklendi. Bu seçenek belirtilmediğinde varsayılan Visual Studio 2012 ile aynı davranıştır.
  - Not: kullanarak varsayılan işlevler için = varsayılan memberwise taşıma oluşturucuları istek ve taşıma atama işleçleri desteklenmiyor.

### <a name="c99-libraries"></a>C99 kitaplıkları

Bu üst bilgileri eksik işlev bildirimleri ve uygulamaları eklenir: math.h, ctype.h, wctype.h, stdio.h, stdlib.h ve wchar.h. Ayrıca eklenen yeni üstbilgileri complex.h stdbool.h, fenv.h ve inttypes.h ve uygulamalarının tüm işlevleri için bunları bildirilen ' dir. Yeni C++ kapsayıcı üstbilgileri (ccomplex, cfenv, cinttypes, ctgmath) vardır ve diğerleri sayısı (ccomplex, cctype, clocale, cmath, cstdint, cstdio, cstring, cwchar ve cwctype) güncelleştirildi.

### <a name="standard-template-library"></a>Standart Şablon Kitaplığı

C ++ 11 açık dönüşüm işleçleri, başlatıcı listeleri, kapsamlı numaralandırmaları ve variadic şablonları için destek.
Tüm kapsayıcıları şimdi C ++ 11 hassas öğesi gereksinimlerini destekler.
Bu C ++ 14 özellikleri için destek:

- "Saydam işleci functors" <>, büyük <> yanı sıra <>, daha az <> ve benzeri çarpar.
- make_unique<T>(args...) ve make_unique < T [] > (n)
- cbegin()/cend(), rbegin()/rend() ve crbegin()/crend() olmayan üye işlevleri.
- \<atomik > çok sayıda performans geliştirmeleri aldı.
- \<type_traits > ana sabitlemeyi ve kod düzeltmeleri aldı.

### <a name="breaking-changes"></a>Yeni Değişiklikler

Böylece C ++ 11'e uyan ve Visual Studio 2013'te Visual C++'ta doğru derler Bu geliştirilmiş destek ISO C/C++ standartları için var olan kodu değişiklikler gerektirebilir.

### <a name="visual-c-library-enhancements"></a>Visual C++ Kitaplık geliştirmeleri

- C++ REST SDK eklenir. Modern C++ uygulaması REST hizmetleri vardır.
- C++ AMP doku desteği geliştirilmiştir. Şimdi mipmaps ve yeni örnekleme modları için destek de içerir.
- PPL görevleri birden çok zamanlama teknolojileri ve zaman uyumsuz hata ayıklama destekler. Yeni API PPL görevlerde normal sonuçları ve özel durumları oluşturulmasını sağlamak.

### <a name="c-application-performance"></a>C++ uygulama performansı

- Otomatik vektör hale getirici şimdi tanır ve daha fazla C++ desenleri kodunuzu daha hızlı çalışır hale getirmek için en iyi duruma getirir.
- ARM platform ve Atom mikro mimarisi kod kalitesini geliştirmeleri.
- çağırma kuralı __vectorcall eklenir. Vektör tür bağımsız değişkenleri vektör kayıtları kullanmak için __vectorcall çağırma kullanarak geçirin.
- Yeni bağlayıcı seçenekleri. /Gw (derleyici) ve /Gy (derleyici) anahtarları daha yalın ikili dosyaları üretmek Bağlayıcısı iyileştirmeleri etkinleştirin.
- C++ AMP paylaşılan bellek desteği veya verileri CPU ve GPU'ya arasında kopyalama ortadan kaldırmak için.

### <a name="profile-guided-optimization-pgo-enhancements"></a>Profil temelli iyileştirme (PGO) geliştirmeleri

- PGO kullanarak iyileştirilmiş uygulamalar çalışma kümesi azalmasına gelen performans geliştirmeleri.
- Yeni PGO için Windows çalışma zamanı uygulama geliştirme.

### <a name="windows-runtime-app-development-support"></a>Windows çalışma zamanı uygulama geliştirme desteği

- **Destek için Kutulu türleri içinde değerini yapılar.** Null olabilir alanlarını kullanarak değer türleri artık tanımlayabilirsiniz — Örneğin, IBox\<int > ^ int aksine Bu alanların bir değere sahip veya nullptr eşit olduğunu anlamına gelir.
- **Daha zengin özel durum bilgileri.** C + +/ CX yakalanmasını ve zengin özel durum bilgilerini yayılmasını uygulama ikili arabirimi (ABI); sağlayan yeni Windows hata modelini destekler Bu çağrı yığınları ve özel ileti dizeleri içerir.
- **Nesne:: ToString() sanal sunulmuştur.** Kullanıcı tanımlı Windows çalışma zamanı ref türlerinde ToString artık geçersiz kılabilirsiniz.
- **Kullanım dışı API'leri için destek.** Genel Windows çalışma zamanı API'leri artık kullanım dışı ve yapı uyarı olarak görünen özel bir ileti verilen işaretlenebilir ve Geçiş Kılavuzu sağlayabilir.
- **Hata ayıklayıcı geliştirmeleri.** Yerel/JavaScript birlikte çalışma hata ayıklama, Windows çalışma zamanı özel durumu tanı ve zaman uyumsuz kod (Windows çalışma zamanı ve PPL) hata ayıklama desteği.
  - Not: C++ özgü özellikler ve bu bölümde açıklanan geliştirmelerin yanı sıra diğer geliştirmeler Visual Studio'da de daha iyi Windows çalışma zamanı uygulamaları yazmanıza yardımcı olabilir.

### <a name="diagnostics-enhancements"></a>Tanılama geliştirmeleri

- Hata ayıklayıcı geliştirmeleri. Zaman uyumsuz hata ayıklama ve sadece kendi kodumu hata ayıklama desteği.
- Çözümleme kategorisi kodu. Bulma ve kod kusurları gidermenize yardımcı olması için bu kodu Çözümleyicisi kategorilere ayrılmış çıktısını artık görüntüleyebilirsiniz.
- XAML tanılama. UI yanıtlama hızı şimdi tanılayabilirsiniz ve XAML pil kullanım sorunları.
- Grafikler ve hata ayıklama iyileştirmeleri GPU.
- Uzak yakalama ve gerçek aygıtları kayıttan yürütme.
- Eşzamanlı C++ AMP ve CPU hata ayıklama.
- Gelişmiş C++ AMP çalışma zamanı tanılama.
- İşlem HLSL gölgelendirici izleme hata ayıklama.

### <a name="3-d-graphics-enhancements"></a>3B grafik geliştirmeleri

- Görüntü içerik ardışık düzen önceden çarpılan alfa desteği DDS biçimlendirin.
- Görüntü Düzenleyicisi işleme için dahili olarak önceden çarpılan alfa kullanır ve böylece koyu haleleri gibi işleme yapılarını ortadan kaldırır.
- Yansıma ve Model düzenleyicileri. Kullanıcı tanımlı filtresi oluşturma görüntü Düzenleyicisi ve Model Düzenleyicisinde gölgelendirici Tasarımcısı'nda artık desteklenmektedir.

### <a name="ide-and-productivity"></a>IDE ve üretkenlik

**Kod biçimlendirme geliştirilmiş**. C++ kodunuzu daha fazla biçimlendirme ayarlarını uygulayabilirsiniz. Bu ayarları kullanarak yeni satır yerleşimini küme ayraçları ve anahtar sözcükler, girinti, aralık ve satır kaydırma kontrol edebilirsiniz. Kod, ifadeler ve blokları tamamladığınızda ve kodu bir dosyaya yapıştırın, otomatik olarak biçimlendirilir.

**Küme parantezi tamamlama.** C++ kodu şimdi otomatik-bu açılış karakterler karşılık kapanış karakterleri gerçekleştirir:

- {(kaşlı ayraç)
- [(köşeli ayraç)
- ((parantezler)
- ' (tek tırnak)
- "(çift tırnak)

**Ek C++ otomatik tamamlama özellikleri.**

- Sınıf türleri için noktalı virgül ekler.
- Ham dize değişmez değerleri için parantez tamamlar.
- Çok satırlı yorumlar tamamlandıktan (/ * * /)

**Tüm başvuruları Bul** artık otomatik olarak çözer ve metinsel eşleşmeleri listesinde görüntüledikten sonra arka planda başvuruları filtreler.

**Bağlam tabanlı üye listesini filtreleme.** Erişilemez üyeleri dışında IntelliSense üye listeleri filtrelenir. Örneğin, özel üyelerin türü uygulayan kod değiştirmekte olduğunuz sürece üye listesinde görüntülenmez. Üye listesi açıkken bir düzeyde filtreleme kaldırmak için Ctrl + J tuşlarına basabilirsiniz (yalnızca geçerli üye listesi penceresi için geçerlidir). Yeniden metinsel filtreleme kaldırın ve her üye göstermek için Ctrl + J tuşlarına basabilirsiniz.

**Kaydırma parametre yardımcı olur.** Araç ipucunda yerine yalnızca bir rastgele imza gösteren ve güncelleştirme değil geçerli bağlamına dayalı değişiklikleri gerçekten yazdığınız, parametreleri sayısına göre şimdi parametre Yardım görüntülenen işlev imzası. Parametre de doğru şekilde iç içe geçmiş işlevleri zaman görüntüleneceğini işlevleri Yardımı.

**İki durumlu üstbilgi/kod dosyası.** Kısayol menüsü veya bir klavye kısayolu bir komut kullanarak bir başlık ve karşılık gelen kod dosyası arasında şimdi çevirebilirsiniz.

**Yeniden boyutlandırılabilir C++ projesi Özellikler penceresi**

**Otomatik olarak oluşturulmasını olay işleyici kodu C + +/ CX ve C + +/ CLI.**  Ne zaman yazdığınız olay işleyicisi bir C + eklemek için kod +/ CX veya C + +/ CLI kod dosyası Düzenleyicisi'ni temsilci örneği ve olay işleyicisi tanımı otomatik olarak oluşturulmasına neden olabilir. Olay işleyici kodu otomatik olarak oluşturulan kullanırken bir araç ipucu penceresi görüntülenir.

**DPI tanıma geliştirme.** Şimdi DPI tanıma ayar uygulama bildirim dosyası için "Başına İzleyicisi yüksek DPI haberdar" ayarını destekler.

**Daha hızlı yapılandırma geçişi.** Büyük uygulamalar için yapılandırmaları değiştirme — özellikle sonraki işlemleri geçiş — çok daha hızlı bir şekilde yürütün.

**Zamanı verimliliği oluşturun.** Çok sayıda en iyi duruma getirme ve çok çekirdekli kullanımı derlemeleri özellikle büyük projeler için daha hızlı hale getirir. Artımlı derlemeler C++ WinMD başvuran C++ uygulamaları için de çok daha hızlıdır.

## <a name="whats-new-for-c-in-visual-studio-2012"></a>C++ Visual Studio 2012'deki yenilikler

### <a name="improved-c11-standards-support"></a>Geliştirilmiş C ++ 11 standartları desteği

#### <a name="standard-template-library"></a>Standart Şablon Kitaplığı

- Yeni STL üstbilgileri desteği: \<atomik >, \<chrono >, \<condition_variable >, \<filesystem >, \<gelecekteki >, \<mutex >, \<oranı >, ve \< iş parçacığı >.
- Bellek kaynağı kullanımını en iyi duruma getirmek için artık daha küçük kapsayıcılardır. Örneğin, x86 varsayılan ayarlarla Toolkit, std::vector 16 bayt Visual Studio 2010'dan Visual Studio 2012'de 12 bayt küçültülebilir ve std::map 16 bayt Visual Studio 2010'dan Visual Studio 2012'de 8 bayt küçültülebilir.
- İzin verilen olarak C ++ 11 standart tarafından gerekli değildir ancak, KORKUTUCU yineleyiciler uygulanmıştır.

#### <a name="other-c11-enhancements"></a>Diğer C ++ 11 geliştirmeleri

- Aralık tabanlı döngüler için. Diziler, STL kapsayıcıları ve Windows çalışma zamanı form için koleksiyonlarda çalışma daha sağlam döngüler yazabilirsiniz (için aralığı-bildirim: ifadesi). Bu, çekirdek dil desteği parçasıdır.
- Bir boş lambda introducer [] ile başlayan ve hiçbir yerel değişkenler yakalama kod bloklarını olan durum bilgisiz Lambda'lar, işlev işaretçileri C ++ 11 standart gerektirdiği için örtük olarak dönüştürülebilir.
- Kapsamlı numaralandırmaları destekler. C++ enum sınıfı enum anahtar artık desteklenmektedir. Aşağıdaki kod, nasıl bu enum anahtar önceki enum davranışından farklıdır gösterir.

   ```cpp
enum class Element { Hydrogen, Helium, Lithium, Beryllium };
void func1(Element e);
func1(Hydrogen); // error C2065: 'Hydrogen' : undeclared identifier
func1(Element::Helium); // OK
   ```

### <a name="windows-runtime-app-development-support"></a>Windows çalışma zamanı uygulama geliştirme desteği

- **Yerel XAML tabanlı UI modeli**. Windows çalışma zamanı uygulamaları için yeni yerel XAML tabanlı UI modelini kullanabilirsiniz.
- **Visual C++ bileşen uzantıları**. Bu uzantılar Windows çalışma zamanı uygulamaları gerekli bir parçası olan Windows çalışma zamanı nesnelerinin tüketim basitleştirin. Daha fazla bilgi için bkz: [C++ kullanarak yol haritası için Windows çalışma zamanı uygulamaları](../windows/universal-windows-apps-cpp.md) ve [Visual C++ Dil Başvurusu (C + +/ CX)](../cppcx/visual-c-language-reference-c-cx.md)
- **DirectX oyunlar**. Windows çalışma zamanı uygulamaları için yeni DirectX desteğini kullanarak kurmadığını oyunlar geliştirebilirsiniz.
- **XAML/DirectX birlikte çalışabilirliği**. XAML ve DirectX şimdi kullanan Windows çalışma zamanı uygulamaları verimli bir şekilde onunla birlikte çalışamaz.
- **Windows çalışma zamanı bileşeni DLL geliştirme**. Bileşen DLL geliştirme Windows çalışma zamanı ortamı Genişletilebilir hale getirir.

### <a name="compiler-and-linker"></a>Derleyici ve bağlayıcı

- **Otomatik vektör hale getirici**. Döngüler, kodunuzda derleyici analiz eder ve vektör kullanma yönergeleri kaydeder ve tüm modern işlemciler mevcut yönergeleri mümkün yayar yerdir. Bu, daha hızlı çalışır döngüler hale getirir. (İşlemci yönergeleri için Streaming SIMD uzantıları SSE bilinir). Etkinleştirmek veya otomatik olarak uygulandığından bu en iyi duruma getirme isteği gerekmez.
- **Otomatik paralel hale getirici**. Derleyici kodunuzda döngüler çözümleyebilir ve birden çok çekirdek veya işlemci hesaplamaları yayılan yönergeleri yayma. Bu daha hızlı çalışır döngüler yapabilirsiniz. Varsayılan olarak etkin olmadığından bu en iyi duruma getirme istemeniz gerekir. Çoğu durumda, kodunuzu hemen parallelized istediğiniz döngüler önce #pragma loop(hint_parallel(N)) dahil yardımcı olabilir.
- Böylece hesaplamalar birden çok çekirdek arasında yayılır ve her çekirdek kod vektör kayıtlarını kullanır birlikte otomatik vektör yapıcı ve otomatik paralel hale getirici çalışabilirsiniz.

### <a name="new-in-visual-studio-2012-update-1"></a>Yeni Visual Studio 2012 Güncelleştirmesi 1

C++ kodunuzu derlerken Windows XP hedefleyin.
Visual C++ derleyicisi ve hedef Windows XP ve Windows Server 2003 kitaplıkları kullanabilirsiniz.

#### <a name="parallel-programming-support"></a>Paralel Programlama Desteği

##### <a name="c-accelerated-massive-parallelism-amp"></a>C++ hızlandırılmış yoğun paralellik (AMP)

C++ AMP GPU ayrı grafik kart üzerinde normalde mevcut verileri paralel donanım yararlanarak, C++ kod yürütmeyi hızlandırır. Çok boyutlu diziler, dizin oluşturma, bellek aktarımı, döşeme ve matematiksel işlev kitaplığının C++ AMP programlama modeli içerir. C++ AMP dil uzantıları ve derleyici kısıtlamaları kullanarak nasıl veri İşlemcisinden GPU ve geri taşınır kontrol edebilirsiniz.

**Hata ayıklama.** Hata ayıklama GPU hedeflemek için C++ AMP kullanan uygulamalar için yalnızca diğer C++ uygulamaları için hata ayıklama gibi deneyimidir. Bu, daha önce bahsedilen eklemeleri hata ayıklama yeni paralel içerir.

**Profil oluşturma.** Var. Şimdi C++ AMP ve diğer Direct3D tabanlı programlama modelleri göre GPU etkinliği desteği profil.

#### <a name="general-parallel-programming-enhancements"></a>Genel Paralel Programlama geliştirmeleri

Çok çekirdekli ve çok çekirdekli mimarileri için taşıma donanım ile geliştiriciler tek çekirdek saati hızlarını gitgide artan artık güvenebilirsiniz. Eşzamanlılık Çalışma zamanı desteği programlama paralel geliştiricilerin bu yeni mimariler yararlanmak olanak sağlar.
Visual Studio 2010'da, güçlü C++ paralelleştirme kitaplıkları paralel Desen kitaplığı gibi sunulan, Gelişmiş veri akışı ardışık düzenleri ifade ederek eşzamanlılık yararlanmak özelliklerle birlikte. Visual Studio 2012'de bu kitaplıklar, geliştiriciler en çok gerek paralel desen için daha iyi performans, daha fazla denetim ve daha zengin destek sağlamak için genişletilmiştir. Teklifi derecesini artık içerir:

- Asynchrony ve devamlılıklar destekleyen bir zengin görev tabanlı programlama modeli.
- Paralel algoritmalar çatalı birleştirme paralellik (parallel_for, benzeşim, parallel_for_each, parallel_sort, parallel_reduce, parallel_transform parallel_for) destekler.
- Eşzamanlılık güvenli kapsayıcılar, priority_queue, kuyruk, vektör ve harita gibi veri yapılarını std iş parçacığı sürümleri sağlar.
- Zaman uyumsuz aracılar geliştiriciler doğal eşzamanlı birimlerine parçalayın veri akışı ardışık düzenleri ifade etmek için kullanabileceğiniz kitaplığı.
- Bu listedeki desenleri kesintisiz oluşumunu kolaylaştırmak için bir özelleştirilebilir Zamanlayıcı ve Kaynak Yöneticisi.

##### <a name="general-parallel-debugging-enhancements"></a>Hata ayıklama genel paralel geliştirmeleri

Tüm iş parçacıklarında ve işlemlerde ifade değerleri inceleyin ve sıralama ve filtreleme sonucuna gerçekleştirmek için Visual Studio 2012 Paralel Görevler penceresi ve Paralel Yığınlar penceresini ek olarak, yeni bir paralel Gözcü penceresi sunar. Penceresini genişletmek için kendi görselleştiriciler de kullanabilirsiniz ve tüm aracı windows yeni birden çok işlem desteğinden yararlanabilirsiniz.

### <a name="ide"></a>IDE

**Visual Studio şablonları destekler.** Artık Yazar C++ proje ve öğe şablonları için Visual Studio şablonları teknolojisi kullanabilirsiniz.

**Zaman uyumsuz çözüm yük.** Projeleri şimdi yüklenir zaman uyumsuz olarak — çözümü anahtar bölümleri ilk — böylece daha hızlı çalışmaya başlayabilirsiniz.

**Uzaktan hata ayıklama için otomatik dağıtım.** Visual C++'da uzaktan hata ayıklama için dosyaları dağıtımını basitleştirilmiştir. Proje bağlam menüsünde dağıtma seçeneği, uzak bilgisayara hata ayıklama yapılandırması özelliklerinde belirtilen dosyaları otomatik olarak kopyalar. Dosyaları uzak bilgisayara el ile kopyalayarak artık gerekli değildir.

**C + +/ CLI IntelliSense.** C + +/ CLI tam IntelliSense desteği artık sahiptir. IntelliSense özellikleri hızlı bilgi, parametre Yardım, listesi üyeleri ve otomatik tamamlama şimdi C + çalışma gibi +/ CLI. Ayrıca, bu belgede listelenen diğer IntelliSense ve IDE geliştirmelerini ayrıca C + iş +/ CLI.

**Daha zengin IntelliSense araç ipuçları.** C++ IntelliSense hızlı bilgi araç ipuçlarını daha zengin XML belgeleri yorumları stil bilgileri şimdi gösterir. Bir Kitaplığı'ndan bir API kullanıyorsanız — Örneğin, C++ AMP — XML belge açıklamaları olan sonra IntelliSense araç ipucu yalnızca bildirimi daha fazla bilgi gösterir. Ayrıca, kodunuzu XML belge açıklamaları varsa, IntelliSense araç ipuçları daha zengin bilgileri gösterir.

**C++ kodu oluşturur.** İskelet kodunu anahtarı, if-else, döngü ve diğer temel kod yapılardan listesi üyeleri aşağı açılan liste için kullanılabilir. Kodunuza eklemek ve ardından gerekli mantık doldurmak için listeden bir kod seçin. Kendi özel kullanım için kod parçalarını Düzenleyicisi'nde de oluşturabilirsiniz.

**Liste üyeleri geliştirmeleri.** Kod düzenleyicisine kodu yazarken listesi üyeleri açılan listesini otomatik olarak görünür. Sonuçları filtrelenir, böylece yazarken yalnızca ilgili üyeleri görüntülenir. Üye listesi tarafından kullanılan filtreleme mantığını türünü kontrol edebilirsiniz — altında metin düzenleyici Seçenekleri iletişim kutusunda, C/C++, Gelişmiş.

**Anlam renklendirme.** Şimdi türleri, numaralandırma, makroları ve diğer C++ belirteçleri renklendirme varsayılan olarak sahiptir.

**Başvuru vurgulama.** Bir simge şimdi seçerek simgenin geçerli dosyasında bulunan tüm örneklerini vurgular. Vurgulanan referansları arasında taşımak için Ctrl + Shift + Yukarı Ok veya Ctrl + Shift + aşağı ok tuşlarına basın. Bu özellik Seçenekleri iletişim kutusunda altında kapatabilirsiniz **metin düzenleyici, C/C++, Gelişmiş**.

### <a name="application-lifecycle-management-tools"></a>Uygulama yaşam döngüsü yönetimi araçları

#### <a name="static-code-analysis"></a>Statik kod çözümleme

C++ için statik çözümleme daha zengin hata bağlam bilgilerini, daha fazla çözümleme kurallarını sağlamak için güncelleştirilmiş ve daha iyi analiz sonuçlanır. Yeni Kod Analizi penceresinde iletileri anahtar sözcüğü, proje ve önem derecesine göre filtreleyebilirsiniz. Bir ileti penceresinde seçtiğinizde, ileti tetiklendiği kod satırında Kod düzenleyicisinde vurgulanır. Belirli C++ uyarıları, uyarı olarak müşteri adayları yürütme yolu Göster kaynak satırları ileti listeler; karar noktaları ve bu belirli bir yola alma nedenleri vurgulanır.
Kod çözümleme çoğu Visual Studio 2012 sürümlerinde bulunur. Professional, Premium ve Ultimate sürümleri tüm kuralları dahil edilir. Windows 8 ve Windows Phone için Express sürümlerinde, yalnızca en kritik uyarılar dahil edilir. Kod çözümleme için Web Express Edition'da bulunmaz.
Bazı bir kod çözümleme geliştirmeleri şunlardır:

- Yeni eşzamanlılık uyarıları, birden çok iş parçacıklı C/C++ programlarında doğru kilitleme uzmanlık alanlarından kullanarak sağlayarak eşzamanlılık hataları önlemenize yardımcı. Çözümleyici olası yarış durumları, kilit sipariş inversions, çağıran ve çağrılan kilitleme sözleşmenin ihlali, eşleşmeyen eşitleme işlemleri ve diğer eşzamanlılık hataları algılar.
- Kural kümeleri kullanarak Analiz çalıştırır kod uygulamak istediğiniz C++ kuralları belirtebilirsiniz.
- Kod Analizi penceresinde seçili uyarıyı bastırır pragma kaynak koda ekleyebilirsiniz.
- Bir işlev, bu BT bunları ve garanti hakkında kılar varsayımlar parametrelerinin nasıl kullandığını tanımlamak için yeni sürümü, Microsoft kaynak kodu ek açıklama dili (SAL) kullanarak statik kod analizi tamlığını ve doğruluğunu geliştirebilirsiniz tamamlandığında yapar.
- C++ projeleri için 64 bit destekler.

#### <a name="updated-unit-test-framework"></a>Güncelleştirilmiş Birim Test Çerçevesi

Yeni C++ birim test çerçevesi Visual Studio'da C++ birim testleri yazmak için kullanın. Yeni bir birim test projesi mevcut C++ çözümünüz için yeni proje iletişim kutusunda C++ birim testi projesi şablonu Visual C++ kategorisi altında bularak ekleyin. Birim testleri Unittest1.cpp dosyasında oluşturulan TEST_METHOD kod saplama yazmaya başlayın. Test kodu yazıldığında çözümü oluşturun. İstediğiniz testleri çalıştırmak için Görünüm, diğer pencereler, birim testi Explorer'ı seçerek bir birim testi Explorer penceresi açın ve ardından, test çalışması için kısayol menüsünde istediğiniz seçili test çalıştırma seçin. Tamamlandığında test çalıştırdıktan sonra test sonuçlarını ve ek yığın izleme bilgileri aynı penceresinde görüntüleyebilirsiniz.

#### <a name="architecture-dependency-graphs"></a>Mimari bağımlılık grafikleri

Kodunuzu daha iyi anlamak için artık ikili, ad alanı, sınıf için bağımlılık grafikleri oluşturmak ve bir çözümde dosyaları içerir. Menü çubuğunda mimarisi, bağımlılık grafiği oluşturmak ve ardından çözüm veya içerme dosyası için bir bağımlılık grafiği oluşturmak için seçin. Grafik oluşturma tamamlandığında, her düğüm genişleterek keşfetmek, düğümler arasında taşıyarak bağımlılık ilişkileri öğrenin ve kaynak kodu içeriği görüntüle bir düğüm için kısayol menüsünde seçerek göz atın. Bağımlılık grafiğinin *.cpp kaynak kodu dosyasının veya *.h üstbilgi dosyası için kısayol menüsünde içerme dosyaları oluşturmak için Oluştur grafiği, dosyaları içerir seçin.

#### <a name="architecture-explorer"></a>Mimari Gezgini

Mimari Gezgini'ni kullanarak, C++ çözüm, projeler veya dosyaları varlıkları keşfedebilirsiniz. Menü çubuğunda mimarisi, Windows, mimarisi Explorer'ı seçin. Örneğin, ilgilendiğiniz bir düğüm sınıfı görünüm seçebilirsiniz. Bu durumda, aracı pencerenin sağ tarafında ad alanlarının bir listesini genişletilir. Bir ad alanı seçerseniz, yeni bir sütun bu ad alanındaki sınıflar, yapılar ve numaralandırmaları listesini gösterir. Sütun en solundaki üzerinde başka bir sorgu başlatmak için geri dönün veya bu varlıkları keşfedin devam edebilirsiniz. Bkz: Bul kodu Mimari Gezgini ile.

#### <a name="code-coverage"></a>Kod Kapsamı

Kod kapsamı, çalışma zamanında dinamik olarak gereç ikili için güncelleştirilmiştir. Bu yapılandırma yükünü azaltır ve daha iyi performans sağlar. C++ uygulamaları için birim testleri gelen kod kapsamı verilerini de toplayabilirsiniz. C++ birim testleri oluşturduğunuzda, çözümünüz içinde testleri bulmak için Birim Test Gezgini kullanabilirsiniz. Birim testleri çalıştırma ve kod toplamak için kod kapsamını çözümleme birim testi Gezgini'nde, onlar için kapsamı verileri seçin. Kod Kapsamı Sonuçları penceresinde kod kapsamı sonuçlarını inceleyebilirsiniz — menü çubuğunda, Test, Windows, kod kapsamı sonuçları seçin.

## <a name="whats-new-for-c-in-visual-studio-2010"></a>Visual Studio 2010 c++ yenilikleri

### <a name="c-compiler-and-linker"></a>C++ derleyicisi ve bağlayıcı

**Auto anahtar sözcüğü.** Auto anahtar sözcüğü yeni bir amacı vardır. Auto anahtar sözcüğü varsayılan anlamını türü değişken bildirimi başlatma ifadesinden anlaşılabilen bir değişken bildirmek için kullanın. Yeni veya auto anahtar sözcüğü önceki anlamını /Zc:auto derleyici seçeneği çağırır.

**decltype tür belirteci.** Decltype tür belirteci belirtilen ifade türü döndürür. Decltype tür belirteci karmaşık ya da yalnızca derleyici için bilinen bir türe bildirmek için auto anahtar sözcüğü ile birlikte kullanın. Örneğin, bir şablon işlevi, dönüş türü, şablon bağımsız değişken türlerine bağlıdır bildirmek için birlikte kullanın. Ya da başka bir işlevi çağırır ve sonra çağrılan işlev dönüş türü döndüren bir şablon işlevi bildirin.

**Lambda ifadeleri.** Lambda işlevleri işlev gövdesi ancak ad var. Lambda işlevleri işlev işaretçileri ve işlev nesneleri en iyi özelliklerini birleştirin.
Bir şablon işlevi parametresi bir işlev nesnesi yerine ya da bir değişken, türü bildirmek için auto anahtar sözcüğü ile birlikte bir lambda olduğu gibi tek başına bir lambda işlevini kullanın.

**Rvalue başvuru.** Rvalue başvuru bildirimcisi (& &) bir rvalue başvuru bildirir. Kullandığınız bir rvalue başvuru sağlar, semantik ve daha verimli Oluşturucular, İşlevler ve şablonları yazmak için kusursuz iletme taşıyın.

**static_assert bildirimi.** Bir static_assert bildirimi derleme zamanında çalışma zamanında test diğer onaylama mekanizmaları aksine yazılım onaylama sınar. Onaylama başarısız olursa, derleme başarısız oluyor ve belirtilen hata iletisi görüntülenir.

**nullptr ve __nullptr anahtar sözcükler.** Visual C++ derleyicisi nullptr anahtar sözcüğü yönetilen kod veya yerel kod ile kullanmanıza olanak sağlar. Nullptr anahtar sözcüğü bir nesneye bir nesne tanıtıcısı, iç işaretçi veya yerel işaretçi türü göstermiyor gösterir. / CLR seçeneği kullanmadığınızda/CLR derleyici seçeneği kullandığınızda, yönetilen kod ve yerel kodu olacak şekilde nullptr derleyici yorumlar.
Microsoft'a özgü __nullptr anahtar sözcüğü nullptr ile aynı anlamı taşır, ancak yalnızca yerel koda uygular. / CLR derleyici seçeneği kullanarak yerel C/C++ kod derleme yaparsanız derleyici nullptr anahtar sözcüğü bir yerel veya yönetilen bir terim olup olmadığını belirleyemiyor. Derleyicinin temizleyin, amacınız yapmak için nullptr anahtar sözcüğü Yönetilen terim ve yerel terim belirtmek için __nullptr belirtmek için kullanın.

**/ ZC: trigraphs derleyici seçeneği.** Varsayılan olarak, desteği trigrafları devre dışı. / ZC: trigraphs derleyici seçeneği trigrafları desteğini etkinleştirmek için kullanın.
İki ardışık soru benzersiz üçüncü bir karakterin ardından işareti (?), bir trigrafı oluşur. Derleyici bir trigrafı karşılık gelen bir noktalama karakteri ile değiştirir. Örneğin, derleyici değiştirir?? # (sayı işareti) karakteri ile trigrafı =. Trigrafları belirli noktalama karakterleri içermeyen bir karakter kümesi kullanan C kaynak dosyalarında kullanın.

**Yeni profil temelli iyileştirme seçeneği.** PogoSafeMode uygulamanızı en iyi duruma getirdiğinizde güvenli mod veya hızlı mod kullanılıp kullanılmayacağını belirlemenize olanak sağlayan yeni bir profil temelli iyileştirme seçenektir. İş parçacığı güvenli mod, ancak hızlı mod yavaştır. Hızlı mod varsayılan davranıştır.

**Yeni ortak dil çalışma zamanı (CLR) seçeneği /clr:nostdlib.** / CLR (ortak dil çalışma zamanı derlemesi) için yeni bir seçenek eklenir. Aynı kitaplıkları farklı sürümleri dahil, bir derleme hatası verilir. Yeni seçenek programınızı belirtilen sürüm kullanabilmesi için varsayılan CLR kitaplık dışlamanıza olanak sağlar.

**Yeni pragma yönergesi detect_mistmatch.** Pragma yönergesi detect_mismatch bir etiket dosyalarınızda karşılaştırılır aynı ada sahip başka etiketler put olanak sağlar. Aynı ad için birden çok değer varsa bağlayıcı bir hata verir.

**XOP İç bilgileri, FMA4 İç bilgileri ve LWP İç bilgileri.** Yeni iç işlevler XOP İç bilgileri eklendi Visual Studio 2010 SP1, iç bilgileri FMA4 İç eklenen için Visual Studio 2010 SP1 ve LWP İç bilgileri eklendi için Visual Studio 2010 SP1 işlemci teknolojileri için destek eklendi. __Cpuid, belirli bir bilgisayarda hangi işlemci teknolojilerinin desteklendiğini belirlemek için __cpuidex kullanın.

### <a name="visual-c-projects-and-the-build-system"></a>Visual C++ projeleri ve yapı sistem

**MSBuild.** Visual C++ çözümler ve projeler şimdi VCBuild.exe değiştirir MSBuild.exe kullanarak oluşturulur. MSBuild diğer Visual Studio dilleri ve proje türleri tarafından kullanılan aynı esnek, Genişletilebilir, XML tabanlı derleme aracıdır. Bu değişiklik nedeniyle Visual C++ proje dosyalarını şimdi bir XML dosya biçimini kullanın ve .vcxproj dosya adı uzantısına sahiptir. Visual Studio sürümlerinde Visual C++ proje dosyalarından otomatik olarak yeni bir dosya biçimine dönüştürülür.

**VC ++ dizinleri.** VC ++ dizinleri ayarlama şimdi iki yerde bulunur. VC ++ dizinleri proje başına değerlerini ayarlamak için proje özellik sayfalarını kullanın. Özellik Yöneticisi ve genel ayarlamak için bir özellik sayfası VC ++ dizinleri başına yapılandırma değerlerini kullanın.

**Proje Proje bağımlılıkları.** Önceki sürümlerde, projeler arasında tanımlanan bağımlılıkları çözüm dosyasında saklanır. Bu çözümlerin yeni bir proje dosya biçimine dönüştürüldüğünde bağımlılıkları proje proje başvuruları dönüştürülür. Çözüm bağımlılıklarını ve proje proje başvuruları kavramlarını farklı olduğu için bu değişiklik uygulamaları etkileyebilir.

**Makrolar ve ortam değişkenleri.** Yeni _ITERATOR_DEBUG_LEVEL makrosu yineleyiciler hata ayıklama desteği çağırır. Bu makrosu yerine eski _SECURE_SCL ve _HAS_ITERATOR_DEBUGGING makroları kullanın.

### <a name="visual-c-libraries"></a>Visual C++ Kitaplıkları

**Eşzamanlılık Çalışma zamanı kitaplıkları.** Eşzamanlılık Çalışma zamanı framework uygulamaları ve aynı anda çalışmasına bileşenleri destekler ve eşzamanlı uygulamalarında Visual C++ programlama çerçevesidir. Eşzamanlı uygulama programlama desteklemek için paralel Desen kitaplığı (PPL) genel amaçlı kapsayıcıları ve algoritmaları hassas paralellik gerçekleştirmek için sağlar. Zaman uyumsuz aracılar kitaplığı bir aktör tabanlı programlama modeli ve görevleri ardışık düzen ve arabirimler parçalı veri akışı için geçirme ileti sağlar.

**Standart C++ Kitaplığı.** Aşağıdaki listede birçok standart C++ Kitaplığı'na yapılan değişiklikleri açıklar.

- Yeni rvalue başvuru C++ dili özelliği, taşıma semantik ve birçok işlevler için kusursuz iletme standart Şablon Kitaplığı'nda uygulamak için kullanılır. Semantiği taşıyın ve kusursuz iletme büyük ölçüde ayırmak veya değişkenler veya parametreler işlemlerinin performansını geliştirebilirsiniz.
- Rvalue başvuru auto_ptr sınıfı daha güvenli bir akıllı işaretçi türde yeni unique_ptr sınıfı uygulamak için de kullanılır. Unique_ptr sınıfı taşınabilir ancak değil copyable uygulayan güvenlik etkilemeden katı sahipliği semantiği olduğunu ve iyi rvalue başvuruları farkında kapsayıcılarını ile çalışır. Auto_ptr sınıfı kullanım dışıdır.
- Örneğin, find_if_not, copy_if ve is_sorted, beş yeni işlevler eklenmiştir \<algoritması > Üstbilgi.
- İçinde \<bellek >, yeni make_shared işlevi başlığıdır nesne yapılandırılmıştır aynı anda bir nesne için paylaşılan bir işaretçi yapmak için kullanışlı, sağlam ve verimli bir yol.
- Tarafından desteklenen tek bağlı listeleri \<forward_list > Üstbilgi.
- Yeni cbegin, cend, crbegin ve crend üye işlevleri bir kapsayıcı ileriye veya geriye doğru hareket const_iterator sağlar.
- \<System_error > Üstbilgi ve ilgili şablonları alt düzey sistem hatalarının işlenmesini destekler. Exception_ptr sınıfı üyeleri özel durumları iş parçacıkları arasında taşıma için kullanılabilir.
- \<Codecvt > Üstbilgi destekleyen diğer Kodlamalar çeşitli Kodlamalar Unicode karakter dönüştürme.
- \<Allocators > Üstbilgi ayırın ve boş bellek blokları düğümünü tabanlı kapsayıcıları için Yardım çeşitli şablonlar tanımlar.
- Çok sayıda güncelleştirme \<rastgele > Üstbilgi.

### <a name="microsoft-foundation-class-mfc-library"></a>Microsoft Foundation Class (MFC) kitaplığı

**Windows 7 özellikleri.** MFC çok sayıda Windows 7 özellikleri, örneğin, Şerit kullanıcı arabirimi (UI), görev çubuğunda, bağlantı listeleri, sekmeli küçük resimleri, küçük resim önizlemeleriyle, ilerleme çubuğu, simge katmanını ve arama dizini oluşturma destekler. MFC otomatik olarak çok sayıda Windows 7 özellikleri desteklediğinden, mevcut uygulamanızda değiştirmek olmayabilir. İçinde yeni uygulamalar diğer özellikleri desteklemek için kullanmak istediğiniz işlevleri belirtmek için MFC Uygulama Sihirbazı'nı kullanın.

**Çok dokunma tanıma.** MFC çok dokunma kullanıcı arabirimine sahip uygulamalar gibi Microsoft Surface işletim sistemi için yazılmış olan uygulamaları destekler. Bir çok touch uygulaması Windows dokunma iletileri ve dokunma iletileri birleşimleridir hareketi iletileri işleyebilir. Yalnızca uygulamanız dokunma için kaydolun ve hareketi olayları ve işletim sistemi çok dokunma olayları olay işleyicilerine yönlendirilecek.

**Yüksek DPI tanıma.** Varsayılan olarak, MFC uygulamaları artık yüksek DPI kullanmayan bulunur. Yüksek DPI (yüksek inç başına nokta) kullanan bir uygulama ise, işletim sisteminin windows, metin ve diğer kullanıcı Arabirimi öğeleri geçerli ekran çözünürlüğü için ölçeklendirebilirsiniz. Bu, ölçeklendirilmiş bir görüntü doğru düzenlendiği ve değil kırpılmış olasılığı daha yüksektir anlamına gelir veya pixelated.

**Yöneticisi'ni yeniden başlatın.** Yeniden başlatma Yöneticisi'ni otomatik olarak belgeleri kaydeder ve beklenmedik bir şekilde kapatır veya yeniden başlatır, uygulamanızın yeniden başlatır. Örneğin, otomatik güncelleştirme tarafından kapatıldıktan sonra uygulamayı başlatmak için yeniden başlatma Yöneticisi'ni kullanabilirsiniz. Yeniden başlatma Yöneticisi'ni kullanmak için uygulamanızı yapılandırma hakkında daha fazla bilgi için bkz: nasıl yapılır: yeniden başlatma Yöneticisi desteği ekleme.

**CTaskDialog.** CTaskDialog sınıfı standart AfxMessageBox ileti kutusu yerine kullanılabilir. CTaskDialog sınıfı standart ileti kutusu daha fazla bilgi mu toplar ve görüntüler.

#### <a name="safeint-library"></a>SafeInt Kitaplığı

Yeni SafeInt Kitaplığı güvenli aritmetik işlemler bu hesap için tamsayı taşma gerçekleştirir. Bu kitaplık, aynı zamanda tamsayılar farklı türde karşılaştırır.

#### <a name="new-active-template-library-atl-macros"></a>Yeni Etkin Şablon kitaplığı (ATL) makroları

Yeni makrolar PROP_ENTRY_TYPE ve PROP_ENTRY_TYPE_EX işlevselliğini genişletmek için ATL için eklenmiştir. PROP_ENTRY_INTERFACE ve PROP_ENTRY_INTERFACE_EX geçerli CLSID listesini eklemenize olanak tanır. PROP_ENTRY_INTERFACE_CALLBACK ve PROP_ENTRY_INTERFACE_CALLBACK_EX CLSID geçerli olup olmadığını belirlemek için bir geri çağırma işlevini belirtmenize olanak tanır.

#### <a name="analyze-warnings"></a>/ analyze uyarıları

En / analyze (Kurumsal kod uyarıları C çalışma zamanı (CRT), MFC ve ATL kitaplıklarından kaldırılmış çözümleme).

#### <a name="animation-and-d2d-support"></a>Animasyon ve D2D desteği

MFC artık animasyon ve Direct2D grafiklerini destekler. MFC kitaplığını birkaç yeni MFC sınıfları ve bu işlevselliği desteklemek üzere işlevleri vardır. D2D nesnesi ve bir animasyon nesne için bir proje eklemek nasıl göstermek için iki yeni izlenecek yol da vardır. Bu izlenecek olan izlenecek yol: bir MFC projesine ve gözden geçirme D2D nesnesi ekleme: bir MFC projesine animasyon ekleme.

### <a name="ide"></a>IDE

**Geliştirilmiş IntelliSense.** Visual C++ için IntelliSense tamamen daha hızlı, daha doğru ve daha büyük projeler işlemek için tasarlanmıştır. Bu geliştirme elde etmek için nasıl bir geliştirici görünümleri ve kaynak kodunu değiştirir ve kaynak kodu ve proje ayarları IDE bir çözümü oluşturmak için nasıl kullandığını arasında bir fark IDE sağlar.
Bu görev ayrımını nedeniyle gibi sınıf görünümü ve yeni gitmek için iletişim kutusu tarafından eski değiştiren bir yeni SQL Server Masaüstü Veritabanı (.sdf) dosyasını temel alan bir sistem hiçbir derleme işlenen göz atma özellikleri (.ncb) dosya göz atın. IntelliSense özellikleri hızlı bilgi, otomatik tamamlama ve parametre Yardım gibi yalnızca gerekli olduğunda çeviri birimleri ayrıştırılamıyor. Karma özellikleri gibi yeni bir çağrı hiyerarşisi penceresi Gözat ve IntelliSense özellikleri bileşimini kullanır.
IntelliSense yalnızca şu anda ihtiyaç duyduğunuz bilgileri işlediğinden, IDE daha iyi yanıt. Bilgi daha güncel olduğundan, ayrıca, IDE görünümleri ve windows daha doğru. Son olarak, IDE altyapı daha iyi düzenlenmiş, daha yetenekli ve daha ölçeklenebilir olduğundan, daha büyük projeleri işleyebilir.

**Geliştirilmiş IntelliSense hatalar.** IDE daha iyi IntelliSense kaybına neden olabilecek hataları algılar ve bunları altında kırmızı dalgalı alt çizgiler görüntüler. Ayrıca, IDE IntelliSense hataları için Hata Listesi penceresi bildirir. Soruna neden olan kodumu görüntülemek için Hata Listesi penceresi hatayı çift tıklatın.

**# Otomatik Tamamlama özelliği include.** IDE için otomatik tamamlama destekleyen # anahtar sözcüğü include. Yazdığınızda #include, IDE geçerli üstbilgi dosyaları, aşağı açılan liste kutusu oluşturur. Dosya adını yazarak devam ederseniz, IDE listenin girişi temel alarak filtreler. Herhangi bir noktada eklemek istediğiniz dosya listeden seçebilirsiniz. Bu, hızlı tam dosya adını bilmeden dosyaları dahil etmenizi sağlar.

**Gidin.** Gezinmek için iletişim kutusu, tüm simgeleri ve belirtilen bir dizeyle Eşleştir dosyaları projenizdeki arama sağlar. Arama dizesinde ek karakterler yazarken arama sonuçları hemen düzeltilir. Sonuçları geri bildirim alan bulunan öğelerin sayısı bildirir ve aramanızı sınırlamak karar vermenize yardımcı olur. Tür/kapsam, konum ve önizleme geri bildirim alanları benzer adlara sahip öğeleri belirsizliğini ortadan kaldırmak yardımcı olur. Ayrıca, diğer programlama dilleri desteklemek için bu özelliği genişletebilirsiniz.

**Paralel hata ayıklama ve profil oluşturma.** Visual Studio hata ayıklayıcısı eşzamanlılık çalışma zamanı farkındadır ve, paralel işleme uygulamalarla ilgili sorunları gidermenize yardımcı olur. Uygulamanızın genel davranışını görselleştirmek için yeni eşzamanlılık Profil Oluşturucu aracını kullanabilirsiniz. Ayrıca, görevleri ve bunların çağrı yığınları durumunu görselleştirmek için yeni windows aracı kullanabilirsiniz.

**Şerit Tasarımcısı.** Şerit Tasarımcısı oluşturmak ve bir MFC Şerit UI'si değiştirmenizi sağlayan bir grafik düzenleyicisidir. Son Şerit UI'si bir XML tabanlı kaynak dosyası (.mfcribbon-ms) temsil edilir. Var olan uygulamalar için geçici olarak birkaç satır kod ekleme ve Şerit Tasarımcısı çağrılırken, geçerli Şerit UI'si yakalayabilirsiniz. Şerit kaynak dosyası oluşturulduktan sonra el yazısı Şerit UI kod Şerit kaynağı yükleme birkaç deyimleri ile değiştirin.

**Çağrı hiyerarşisi.** Çağrı hiyerarşisi penceresi, belirli bir işlev tarafından çağrılan tüm işlevleri veya belirli bir işlevi çağırmak tüm işlevleri gidin olanak tanır.

### <a name="tools"></a>Araçlar

**MFC Sınıf Sihirbazı.** Visual C++ 2010 iyi regarded MFC Sınıf Sihirbazı Aracı'nı geri getirir. MFC Sınıf Sihirbazı'nı el ile kaynak dosyaları kümesini değiştirmek zorunda kalmadan bir projeye sınıfları, iletileri ve değişkenleri eklemek için uygun bir yoludur.

**ATL Denetim Sihirbazı.** ATL Denetim Sihirbazı'nı ProgID alan artık otomatik olarak doldurur. ATL Denetim ProgID sahip değilse, diğer araçları ile çalışmayabilir. Tek bir ProgID denetimlerinizin gerektiren bir aracı Active Denetimi Ekle iletişim kutusu örnektir. ActiveX denetimi Ekle iletişim kutusu iletişim kutusu hakkında daha fazla bilgi için bkz.

### <a name="microsoft-macro-assembler-reference"></a>Microsoft Macro Assembler Başvurusu

YMMWORD veri türü eklenmesi, Intel Gelişmiş vektör Uzantıları (AVX) yönergeleri dahil 256 bit multimedya işlenenleri destekler.

## <a name="whats-new-for-c-in-visual-studio-2008"></a>C++ Visual Studio 2008'deki yenilikler

### <a name="visual-c-integrated-development-environment-ide"></a>Visual C++ tümleşik geliştirme ortamı (IDE)

- ATL ve MFC Win32 uygulamaları artık oluşturulan iletişim kutuları, Windows Vista stili yönergelerine uyduğundan. Visual Studio 2008 kullanarak yeni bir proje oluşturduğunuzda, uygulamanıza eklediğiniz tüm iletişim kutularını Windows Vista Stil Kılavuzu ile uyumlu. Visual Studio'nun önceki bir sürümüyle oluşturulmuş bir Proje derlenir, varolan herhangi bir iletişim kutusunu daha önce sahip oldukları aynı konum korur. İletişim kutusu Düzenleyicisi iletişim kutularını uygulamanıza eklemek hakkında daha fazla bilgi için bkz.

- ATL Proje Sihirbazı'nı şimdi tüm kullanıcılar için bileşenleri kaydetmek için bir seçenek vardır. Tüm kullanıcılar için kayıt bileşeni seçmediğiniz sürece Visual Studio 2008'den itibaren COM bileşenlerini ve ATL Proje Sihirbazı tarafından oluşturulan tür kitaplıklarının HKEY_CURRENT_USER düğümünün kayıt defterini kaydedilir.
- ATL projeleri oluşturmak için bir seçenek öznitelikli ATL Proje Sihirbazı'nı artık sağlar. Visual Studio 2008'den itibaren yeni bir proje öznitelikli durumunu değiştirmek için bir seçenek ATL Proje Sihirbazı'nı yok. Sihirbazın oluşturduğu tüm yeni ATL projeleri sunulmuştur unattributed.
- Kayıt defterine yazılıyor yönlendirilebilir. Windows Vista başlanmasıyla, bir programı yükseltilmiş modda çalıştırmak için belirli kayıt defteri alanı yazılmasını gerektirir. Visual Studio her zaman yükseltilmiş modda çalıştırmak için arzu değil. Kullanıcı başına yeniden yönlendirme kayıt defteri yazma hızı HKEY_CLASSES_ROOT HKEY_CURRENT_USER için herhangi bir programlama değişiklik yapılmadan otomatik olarak yeniden yönlendirir.
- Sınıf Tasarımcısı şimdi yerel C++ kodu için destek sınırlıdır. Visual Studio'nun önceki sürümleri, yalnızca Visual C# ve Visual Basic ile Sınıf Tasarımcısı çalışmıştır. C++ kullanıcılar, artık yalnızca salt okunur modda Sınıf Tasarımcısı kullanabilirsiniz. Sınıf tasarımcısında Visual C++ kodu ile çalışma Sınıf Tasarımcısı C++ ile kullanma hakkında daha fazla bilgi için bkz.
- Proje Sihirbazı'nı artık bir SQL Server C++ projesi oluşturmak için bir seçenek vardır. Visual Studio 2008'den itibaren Yeni Proje Sihirbazı'nı bir SQL Server C++ projesi oluşturmak için bir seçenek yok. Visual Studio'nun önceki bir sürümü kullanılarak oluşturulan SQL Server projeleri hala derleyin ve düzgün çalışır.

### <a name="visual-c-libraries"></a>Visual C++ Kitaplıkları

#### <a name="general"></a>Genel

- Visual C++ kitaplıkları belirli sürümleri için uygulamalar bağlanabilir. Bazen bir uygulama için Visual C++ kitaplıkları bir sürümünden sonra yapılan güncelleştirmeler bağlıdır. Bu durumda, uygulamanın önceki sürümler kitaplıkların bir bilgisayarda çalışan beklenmeyen davranışlara neden olabilir. Böylece kitaplıkları önceki bir sürümü olan bir bilgisayarda çalışmaz uygulamanın belirli bir sürüme kitaplıkların şimdi bağlayabilirsiniz.

#### <a name="stlclr-library"></a>STL/CLR Kitaplığı

- Visual C++ artık STL/CLR kitaplığı içerir. STL/CLR kitaplığı paketleme, standart Şablon kitaplığı (STL), bir alt C++ ve .NET Framework ortak dil çalışma zamanı (CLR) ile kullanmak için standart C++ Kitaplığı ' dir. STL/CLR ile tüm kapsayıcıları, Yineleyiciler ve STL algoritmaları yönetilen bir ortamda artık kullanabilirsiniz.

#### <a name="mfc-library"></a>MFC Kitaplığı

- Windows Vista ortak denetimleri destekler. 150'den fazla yöntemleri 18 sınıflardaki yeni veya var olan Windows Vista'da özellikleri desteklemek için veya geçerli MFC sınıfları işlevleri geliştirmek için eklenmiştir.
- Yeni CNetAddressCtrl sınıfı, giriş ve IPv4 ve IPv6 adresleri veya DNS adlarını doğrulama sağlar.
- Yeni CPagerCtrl sınıfı Windows çağrı cihazı denetim kullanımını basitleştirir.
- Yeni CSplitButton sınıfı bir varsayılan veya isteğe bağlı eylem seçmek için Windows splitbutton denetim kullanımını basitleştirir.

#### <a name="c-support-library"></a>C++ Destek Kitaplığı

- C++ hazırlama kitaplığını tanıtır. Hazırlama kitaplığını yerel ve yönetilen ortamlar arasında verileri hazırlamak için kolay ve en iyi duruma getirilmiş bir yol sağlar. Kitaplık PInvoke kullanarak gibi daha karmaşık ve daha az verimli yaklaşımlar alternatiftir. Genel bakış, hazırlama c++ daha fazla bilgi için bkz.

#### <a name="atl-server"></a>ATL Sunucu

- ATL Sunucu paylaşılan kaynak projesi olarak yayımlanır.
- ATL Sunucu kod tabanını çoğu CodePlex üzerinde paylaşılan kaynaklı proje olarak yayımlanmıştır ve Visual Studio 2008'in bir parçası olarak yüklü değil. ATL Sunucu ile ilişkilendirilen çeşitli dosyaları artık Visual Studio bir parçasıdır. ATL Sunucusu dosyaları kaldırıldı kaldırılan dosyaların listesi için bkz.
- Kodlama ve kod çözme atlenc.h ve yardımcı işlevlerini sınıflardan ve atlutil.h ve atlpath.h sınıflardan veri şimdi ATL kitaplığının parçasıdır.
- Microsoft, Visual Studio'nun bu sürümleri desteklenir sürece, Visual Studio'nun önceki sürümlerde bulunan ATL sunucu sürümlerini desteklemeye devam eder. CodePlex, ATL sunucu kodu geliştirme topluluk projesi olarak devam eder. Microsoft, ATL Sunucu CodePlex sürümünü desteklemiyor.

### <a name="visual-c-compiler-and-linker"></a>Visual C++ derleyicisi ve bağlayıcı

#### <a name="compiler-changes"></a>Derleyici değişiklikleri

- Derleyici yönetilen artımlı derlemelerini destekler. Bu seçeneği belirttiğinizde, derleyici, kod başvurulan derlemeyi değiştiğinde derlenir değil. Bunun yerine bir artımlı derleme gerçekleştirir. Yalnızca değişiklikler bağımlı kod etkilerse dosyaları derlenir.
- ATL sunucusu ile ilgili öznitelikleri artık desteklenmemektedir. Derleyici artık ATL sunucusu ile doğrudan ilgili birkaç öznitelik destekler. Yeni değişiklikler kaldırılan özniteliklerin tam listesi için bkz.
- Derleyici Intel Core mikro mimarisi destekler. Intel Core mikro mimarisi için kod oluşturma sırasında ayarlama derleyici içerir. Varsayılan olarak, bu ayar etkindir ve Pentium 4 ve diğer işlemciler de yardımcı olduğundan devre dışı bırakılamaz.
- İç bilgiler yeni AMD ve Intel işlemcileri destekler. Birkaç yeni iç yönergeleri daha yeni AMD ve Intel işlemcileri işlevselliği destekler. Yeni İç bilgileri hakkında daha fazla bilgi için ek Streaming SIMD uzantıları 3 yönergeleri, Streaming SIMD uzantıları 4 yönergeleri, SSE4A ve Gelişmiş Bit işleme iç bilgileri, AES iç bilgileri, _mm_clmulepi64_si128 ve __rdtscp bakın.
- __Cpuid işlevi güncelleştirilir. __Cpuid __cpuidex işlevleri artık AMD ve Intel işlemcileri son sürümlerine birkaç yeni özellikleri destekler. İç __cpuidex yenidir ve son işlemcileri'nden daha fazla bilgi toplar.
- /MP derleyici seçeneği toplam derleme süresini azaltır. /MP seçeneği dosyaları aynı anda derlemek çeşitli işlemleri oluşturarak birkaç kaynak dosyalarını derlemek için toplam süreyi önemli ölçüde azaltabilir. Bu seçenek, hiper iş parçacığı, birden çok işlemciye veya birden çok çekirdek destekleyen bilgisayarlarda özellikle yararlıdır.
- __W64 anahtar sözcüğü ve /Wp64 derleyici seçeneği kullanım dışı bırakılmıştır. 64 bit taşınabilirlik sorunlarını algıla, /Wp64 derleyici seçeneği ve __w64 anahtar sözcüğü, kullanım dışıdır ve derleyici gelecek bir sürümünde kaldırılacak. Derleyici seçeneği ve bu anahtar sözcüğü yerine, bir Visual C++ Derleyici hedeflerin 64 bit platform kullanın.
- / Qfast_transcendentals soyut işlevleri için satır içi kod oluşturur.
- / Qimprecise_fwaits /fp kullandığınızda try blokları fwait komutları iç kaldırır: dışındaki derleyici seçeneği.

### <a name="linker-changes"></a>Bağlayıcı değişiklikleri

- Kullanıcı hesabı denetimi bilgileri artık bildirim dosyalarına yürütülebilir dosyaları için Visual C++ bağlayıcı (link.exe) katıştırılır. Bu özellik varsayılan olarak etkindir.   Bu özellik devre dışı bırakma ya da varsayılan davranışı değiştirme hakkında daha fazla bilgi için /MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır) bakın.
- Bağlayıcı şimdi /DYNAMICBASE Windows Vista'nın adres boşluğu düzeni rastgele seçimini özelliğini etkinleştirme seçeneğiniz vardır. Bu seçenek, uygulama yükleme zamanında rastgele rebased olup olmadığını belirtmek için yürütülebilir bir dosya üstbilgisi değiştirir.

## <a name="whats-new-for-c-in-visual-studio-2005"></a>C++ Visual Studio 2005'teki yenilikler

Aşağıdaki özellikler Visual C++ 2005 Service Pack 1'de yeni:

### <a name="intrinsics-for-x86-and-x64"></a>İç bilgiler x86 hem x64 için

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

### <a name="intrinsics-for-x64-only"></a>İç bilgiler yalnızca x64 için

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

Derleyici önemli değişiklikler bu sürümde sahiptir.

- ' 64-bit yerel ve çapraz derleyicileri.
- / analyze (Kurumsal kod çözümleme) derleyici seçeneği eklenmiştir.
- / bigobj derleyici seçeneği eklenmiştir.
- /clr:pure, /clr:safe, and /clr:oldSyntax have been added. (Daha sonra Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 kaldırıldı.)
- Derleyici seçenekleri kullanım: Bu sürümde; birçok derleyici seçenekleri kullanım dışı bırakıldı kullanım dışı derleyici seçenekleri daha fazla bilgi için bkz.
- / CLR kodda çift dönüştürme azalır; Çift dönüştürme (C++) daha fazla bilgi için bkz.
- /EH (özel durum işleme modeli) veya /EHs artık bir throw dışında bir şey ile gerçekleştirilen bir özel durum yakalamak için kullanılabilir; /EHa kullanın.
- / errorreport (dahili derleme hatalarını raporla) derleyici seçeneği eklenmiştir.
- / favor (64 için iyileştirme) derleyici seçeneği eklenmiştir.
- / FA, /Fa (listeleme dosyası) derleyici seçeneği eklenmiştir.
- /FC (tam yolu, kaynak kodu dosyasının tanılamadaki) derleyici seçeneği eklenmiştir.
- /FP (Floating-Point davranış belirtme) derleyici seçeneği eklenmiştir.
- /G (işlemci için iyileştirme) seçenekleri derleyici seçeneği eklenmiştir.
- /G (işlemci için iyileştirme) seçenekleri derleyici seçeneği eklenmiştir.
- / G3, /G4, /G5, /G6, /G7 ve /GB derleyici seçenekleri kaldırılmıştır. Derleyici şimdi "tüm mimarileri için en iyi çıktı dosyası oluşturma girişimleri karışık bir modeli" kullanır.
- /GF kaldırılmıştır. /GF (yinelenen dizeleri ortadan) kullanın.
- /GL (bütün Program iyileştirmesi) artık /CLRHEADER ile uyumludur.
- /gr artık varsayılan olarak açıktır.
- /GS (arabellek güvenlik denetimi) şimdi savunmasız işaretçi parametreleri için güvenlik korumasını sağlar. /GS artık varsayılan olarak açıktır. /GS şimdi de için MSIL/CLR (ortak dil çalışma zamanı derlemesi) ile derlenmiş işlevleri üzerinde çalışır.
- / homeparams (kayıt parametrelerini yığına Kopyala) derleyici seçeneği eklenmiştir.
- / hotpatch (düzeltme eki eklenebilen görüntü oluşturma) derleyici seçeneği eklenmiştir.
- Satır içi işlev buluşsal yöntemler güncelleştirildi; Satır içi, __inline, __forceinline ve inline_depth daha fazla bilgi için bkz.
- Birçok yeni iç işlevler eklenir ve birçok önceden belgelenmemiş iç bilgileri şimdi belgelenmiştir.
- Varsayılan olarak, başarısız olan herhangi bir çağrısına yeni bir özel durum oluşturur.
- /ML ve /MLd derleyici seçenekleri kaldırılmıştır. Visual C++ artık tek iş parçacıklı, statik olarak bağlantılı CRT kitaplık desteği destekler.
- Derleyici adlı dönüş değeri /O1, O2 derlediğinizde, etkinleştirilen en iyi duruma getirme, uygulanan (boyutu en aza indirmek, hızı en üst düzeye) /Og (Global iyileştirmeler) ve /Ox (tam iyileştirme).
- /OA derleyici seçeneği kaldırıldı ancak sessizce göz ardı edilir; noalias veya restrict__declspec değiştiricileri nasıl derleyici yumuşatma mu belirtmek için kullanın.
- /OP derleyici seçeneği kaldırılmış. /FP (Floating-Point davranış belirtin) kullanın.
- OpenMP şimdi Visual C++ tarafından desteklenir.
- / OpenMP (OpenMP 2.0 desteğini etkinleştir) derleyici seçeneği eklenmiştir.
- /OW derleyici seçeneği kaldırıldı ancak sessizce yok sayılacak. Noalias veya restrict__declspec değiştiricileri nasıl derleyici yumuşatma mu belirtmek için kullanın.

### <a name="profile-guided-optimizations"></a>Profil Temelli İyileştirmeler

- / QI0f kaldırılmıştır.
- / QIfdiv kaldırılmıştır.
- / QIPF_B (ayrıntıyla açıklayan hata bilgilerini B CPU atlama için) derleyici seçeneği eklenmiştir.
- / QIPF_C (ayrıntıyla açıklayan hata bilgilerini C CPU atlama için) derleyici seçeneği eklenmiştir.
- / QIPF_fr32 (yapmak olmayan kullanım üst 96 kayan noktası kaydeder) derleyici seçeneği eklenmiştir.
- / QIPF_noPIC (konum bağımlı kodu oluştur) derleyici seçeneği eklenmiştir.
- / QIPF_restrict_plabels (varsayın Hayır işlevleri oluşturulan çalışma zamanında) derleyici seçeneği eklenmiştir.

### <a name="unicode-support-in-the-compiler-and-linker"></a>Derleyicide ve Bağlayıcıda Unicode Desteği

- /VD (yapı yer devre dışı bırak) değiştirmelerini şimdi dynamic_cast işleci yapılandırılan bir nesne üzerinde kullanmanıza olanak verir (/ vd2)
- /YX derleyici seçeneği kaldırılmıştır. /Yc (önceden derlenmiş üst bilgi dosyası oluştur) veya /Yu (önceden derlenmiş üst bilgi dosyasını kullanma) kullanın. /YX, yapı yapılandırmalardan kaldırmanız ve hiçbir şey ile değiştirmek, daha hızlı derlemelerde neden olabilir.
- / ZC: forscope artık varsayılan olarak açıktır.
- / ZC: wchar_t artık varsayılan olarak açıktır.
- /ZD derleyici seçeneği kaldırılmıştır. Satır numarası yalnızca hata ayıklama bilgileri artık desteklenmiyor. /Zı (/Z7, / zi, /zı (hata ayıklama bilgileri biçimi) daha fazla bilgi için bkz.) kullanın.
- /ZG artık yalnızca C kaynak kodu dosyaları ve C++ kaynak kodu dosyaları değil, geçerli olur.
- /ZX (en iyi duruma getirilmiş Itanium kodu hata ayıklama) derleyici seçeneği eklenmiştir.

### <a name="new-language-features"></a>Yeni dil özellikleri

- Attributeattribute artık kullanım dışı bırakılmıştır.
- appdomain__declspec değiştiricisi eklendi.
- __clrcall arama kuralı eklendi.
- kullanım dışı (C++) declspec değiştiricisi artık kullanım dışı sınıfı veya işlevi erişmek için bir kullanıcı bulunduğunda derleme zamanında görüntülenen bir dize belirtmenize olanak tanır.
- dynamic_cast işleci önemli değişiklikler vardır.
- Yerel numaralandırmaları artık temel alınan tür belirtmenizi sağlar.
- jitintrinsicdeclspec değiştiricisi eklendi.
- noaliasdeclspec değiştiricisi eklendi.
- process__declspec değiştiricisi eklendi.
- soyut, geçersiz kılmak ve korumalı yerel derlemeleri için geçerlidir.
- __restrict anahtar sözcüğü eklendi.
- restrictdeclspec değiştiricisi eklendi.
- __thiscall anahtar sözcük sunulmuştur.
- __unaligned anahtar sözcüğü artık belgelenmiş durumdadır.
- geçici (C++) en iyi duruma getirme ile ilgili davranışı güncelleştirdi.

### <a name="new-preprocessor-features"></a>Önişlemci yenilikleri

- __CLR_VER önceden tanımlanmış makrosu eklendi.
- Yorum (C/C++) pragma /MANIFESTDEPENDENCY şimdi bağlayıcı yorum olarak kabul eder. Açıklama eklemek için exestr seçeneği artık kullanım dışı bırakılmıştır.
- embedded_idl özniteliği (#import yönergesi) artık isteğe bağlı bir parametre alır.
- fenv_access pragması
- float_control pragması
- fp_contract pragması
- Genel değişkenler pragma içinde yönetilmeyen ve yönetilmeyen bölümler, yönetilen, genel değişkenler varsa bunlar bildirilir sırayla başlatılmayacak. Bu olası önemli bir değişiklik olur, örneğin, bir yönetilmeyen genel değişkeni ile yönetilen bir genel değişkenler başlatılır ve yönetilen tam oluşturulan nesneye gereklidir.
- İnit_seg ile belirtilen bölümler artık salt okunur ve okuma/önceki sürümlerinde olduğu gibi yazma değil.
- inline_depth varsayılan 16 sunulmuştur. 16'ın varsayılan de Visual C++ .NET 2003'te etkisi içindeydi.
- _Integral_max_bıts önceden tanımlanmış makrosu eklenen, önceden tanımlı makrolar bakın.
- _M_CEE, _M_CEE_PURE ve önceden tanımlanmış _M_CEE_SAFE makroları eklenen, önceden tanımlı makrolar bakın.
- _M_ıx86_fp önceden tanımlanmış makrosu eklendi.
- _M_X64 önceden tanımlanmış makrosu eklendi.
- make_public pragması
- yönetilen, yönetilmeyen pragma söz dizimi güncelleştirildi (itme ve pop artık yoktur)
- mscorlib.dll şimdi örtük olarak tarafından başvurulan # içinde tüm/CLR derlemelerine using yönergesi.
- _OPENMP önceden tanımlanmış makrosu eklendi.
- en iyi duruma getirme pragma güncelleştirildi, a ve w artık geçerli parametreleridir.
- #import no_registry özniteliği eklendi.
- bölge, eklenen endregion pragmaları
- _Vc_nodefaultlıb önceden tanımlanmış makrosu eklendi.
- Variadic makrolar şimdi uygulanır.
- vtordisp kullanım dışıdır ve Visual C++'ın bir sonraki sürümde kaldırılacak.
- Uyarı pragma bastır belirleyici artık sahiptir.

### <a name="new-linker-features"></a>Yeni bağlayıcı Özellikleri

- (Derleme olmayan MSIL çıkış dosyaları) modülleri şimdi bağlayıcı girişi olarak izin verilir.
- / ALLOWISOLATION (bildirim arama) bağlayıcı seçeneği eklenmiştir.
- / ASSEMBLYRESOURCE (yönetilen kaynağı katıştır), artık derlemede kaynağın adını belirtin ve kaynak bütünleştirilmiş kodunda özel olduğunu belirtmek için izin vermek için güncelleştirilmiştir.
- / CLRIMAGETYPE (CLR, türü görüntü belirtin) bağlayıcı seçeneği eklenmiştir.
- / CLRSUPPORTLASTERROR (korumak için son hata kodunu PInvoke çağrıları) bağlayıcı seçeneği eklendi.
- / CLRTHREADATTRIBUTE (CLR iş parçacığı özniteliğini Ayarla) bağlayıcı seçeneği eklenmiştir.
- / CLRUNMANAGEDCODECHECK (SupressUnmanagedCodeSecurityAttribute ekleme) bağlayıcı seçeneği eklenmiştir.
- / ERRORREPORT (dahili bağlayıcı hatalarını raporla) bağlayıcı seçeneği eklenmiştir.
- / EXETYPE bağlayıcı seçeneği kaldırılmıştır. Bağlayıcı artık oluşturma Windows 95 ve Windows 98 aygıt sürücülerini destekler. Bu aygıt sürücüleri oluşturmak için uygun bir DDK kullanın. EXETYPE anahtar sözcüğü artık modül tanımı dosyaları için geçerli değil.
- / FUNCTIONPADMIN (düzeltme eki eklenebilen görüntü oluşturma) bağlayıcı seçeneği eklenmiştir.
- / LTCG bağlayıcı seçeneği artık/CLR ile derlenmiş modüller desteklenir. / LTCG ayrıca profil temelli iyileştirmeler desteklemek üzere güncelleştirilmiştir.
- / BİLDİRİMİ (oluşturmak yan yana derleme bildirimi) bağlayıcı seçeneği eklenmiştir.
- / MANIFESTDEPENDENCY (bildirim bağımlılıklarını belirtin) bağlayıcı seçeneği eklenmiştir.
- / MANIFESTFILE (bildirim dosyasını Adlandır) bağlayıcı seçeneği eklenmiştir.
- /MAPINFO:LINES bağlayıcı seçeneği kaldırılmıştır.
- / NXCOMPAT (Veri Yürütme Engellemesi uyumlu) bağlayıcı seçeneği eklenmiştir.
- / PGD (Profile-Guided iyileştirmeler için veritabanını belirtin) bağlayıcı seçeneği eklenmiştir.
- / PROFILE (performans araçları Profil Oluşturucusu) bağlayıcı seçeneği eklendi.
- / SECTION (Bölüm öznitelikleri belirtin) bağlayıcı seçeneği artık özniteliği değilleme ve artık m veya D (VxD ilgili) öznitelikleri destekler.
- Derleyicide ve Bağlayıcıda Unicode Desteği
- / VERBOSE (ilerleme iletilerini Yazdır) bağlayıcı seçeneği şimdi de ICF ve REF kabul eder.
- / VXD bağlayıcı seçeneği kaldırılmıştır. Bağlayıcı artık oluşturma Windows 95 ve Windows 98 aygıt sürücülerini destekler. Bu aygıt sürücüleri oluşturmak için uygun bir DDK kullanın. VXD anahtar sözcüğü artık modül tanımı dosyaları için geçerli değil.
- /WS bağlayıcı seçeneği kaldırılmıştır. /WS Windows NT 4.0 için hedeflenen görüntülerini değiştirmek için kullanıldı. IMAGECFG.exe -R filename /WS yerine kullanılabilir. IMAGECFG.exe SUPPORT\DEBUG\I386\IMAGECFG Windows NT 4.0 ROM'da bulunabilir. EXE.
- /WX (Bağlayıcı uyarıları hata olarak değerlendir) bağlayıcı seçeneği artık belgelenmiş durumdadır.

### <a name="new-linker-utility-features"></a>Yeni bağlayıcı yardımcı programı özellikleri

- / ALLOWISOLATION editbin seçeneği eklendi
- Açıklama modül tanım dosyası deyimi kaldırılır. Bağlayıcı, artık sanal cihaz sürücüleri oluşturmayı destekler.
- / ERRORREPORT seçeneği bscmake.exe, dumpbin.exe ve lib.exe editbin.exe eklendi.
- / LTCG LIB seçeneği eklenmiştir.
- / NXCOMPAT editbin seçeneği eklenmiştir.
- / RANGE dumpbin seçeneği eklenmiştir.
- / TLS dumpbin seçeneği eklenmiştir.
- /WS editbin seçeneği kaldırılmıştır. /WS Windows NT 4.0 için hedeflenen görüntülerini değiştirmek için kullanıldı. IMAGECFG.exe -R filename /WS yerine kullanılabilir. IMAGECFG.exe SUPPORT\DEBUG\I386\IMAGECFG Windows NT 4.0 ROM'da bulunabilir. EXE.
- /WX [: Hayır] lib seçeneği eklenmiştir.

### <a name="new-nmake-features"></a>NMAKE yenilikleri

- / ERRORREPORT eklendi.
- /G eklendi.
- Önceden tanımlanmış kurallar güncelleştirildi.
- Özyineleme makroları belgelenen, $(MAKE) makrosu şimdi nmake.exe için tam yolunu sağlar.

### <a name="new-masm-features"></a>Yeni MASM özellikleri

- MASM ifadeleri şimdi 64-bit değerlerdir. Önceki sürümlerde MASM ifadeleri 32-bit değerleri yoktu.
- Yönerge __asm int 3 şimdi yerel derlenmesi için bir işlev neden olur.
- Diğer ad (MASM) artık belgelenmiş durumdadır.
- / ERRORREPORT ml.exe ve ml64.exe seçeneği eklenir.
- . FPO artık belgelenmiş durumdadır.
- H2INC.exe Visual C++ 2005'te birlikte değil. H2INC kullanmaya devam etmek gerekiyorsa, Visual C++'ın önceki bir sürümden H2INC.exe kullanın.
- IMAGEREL işleci eklendi.
- işleç hıgh32 eklendi.
- işleç LOW32 eklendi.
- ml64.exe x64 MASM sürümüdür mimarisi. X64 derler x64 .asm dosyalarıyla dosyaları nesne. Satır içi derleme dili x64 desteklenmiyor derleyici. Aşağıdaki MASM yönergeleri ml64.exe (x64) eklenmiştir:
- .ALLOCSTACK
- .ENDPROLOG
- .PUSHFRAME
- .PUSHREG
- .SAVEREG
- .SAVEXMM128
- . SETFRAME yanında PROC yönergesi yalnızca x64 sözdizimiyle güncelleştirildi.
- MMWORD yönergesi eklendi
- / OMF (ML.exe komut satırı seçeneği) şimdi /c anlamına gelir. ML.exe OMF biçimi nesnelerini bağlamanın desteklemez.
- SEGMENT yönergesi artık ek öznitelikler destekler.
- SECTIONREL işleci eklendi.
- XMMWORD yönergesi eklendi

### <a name="new-crt-features"></a>CRT yenilikleri

- Çeşitli işlevler güvenli sürümlerini eklenmiştir. Bu işlevler hataları daha iyi bir şekilde işlemek ve ortak güvenlik açıkları önlemeye yardımcı olmak için arabellek daha sıkı denetimleri zorlayın. Yeni Güvenli sürümleri _Yanları soneki ile tanımlanır.
- Çok daha az güvenli sürümlerini varolan işlevler kullanım dışı bırakıldı. Kullanımdan kaldırma uyarıları devre dışı bırakmak için _CRT_SECURE_NO_WARNINGS tanımlayın.
- Birçok var olan işlevler şimdi bunların parametrelerini doğrulayın ve geçersiz bir parametre geçirildiğinde geçersiz parametre işleyicisi çağırma.
- Birçok var olan işlevler şimdi burada değil Öncekine errno ayarlayın.
- Typedef errno_t türü tamsayı değerine sahip eklendi. errno_t her bir işlevin dönüş türü veya parametresi errno hata kodlarıyla ilgilenir kullanılır. errno_t errcode değiştirir.
- Yerel ayara bağımlı işlevler şimdi yerel bir parametre geçerli yerel kullanmak yerine alması sürümlere sahip. Bu yeni işlevler _l son ekine sahip. Yerel ayar nesneleriyle çalışmak için birkaç yeni işlevler eklendi. _Get_current_locale, _create_locale ve _free_locale yeni işlevler içerir.
- Yeni işlevleri kilitlenmesini ve kilidinin açılmasını dosya tanıtıcıları destek eklenmiştir.
- Önceki sürümlerde olduğu gibi işlevler _spawn ailesi başarılıysa sıfır olarak errno sıfırlamaz.
- Bağımsız değişkenler kullanılan sırayı belirlemenize olanak sağlayan İşlevler printf ailesinin sürümlerinde kullanılabilir.
- Unicode desteklenen metin biçiminde sunulmuştur. İşlev _kurulum Aç _O_TEXTW, _O_UTF8 ve _O_UTF16 öznitelikleri destekler. Fopen işlevi destekler "ccs kodlama =" Unicode biçiminde belirtmenin yöntemi.
- Yönetilen kod (MSIL) yerleşik CRT kitaplıkları yeni bir sürümü kullanıma sunulmuştur ve/CLR (ortak dil çalışma zamanı derlemesi) seçeneği ile derleme yapılırken kullanılır.
- _fileinfo kaldırılmıştır.
- Time_t için varsayılan boyutu 64 bit time_t aralığı ve saat işlevlerini birkaç yıl 3000 genişletir sunulmuştur.
- CRT şimdi yerel bir iş parçacığı başına temelinde ayarını destekler. Bu özelliği desteklemek için işlevi _configthreadlocale eklendi.
- _Statusfp2 ve __control87_2 işlevleri için erişim ve denetim noktası denetim sözcüğü hem x87 üzerinde veya SSE2 Yüzen işlemci noktası izin vermek için eklendi.
- The_mkgmtime ve _mkgmtime64 işlevleri (GMT) Greenwich saati (yapısı tm) dönüştürmek için destek sağlamak için eklenmiştir.
- Değişiklikler, standart daha iyi uyacak şekilde swprintf ve vswprintf yapıldı.
- Yeni bir üstbilgi dosyası, INTRIN. H, bazı iç işlevler için prototipleri sağlar.
- Fopen işlevi artık N özniteliğine sahiptir.
- _Open işlevi artık _O_NOINHERIT özniteliğine sahiptir.
- Atoi işlevi artık INT_MAX döndürür ve errno taşmasına ERANGE için ayarlar. Önceki sürümlerde taşma davranışı tanımlanmamış.
- Kayan nokta işlevleri destekler onaltılık printf ailesinin çıktı uygulanan biçim tür tanımlayıcıları kullanarak ANSI C99 standart göre %a ve %A.
- Printf ailesinin artık "tümü" (long long) boyutu önek destekler.
- _Controlfp işlevi daha iyi performans için optimize edilmiştir.
- Bazı işlevler hata ayıklama sürümleri eklenmiştir.
- Eklenen _chgsignl ve _cpysignl (uzun çift sürümler).
- Eklenen _locale_t türü için tablo.
- Yeni makrosu _countof makrosu bir dizideki öğeler, bilgi işlem sayısını eklendi.
- Her işlevi konuya .NET Framework eşdeğerleri bir bölüm eklenmiştir.
- Birkaç dize işlevleri şimdi Çıktı arabelleği çok küçük olduğunda başarısız yerine dizeleri kesilmesiyle seçeneğiniz vardır; _TRUNCATE bakın.
- _set_se_translator şimdi /EHa derleyici seçeneği kullanılmasını gerektirir.
- fpos_t olan şimdi __int64 /Za (için C kodu) altında ve ne zaman __STDC__ (C++ kodunu) el ile ayarlayın. Yapı olması için kullanılır.
- _Crt_dısable_perfcrıt_locks tek iş parçacıklı programlar g/ç performansını artırabilir.
- POSIX adlarını ISO C++ uyumluluğunu adları lehinde (örneğin, kullanım _getch yerine getch) kullanım dışı bırakıldı.
- Yeni bağlantı seçenekleri .obj dosyaları saf modu için kullanılabilir
- _recalloc realloc ve calloc özelliklerini birleştirir.

## <a name="whats-new-for-c-in-visual-studio-2003"></a>C++ Visual Studio 2003'teki yenilikler

### <a name="compiler"></a>Derleyici

- Bir önceki bir çalışma zamanı sürümünde geçerli sürüme ait derleyicisi ile yerleşik C++ uygulaması için Yönetilen Uzantılar çalıştırma hakkında bilgiler.
- Sık sorulan sorular C++ için Yönetilen Uzantılar.
- C++ için Yönetilen Uzantılar kullanmak için varolan, yerel bir uygulama bağlantı noktası nasıl gösteren bir anlatım eklendi: izlenecek yol: .NET Framework bileşenleri ile Interoperate bir var olan yerel C++ uygulamaya taşıma.
- Bu gibi durumlarda, bir temsilci şimdi değer türünün bir yöntem oluşturabilirsiniz.
- C++ Standart derleyicinin uygunluğu Visual C++ .NET 2003'te önemli ölçüde geliştirilmiştir.
- / Yay derleyici seçeneği eklenir.
- /GF kullanım dışıdır ve Visual C++ bir sonraki sürümde kaldırılacak.
- / G7 derleyici seçeneği eklenir.
- /GS derleyici seçeneği, yerel değişkenleri doğrudan arabellek taşmaları korunmasına yardımcı olmak için geliştirilmiştir.
- /NoBool derleyici seçeneği kaldırılmıştır. Derleyici bir C++ kaynak kodu dosyasına artık yalnızca bir anahtar sözcüğü (ve bir tanımlayıcı) görünmesini bool izin verir.
- Long long türünde typedef unutmayın henüz destek CRT'deki uzun uzun __int64 biri olarak kullanıma sunulmuştur.
- /Zm derleyici seçeneği artık önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir.
- _InterlockedCompareExchange iç, artık belgelenmiş.
- _InterlockedDecrement iç, artık belgelenmiş.
- _InterlockedExchange iç, artık belgelenmiş.
- _Interlockedexchangeadd iç, artık belgelenmiş.
- _InterlockedIncrement iç, artık belgelenmiş.
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

. SAFESEH yönergesi ve SAFESEH ml.exe seçeneği eklenmiştir.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)
