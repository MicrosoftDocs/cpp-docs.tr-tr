---
title: "Visual C++ &#39; teki 2015 aracılığıyla yeni 2003 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 512665a243a0c24c143242084a51f6b3025c1a19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Visual C++ &#39; teki 2015 aracılığıyla yeni 2003

**Not** Visual Studio 2017 hakkında daha fazla bilgi için bkz: [Visual Studio 2017'de Visual C++ yenilikleri](../what-s-new-for-visual-cpp-in-visual-studio.md) ve [uygunluk Visual Studio 2017'de Visual C++ yenilikleri](../cpp-conformance-improvements-2017.md).

Visual C++ 2015 ve daha sonra devam eden iyileştirmeler derleyici uyumluluğu bazen derleyici mevcut kaynak kodunuzu nasıl anlar değiştirebilirsiniz. Bu gerçekleştiğinde, yapı veya önceden oluşturulmuş ve düzgün çalışmasına görünüyor kodu dahi davranış farklılıkları sırasında yeni ya da farklı hatalarla karşılaşabilirsiniz.  
  
 Neyse ki, bu farklılıklar çok az kayıpla veya hiç kaynak kodunuzu çoğunu üzerinde etkisi ve kaynak kodu veya başka değişiklikler bu farklılıklar gidermenin gerekli olduğunda, düzeltmeleri genellikle küçük ve düz ilet. Birçok değiştirilmesi gerekebilir önceden kabul edilebilir kaynak kod örnekleri dahil ettiğiniz *(önce)* ve bunları düzeltmek için düzeltmeler *(sonra)*.  
  
 Bu farklılıklar, kaynak kodu veya diğer yapı yapıları etkileyebilir karşın, bunların Visual C++ sürümleri için güncelleştirmeler arasında ikili uyumluluğu etkilemez. Değişiklik, daha ciddi bir tür *değişiklik çiğnemekten* ikili uyumluluğu etkileyebilir, ancak bu tür bir ikili uyumluluğu sonlarını yalnızca Visual C++ ana sürümleri arasında oluşur. Örneğin, Visual C++ 2013 ve Visual C++ 2015 arasında. Visual C++ 2013 ve Visual C++ 2015 arasında oluştu önemli değişiklikler hakkında daha fazla bilgi için bkz: [Visual C++ değişiklik geçmişini 2003 2015](../porting/visual-cpp-change-history-2003-2015.md).  
  
-   [Visual C++ 2015 uyumluluğu yenilikleri](#VS_RTM)  
  
-   [Güncelleştirme 1 uygunluk yenilikleri](#VS_Update1)  
  
-   [Güncelleştirme 2 uygunluk yenilikleri](#VS_Update2)  
  
-   [Güncelleştirme 3 uygunluk yenilikleri](#VS_Update3)  
  
##  <a name="VS_RTM"></a>Visual C++ 2015 uyumluluğu yenilikleri  
  
-   /ZC:forScope-seçeneği  
  
     Derleyici seçeneği **/Zc:forScope-** kullanım dışıdır ve gelecek sürümde kaldırılacak.  
  
    ```  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     Seçeneği genellikle kullanır, burada, standart göre kullanıcılar fazlası kapsam dışında noktadan sonra değişkenleri döngü standart olmayan kod izin vermek üzere kullanıldı. /Za bu yana /Za seçeneğiyle derlediğiniz zaman yalnızca gerekli kullanarak bir döngü sonundan her zaman izin sonra döngü değişkeni için. (Örneğin, kodunuzu diğer derleyiciler için taşınabilir tasarlanmamıştır) standartları uyumluluğu hakkında önemli değil, /Za seçeneğini devre dışı bırakın (veya dil uzantılarını devre dışı bırakma özelliğini Hayır olarak ayarlayın). Taşınabilir, standartlara uygun kod yazma hakkında dikkat edin, böylece bu değişkenleri bildirimi döngü dışında bir nokta taşıyarak standardına uygun kodunuzu yeniden yazma.  
  
    ```  
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
  
-   **/ZG derleyici seçeneği**  
  
     /Zg derleyici seçeneği (işlev prototipleri oluşturma), artık mevcut değil. Bu derleyici seçeneği önceden kullanımdan kaldırılmıştır.  
  
-   Artık birim testleri C + ile çalıştırabilirsiniz +/ CLI mstest.exe ile komut satırından. Bunun yerine, vstest.console.exe kullanın. Bkz: [VSTest.Console.exe komut satırı seçenekleri](/devops-test-docs/test/vstest-console-exe-command-line-options).  
  
-   **mutable anahtar sözcüğü**  
  
     `mutable` Depolama sınıfı tanımlayıcısı burada önceden derlenmiş hatasız yerlerde artık verilir. Derleyici Hatası C2071 şimdi verir (geçersiz depolama sınıfı). Standart göre değişebilir tanımlayıcı yalnızca sınıfı veri üyesi adlarına uygulanabilir ve const veya statik bildirilen adlarına uygulanamaz ve üyeleri başvurmak için uygulanamaz.  
  
     Örneğin, aşağıdaki kodu göz önünde bulundurun:  
  
    ```  
    struct S {  
        mutable int &r;  
    };  
    ```  
  
     Visual C++ derleyicisi önceki sürümlerinde bu kabul ancak şimdi derleyici aşağıdaki hata verir:  
  
    ```Output  
    error C2071: 'S::r': illegal storage class  
    ```  
  
     Hatayı düzeltmek için basitçe yedekli mutable anahtar sözcüğü kaldırın.  
  
-   **char_16_t ve char32_t**  
  
     Artık kullanabilirsiniz `char16_t` veya `char32_t` bir typedef adlarda olarak çünkü bu türleri artık yerleşik kabul edilir. Kullanıcılar ve char16_t ve char32_t uint16_t ve uint32_t, diğer adlar sırasıyla tanımlamak için kitaplık yazarları için ortak.  
  
    ```  
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
  
-   **Tür olmayan şablon parametreleri**  
  
     Açık şablon değişkenlerini sağladığınızda tür olmayan şablon parametreleri içeren belirli kod artık doğru türü uyumluluk için kontrol edilir. Visual C++'ın önceki sürümlerinde hatasız derlenmiş Örneğin, aşağıdaki kodu.  
  
    ```  
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
  
-   **__declspec(align)**  
  
     Derleyici artık kabul `__declspec(align)` işlevlerde. Bu her zaman gözardı edildi ancak şimdi bir derleyici hatası oluşturur.  
  
    ```  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     Bu sorunu gidermek için kaldırın `__declspec(align)` işlev bildirimi gelen. Herhangi bir etkisi sahip olduğundan, kaldırarak herhangi bir şeyi değiştirmez.  
  
-   **Özel durum işleme**  
  
     Birkaç özel durum işleme için değişiklik vardır. İlk olarak, özel durum nesneleri copyable veya taşınabilir olması gerekir. Aşağıdaki kod derlenmiş [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], ancak içinde derlenmiyor [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:  
  
    ```  
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
  
    ```  
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
  
    ```  
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
  
    ```  
    catch(D& d)  
    {  
    }  
    ```  
  
-   **Makroları tarafından izlenen dize değişmez değerleri**  
  
     Derleyici artık kullanıcı tanımlı değişmez değerler destekler. Dize değişmez değerleri müdahalede bulunan tüm boşluk olmadan makroları ve ardından hataları veya beklenmeyen sonuçlara neden, kullanıcı tanımlı değişmez değerler, sonuç olarak yorumlanır. Örneğin, aşağıdaki kod önceki derleyicileri başarıyla derlenmiş:  
  
    ```  
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
  
    ```  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found  
    note: Did you forget a space between the string literal and the prefix of the following string literal?  
  
    ```  
  
     Bu sorunu gidermek için dize sabit değeri ile makrosu arasında bir boşluk ekleyin.  
  
-   **Bitişik dize değişmez değerleri**  
  
     Benzer şekilde önceki, dizesini ayrıştırma, ilgili değişiklikler nedeniyle hiçbir boşluk olmadan bitişik dize değişmez değerleri (ya da geniş veya dar karakteri dize değişmez değerleri) tek bir birleştirilmiş dizeyi Visaul C++ önceki sürümlerinde yorumlanan. İçinde [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], artık iki dizeyi arasında boşluk eklemeniz gerekir. Örneğin, aşağıdaki kodu değiştirilmelidir:  
  
    ```  
    char * str = "abc""def";  
    ```  
  
     Bir alanı arasında iki dize eklemeniz yeterlidir.  
  
    ```  
    char * str = "abc" "def";  
    ```  
  
-   **Yeni yerleştirme ve silme**  
  
     Bir değişiklik delete işleci ilkelerinizle uyumlu C ++ 14 standart getirmek için yapılmıştır. Standartlar değişiklik ayrıntılarını bulunabilir [C++ boyutta ayırmayı kaldırma](http://isocpp.org/files/papers/n3778.html). Değişiklikleri boyutu parametresi alan genel delete işleci biçiminde ekleyin. (Yerleştirme yeni işleciyle karşılık gelecek şekilde) aynı imzayla daha önce bir delete işleci kullanıyorsanız, derleyici hatası alırsınız sonu değişikliktir (burada yeni yerleştirme kullanılır, beri noktada oluşur C2956 o kod derleyici burada uygun eşleşen tanımlamayı dener konumda delete işleci).  
  
     İşlev `void operator delete(void *, size_t)` edildi yerleştirme yeni işlev için karşılık gelen bir yerleştirme delete işleci "void \* new işleci (size_t, size_t)" C ++ 11. C ++ 14 boyutlu ayırmayı kaldırma ile bu silme işlevi sunulmuştur bir *normal ayırmayı kaldırma işlevi* (genel delete işleci). Standart bir yerleştirme yeni kullanımını karşılık gelen bir silme işlevini arar ve her zamanki ayırmayı kaldırma işlevi bulur, program hatalı oluşturulmuş olmasını gerektirir.  
  
     Örneğin, kodunuzu yeni bir yerleştirme ve yerleştirme delete tanımlar varsayın:  
  
    ```  
    void * operator new(std::size_t, std::size_t);  
    void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     Sorun, tanımladığınız yerleştirme delete işleci yeni küresel ölçekli delete işleci arasındaki işlevi imzaları eşlemesinde nedeniyle oluşur. Farklı bir tür size_t dışındaki tüm yerleştirme için yeni kullanmak ve delete işleçleri olup olmadığını göz önünde bulundurun.  Size_t typedef türünü derleyici bağımlı olduğunu unutmayın; Visual C++'ta imzasız int için typedef olur. Bu gibi bir enum türü kullanmak iyi bir çözümdür:  
  
    ```  
    enum class my_type : size_t {};  
  
    ```  
  
     Ardından, yerleştirme yeni tanımınız değiştirebilir ve bu tür size_t yerine ikinci bağımsız değişken olarak kullanmak için silebilirsiniz. Ayrıca yeni türü geçirmek için yeni yerleştirme çağrıları güncelleştirmeniz gerekir (kullanarak örneğin, `static_cast<my_type>` tamsayı değerini dönüştürmek için) ve tanımını yeni güncelleştirme ve tamsayı türüne yayınlanamıyor silin. Bunun için bir numaralandırma kullanmanız gerekmez; sınıf türü size_t üyesi ile de çalışır.  
  
     Bir alternatif yeni yerleştirme tamamen ortadan kaldırmak mümkün olabilir çözümüdür. Kodunuzu yerleştirme yeni burada yerleştirme bağımsız değişkeni olan nesne boyutunu tahsis edilen veya silinen, sonra boyutlu ayırmayı kaldırma özelliği, kendi özel bellek havuzu kodunuzu değiştirmek uygun olabilir ve, elden çıkarabilirsiniz bellek havuzundaki uygulamak için kullanıyorsa, yerleştirme işlevler ve yalnızca kendi iki bağımsız değişken delete işleci yerine yerleştirme işlevlerini kullanın.  
  
     Kodunuzu hemen güncelleştirmek istemiyorsanız, derleyici seçeneği /Zc:sizedDealloc-kullanarak eski davranışa geri dönebilirsiniz. Bu seçeneği kullanırsanız, iki bağımsız değişken silme işlevleri mevcut değil ve yerleştirme delete operatörünüze ile bir çakışma neden olmaz.  
  
-   **Birleşim veri üyeleri**  
  
     Veri üyeleri birleşimler artık başvuru türleri olabilir. Başarıyla derlenen aşağıdaki kod [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], ancak bir hata üretir [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  
  
    ```  
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
  
-   Anonim birleşimler için standart daha fazla uyumluluğunu sunulmuştur. Derleyici önceki sürümlerini bir açık oluşturucu ve yıkıcı anonim birleşimler için oluşturulur. Bunlar de silinir [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  
  
    ```  
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
  
    ```  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function  
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     Bu sorunu çözmek için kendi tanımları oluşturucusu ve/veya yıkıcı sağlayın.  
  
    ```  
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
  
-   **Anonim yapılar ile birleşimler**  
  
     Standart uygun için anonim yapılar Birleşimlerdeki üyeleri için çalışma zamanı davranışı değişmiştir. Bu tür bir birleşim oluşturulduğunda UNION anonim yapısı üyeleri Oluşturucusu artık dolaylı olarak adlandırılır. Ayrıca, UNION kapsam dışına çıktığında yıkıcı bir birleşim anonim yapısı üyeler için artık dolaylı olarak adlandırılır. UNION U yıkıcı sahip adlandırılmış bir yapı S olan bir üyeyi içeren bir anonim yapısı içeren aşağıdaki kod, göz önünde bulundurun.  
  
    ```  
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
  
    ```  
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
  
    ```  
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
  
-   **Şablon çözümleme**  
  
     Şablonlar için ad çözümlemesi için değişiklikler yapıldı. Bir ad çözümlemesi için aday değerlendirirken C++'da, göz önünde bulundurarak olası eşleşmeler olarak bir veya daha fazla adlarla geçersiz şablonu örneklemesi üreten durumda olabilir. Bu geçersiz örneklemesi normalde derleyici hataları, SFINAE (değiştirme hatası olmayan bir hata) bilinen bir ilkeye neden olmaz.  
  
     Şimdi, bir sınıf şablonu uzmanlaşması örneği oluşturmak için derleyici SFINAE gerektirir, bu işlem sırasında oluşan hataları derleyici hataları demektir. Önceki sürümlerde derleyici böyle hataları yoksayma. Örneğin, aşağıdaki kodu göz önünde bulundurun:  
  
    ```  
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
  
-   **Kopya oluşturucuları**  
  
     Hem de [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] ve Visual Studio 2015 derleyici oluşturan bir sınıf için bir kopya Oluşturucu bu sınıfın bir kullanıcı tarafından tanımlanan taşıma oluşturucusuna ancak hiçbir kullanıcı tarafından tanımlanan kopya Oluşturucu varsa. Dev14 içinde bu örtük olarak oluşturulmuş kopya Oluşturucu de işaretlenmiş "delete =".  
  
##  <a name="VS_Update1"></a>Güncelleştirme 1 uygunluk yenilikleri  
  
-   **Özel sanal taban sınıflar ve dolaylı devralma**  
  
     Derleyici önceki sürümlerini izin üye işlevlerini çağırın türetilmiş bir sınıf kendi *dolaylı olarak türetilmiş* `private virtual` temel sınıflar. Bu eski davranış yanlış ve C++ Standart uygun değil. Derleyici artık bu şekilde yazılan kod kabul eder ve derleyici hatası C2280 sonuç olarak verir.  
  
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
  
    ```  
    class base;  // as above  
  
    class middle: private virtual base {};  
    class top: public virtual middle, private virtual bottom {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
-   **New işleci aşırı yüklenmiş ve delete işleci**  
  
     Derleyici önceki sürümlerini izin üyesi olmayan `operator new` ve üye olmayan `operator delete` statik bildirilmesi ve ad alanları genel ad alanı dışında bildirilmesi için.  Bu eski davranış oluşturulan program çağrılmayan risk `new` veya `delete` sessiz hatalı çalışma zamanı davranışını elde edilen Programcı hedeflenen işleci uygulama. Derleyici artık bu şekilde yazılan kod kabul eder ve bunun yerine derleyici hatası C2323 sorunları.  
  
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
  
     Derleyici belirli bir tanılama vermediğinin rağmen ek olarak, yeni satır içi işleci bozuk biçimli olarak kabul edilir.  
  
-   **Çağırma ' işleci *türü*() ' (kullanıcı tanımlı dönüştürme) sınıfı olmayan türler**  
  
     İzin verilen Derleyici önceki sürümlerini ' işleci *türü*() ' sınıfı olmayan türlerinde sessizce yoksayılıyor sırasında çağrılabilir. Bu eski davranış sessiz hatalı kod oluşturmasına, öngörülemeyen çalışma zamanı davranışını kaynaklanan riski oluşturulmuş. Derleyici artık bu şekilde yazılan kod kabul eder ve bunun yerine derleyici hatası C2228 sorunları.  
  
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
  
-   **Yedek typename içinde ayrıntılandırılmış tür tanımlayıcıları**  
  
     İzin verilen Derleyici önceki sürümlerini `typename` ayrıntılandırılmış tür tanımlayıcıları; bu şekilde yazılan kod anlamsal olarak geçersiz. Derleyici artık bu şekilde yazılan kod kabul eder ve bunun yerine derleyici hatası C3406 sorunları.  
  
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
  
-   **Bir başlatıcı listesinden dizi türü kesintisi**  
  
     Derleyici önceki sürümlerini bir başlatıcı listesinden dizi türü kesintisi desteklememektedir. Derleyici şimdi türü kesintisi bu biçimini destekler ve sonuç olarak, başlatıcı listeleri kullanarak işlev şablonları çağrıları şimdi belirsiz olabilir veya farklı bir aşırı daha Derleyici önceki sürümlerde seçilmesi. Bu sorunları gidermek için program şimdi açıkça Programcı hedeflenen aşırı belirtmeniz gerekir.  
  
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
  
-   **Switch deyimi uyarılar geri yükleme**  
  
     Önceden varolan uyarılarla ilgili Derleyici önceki sürümü kaldırılıyor `switch` deyimleri; bunlar uyarılar şimdi geri yüklendi. Derleyici şimdi geri yüklenen uyarıları sorunları ve belirli durumlarda (varsayılan durumu dahil) ilgili uyarılar şimdi soruna neden olan durum içeren satırı yerine switch deyimi son satırının verilir. Sonuç olarak bu uyarılar farklı satırlarındaki geçmişte şimdi veren, uyarıları daha önce gizlenen kullanarak `#pragma warning(disable:####)` tasarlandığı gibi artık gizlenen. Bu uyarılar tasarlandığı gibi gizlemek için bu taşımak gerekli olabilir `#pragma warning(disable:####)` ilk olası sorunlu çalışması üstüne bir çizgi yönergesi. Geri yüklenen uyarılar verilmiştir.  
  
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
  
-   **#include: üst dizini tanımlayıcısı kullanın '..' pathname içinde** (yalnızca wln /WX etkiler)  
  
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
  
-   **#pragma optimize() genişletir üstbilgi dosyası sonunun** (yalnızca wln /WX etkiler)  
  
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
  
-   **#Pragma warning(push) eşleşmeyen** ve **#pragma warning(pop)** (yalnızca wln /WX etkiler)  
  
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
  
-   **Eşleşmeyen #pragma warning(push)** (yalnızca wln /WX etkiler)  
  
     Derleyici önceki sürümlerini algılamadı eşleşmeyen `#pragma warning(push)` durum değişiklikleri çeviri birim sonunda. Derleyici şimdi algılar ve bu şekilde yazılan kod Programcı bildirir ve C5032 eşleşmeyen #pragma warning(push) konumda uyarı isteğe bağlı bir derleyici etkinleştirilirse sorunları. Bu uyarı, yalnızca çeviri biriminde hiç derleme hatası olması durumunda görüntülenir.  
  
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
  
-   **Ek uyarı sonucu olarak geliştirilmiş #pragma uyarı durumu izleme verilebilecek**  
  
     Derleyici önceki sürümlerinden de sorun için yeterince uyarı tüm uyarılar yönelik durum değişiklikleri #pragma izlenir. Bu davranış, uyarıları etkin hedeflenen Programcı farklı durumlarda atlanması, belirli bir risk oluşturulur. Derleyici şimdi #pragma uyarısı durumunu daha yerine--#pragma uyarısı durum değişiklikleri şablonları içinde--özellikle ilgili izler ve isteğe bağlı olarak istenmeyenkullanımlarınıbulunProgramcıyardımcıolmaküzeretasarlanmıştıryeniuyarılarC5031veC5032sorunları`#pragma warning(push)` ve `#pragma warning(pop)`.  
  
     Sonucu olarak geliştirilmiş #pragma durumu değişiklik izleme, eskiden yanlış gizlenen uyarılar veya önceden misdiagnosed sorunlarıyla ilgili uyarılar uyarı artık verilebilir.  
  
-   **Geliştirilmiş kimlik ulaşılamaz kod**  
  
     C++ Standart Kitaplığı değişiklikleri ve satır içi işlev çağrılarını Derleyici önceki sürümlerini üzerinden geliştirilmiş yeteneği belirli kod ulaşılamaz olduğunu kanıtlamak derleyici izin verebilir. Bu yeni davranış yeni ve daha sık uyarı C4720 örneklerini verilen sonuçlanabilir.  
  
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
  
##  <a name="VS_Update2"></a>Güncelleştirme 2 uygunluk yenilikleri  
  
-   **Kısmi ifade SFINAE desteği sonucunda ek uyarıları ve hataları verilebilecek**  
  
     Derleyici önceki sürümlerini ifadelerinin içinde belirli bir türde değil ayrıştırma `decltype` tanımlayıcıları ifade SFINAE desteği eksikliği nedeniyle. Bu eski davranış yanlış ve C++ Standart uygun değil. Derleyici şimdi bu deyimler ayrıştırır ve kısmi ifade SFINAE devam eden uygunluk geliştirmeleri nedeniyle desteği sahiptir. Sonuç olarak, derleyici uyarıları şimdi sorunları ve derleyici önceki sürümleri olmayan incelenemedi ifadelerinde hatalar bulundu.  
  
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
  
-   `volatile`**üye değişkenleri önlemek örtük olarak tanımlanan oluşturucuları ve atama işleçleri**  
  
     Derleyici önceki sürümlerini izin olan bir sınıfı `volatile` varsayılan üye değişkenleri copy/move oluşturucular ve kopyalama/taşıma atama işleçleri otomatik olarak oluşturulan varsayılan. Bu eski davranış yanlış ve C++ Standart uygun değil. Derleyici artık otomatik olarak oluşturulan varsayılan uygulamaları bu işleçlerinin önleyen volatile üye değişkenleri Önemsiz olmayan yapım ve atama işleçleri sahip olan bir sınıfı göz önünde bulundurur.  Böyle bir sınıfın UNION (veya bir sınıf içinde anonim bir birleşimi) bir üyesi olduğunda, copy/move oluşturucuları ve kopya/taşıma atama işleçleri UNION (veya unonymous UNION içeren sınıf) örtük olarak silindi olarak tanımlanır. Oluşturmak veya bunları açıkça tanımlamadan UNION (veya anonim UNION içeren sınıf) kopyalamak çalışırken bir hata derleyici sorunları derleyici hatası C2280 sonucunda ise.  
  
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
  
-   **Statik üye işlevleri MS niteleyicileri desteklemez.**  
  
     Visual C++ 2015 önceki sürümlerini MS niteleyicileri sağlamak statik üye işlevleri izin verilir. Visual C++ 2015 ve Visual C++ 2015 güncelleştirme 1'teki bir gerileme nedeniyle bu davranışı değildir; Visual C++ 2013 ve Visual C++'ın önceki sürümlerinde bu şekilde yazılan kod reddeder. Visual C++ 2015 ve Visual C++ 2015 güncelleştirme 1 davranışını yanlış ve standart C++ için uygun değil.  Visual Studio 2015 güncelleştirme 2 Bu şekilde yazılan kod reddeder ve bunun yerine derleyici hatası C2511 verir.  
  
    ```Output  
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'  
    ```  
  
     Örnek (önce)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() const {}  // C2511  
  
    ```  
  
     Örnek (sonra)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() {}  // removed const  
  
    ```  
  
-   **Enum ileriye dönük bildirimi WinRT kodu izin verilmeyen** (/ZW yalnızca etkiler)  
  
     Windows çalışma zamanı (WinRT) izin vermediği için derlenmiş kod `enum` yönetilen C++ kodu için .net derlendiğinde İleri, benzer şekilde belirtilecek türleri çerçevesi/CLR derleyici kullanılarak geçin. Bu davranış olduğu numaralandırma boyutu her zaman bilinir ve doğru şekilde WinRT türü sisteme öngörülen sağlar. Derleyici bu şekilde yazılan kod reddeder ve derleyici hatası C2599 derleyici hatası C3197 birlikte verir.  
  
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
  
-   **Aşırı yüklenmiş üye olmayan işleci yeni ve delete işleci bildirilmemiş satır içi** (düzey 1 (/ W1) üzerinde tarafından-varsayılan)  
  
     Satır içi yeni üye olmayan işleci ve işleci silme işlevleri bildirirken Derleyici önceki sürümlerini bir uyarı vermek değil. Bu şekilde yazılan kodu bozuk biçimli (tanılama gerekli) ve kaynaklanan sorunlar yeni eşleşmeyen ve tanılamak zor olabilir (özellikle boyutlu ayırmayı kaldırma ile birlikte kullanıldığında) işleçleri silmek bellek neden olabilir.   Derleyici şimdi derleyici C4595 bu şekilde yazılan kod tanımlamaya yardımcı olmak üzere Uyarı yayınlar.  
  
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
  
##  <a name="VS_Update3"></a>Güncelleştirme 3 uygunluk yenilikleri  
  
-   **Std::is_convertable otomatik atanmasını artık algılar** (standart kitaplığı)  
  
     Önceki sürümlerini `std::is_convertable` türü ayırdedici nitelik kopya kurucusu silindiğinde bir sınıf türünün otomatik atanmasını veya özel doğru algılamadı. Şimdi, `std::is_convertable<>::value` doğru bir şekilde ayarlamak `false` bir sınıf türü silindiğinde veya özel kopya Oluşturucu ile uygulandığında.  
  
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
  
-   **Varsayılan veya önemsiz kopya silinir ve oluşturucular saygı erişim tanımlayıcıları taşıyın**  
  
     Derleyici önceki sürümlerini değil varsayılan veya silinen Önemsiz kopyasının erişim belirticisi denetleyin ve bunları çağrılmasına izin vermeden önce oluşturucular taşıyın. Bu eski davranış yanlış ve C++ Standart uygun değil. Bazı durumlarda, bu eski davranış sessiz hatalı kod oluşturmasına, öngörülemeyen çalışma zamanı davranışını kaynaklanan riski oluşturulur. Derleyici şimdi varsayılan veya silinen Önemsiz kopyasının erişim belirticisi denetler ve onu çağrılabilir olup olmadığını ve değilse, C2248 sonucunda uyarı sorunları derleyici olmadığını belirlemek için oluşturucular taşıyın.  
  
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
  
-   **Öznitelik atanmış ATL kodu desteğini kullanımdan** (düzey 1 (/ W1) üzerinde tarafından-varsayılan)  
  
     Desteklenen Derleyici önceki sürümlerini ATL kodu öznitelikli. Öznitelik atanmış ATL desteğini kaldırmanın sonraki aşaması olarak, kod [Visual C++ 2008'de başlangıcından](https://msdn.microsoft.com/library/bb384632\(v=vs.90\).aspx), öznitelik atanmış ATL kodu kullanım dışı bırakıldı. Derleyici şimdi derleyici C4467 bu tür kullanım dışı kodu tanımlamaya yardımcı olmak üzere Uyarı yayınlar.  
  
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
  
-   **Önceden Derlenmiş Üstbilgi (PCH) dosyaları ve uyumsuzluğu # yönergeleri include** (yalnızca wln /WX etkiler)  
  
     Derleyici önceki sürümlerini kabul eşleşmeyen `#include` arasındaki kaynak dosyalarında yönergeleri `-Yc` ve `-Yu` kullanırken derlemeleri önceden derlenmiş üstbilgi (PCH) dosyaları. Bu şekilde yazılan kod artık derleyici tarafından kabul edilir.   Tanımlamaya yardımcı olmak üzere CC4598 uyarı sorunları derleyici eşleşmeyen artık derleyici `#include` PCH dosyalarını kullanırken yönergeleri.  
  
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
  
-   **Önceden Derlenmiş Üstbilgi (PCH) dosyaları ve uyumsuzluğu içeren dizinler** (yalnızca wln /WX etkiler)  
  
     Kabul Derleyici önceki sürümlerini eşleşmeyen içeren dizin (`-I`) arasındaki derleyici komut satırı bağımsız değişkenleri `-Yc` ve `-Yu` kullanırken derlemeleri önceden derlenmiş üstbilgi (PCH) dosyaları. Bu şekilde yazılan kod artık derleyici tarafından kabul edilir.   Tanımlamaya yardımcı olmak üzere CC4599 uyarı sorunları derleyici eşleşmeyen artık derleyici içeren dizin (`-I`) PCH dosyalarını kullanırken komut satırı bağımsız değişkenleri.  
  
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