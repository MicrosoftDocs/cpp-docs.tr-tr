---
title: C++ konsol uygulama projesi oluşturma
description: Visual üzerinde Merhaba Dünya konsol uygulaması ve Hesaplayıcı uygulaması oluşturmaC++
ms.custom: mvc
ms.date: 08/19/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: ff1b5295f9fefd681ea76d09349415b59ceac1f2
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69631306"
---
# <a name="create-a-c-console-app-project"></a>C++ konsol uygulama projesi oluşturma

::: moniker range=">=vs-2019"

C++ Programcı için olağan başlangıç noktası "Merhaba, Dünya!" komut satırında çalışan uygulama. Bu makalede Visual Studio 'da oluşturacağınız şey, daha zorlayıcı bir işlem hesaplayıcısı: bir Hesaplayıcı uygulaması.

## <a name="prerequisites"></a>Önkoşullar

- Bilgisayarınızda yüklü ve çalışır şekilde çalışan iş yüküyle Visual Studio ile **masaüstü geliştirme C++**  yapın. Henüz yüklenmemişse bkz. [Visual Studio 'da destek yükleme C++ ](../build/vscpp-step-0-installation.md).

## <a name="create-your-app-project"></a>Uygulama projenizi oluşturma

Visual Studio kullanan *projeleri* bir uygulama için kod düzenleme ve *çözümleri* projelerinizi düzenlemek için. Bir proje, tüm seçenekleri, yapılandırmaları ve uygulamalarınızı oluşturmak için kullanılan kuralları içerir. Tüm proje dosyaları ve dış dosyaları arasındaki ilişki da yönetir. Uygulamanızı oluşturmak için önce yeni bir proje ve çözüm oluşturacaksınız.

1. Visual Studio 'yu yeni başlattıysanız, Visual Studio 2019 iletişim kutusunu görürsünüz. Başlamak için **Yeni proje oluştur ' a** tıklayın.

   ![Visual Studio 2019 ilk iletişim kutusu](./media/calc-vs2019-initial-dialog.png "Visual Studio 2019 ilk iletişim kutusu")

   Aksi halde, Visual Studio 'daki menü çubuğundan **Dosya** > **Yeni** > **Proje**' yi seçin. **Yeni proje oluştur** penceresi açılır.

1. Proje şablonları listesinde **konsol uygulaması**' nı seçin ve ardından **İleri**' yi seçin.

   ![Konsol uygulaması şablonunu seçin](./media/calc-vs2019-choose-console-app.png "Konsol uygulaması şablonunu seçin")

   > [!Important]
   > C++ **Konsol uygulaması** şablonunun sürümünü seçtiğinizden emin olun. **C++** , **Windows**ve **konsol** etiketlerine sahiptir ve simgenin köşede "+ +" vardır.

1. **Yeni projenizi yapılandırın** iletişim kutusunda, **Proje adı** düzenleme kutusunu seçin, yeni projenizin hesaplaizi *öğreticisini*adlandırın, sonra **Oluştur**' u seçin.

   ![Yeni projenizi yapılandırma iletişim kutusunda projenizi adlandırın](./media/calc-vs2019-name-your-project.png "Yeni projenizi yapılandırma iletişim kutusunda projenizi adlandırın")

   Boş C++ bir Windows konsol uygulaması oluşturulur. Konsol uygulamaları, çıktıyı göstermek ve Kullanıcı girişini kabul etmek için bir Windows konsol penceresi kullanır. Visual Studio 'da bir düzenleyici penceresi açılır ve oluşturulan kodu gösterir:

    ```cpp
    // CalculatorTutorial.cpp : This file contains the 'main' function. Program execution begins and ends there.
    //

    #include <iostream>

    int main()
    {
        std::cout << "Hello World!\n";
    }

    // Run program: Ctrl + F5 or Debug > Start Without Debugging menu
    // Debug program: F5 or Debug > Start Debugging menu

    // Tips for Getting Started:
    //   1. Use the Solution Explorer window to add/manage files
    //   2. Use the Team Explorer window to connect to source control
    //   3. Use the Output window to see build output and other messages
    //   4. Use the Error List window to view errors
    //   5. Go to Project > Add New Item to create new code files, or Project > Add Existing Item to add existing code files to the project
    //   6. In the future, to open this project again, go to File > Open > Project and select the .sln file
    ```

## <a name="verify-that-your-new-app-builds-and-runs"></a>Yeni uygulamanızın derlemediğini ve çalıştığını doğrulayın

Yeni bir Windows konsol uygulaması şablonu basit C++ bir "Merhaba Dünya" uygulaması oluşturur. Bu noktada, Visual Studio 'Nun IDE 'den doğrudan oluşturduğunuz uygulamaları nasıl oluşturup yürüttüğünde daha fazla bilgi alabilirsiniz.

1. Projenizi derlemek için **derleme** menüsünden **çözüm oluştur** ' u seçin. **Çıkış** penceresi, derleme işleminin sonuçlarını gösterir.

   ![Projeyi derleme](./media/calc-vs2019-build-your-project.png "Projeyi derleme")

1. Kodu çalıştırmak için, menü çubuğunda **Hata Ayıkla**, **hata ayıklama olmadan Başlat**' ı seçin.

   ![Projeyi Başlat](./media/calc-vs2019-hello-world-console.png "Projeyi Başlat")

   Konsol penceresi açılır ve uygulamanızı çalıştırır. Visual Studio 'da bir konsol uygulaması başlattığınızda, kodunuzu çalıştırır ve ardından bu pencereyi kapatmak için herhangi bir tuşa basın. biçimindeki telefon numarasıdır. ." çıktıyı görmeniz için bir şans sağlamak üzere. Tebrikler! İlk "Hello, World!" dosyanızı oluşturdunuz Visual Studio 'da konsol uygulaması!

1. Konsol penceresini kapatmak ve Visual Studio 'ya dönmek için bir tuşa basın.

Artık, kodun beklendiği gibi çalıştığını doğrulamak için her değişiklikten sonra uygulamanızı derleyip çalıştırmaya yönelik araçlara sahipsiniz. Daha sonra, bu değilse nasıl hata ayıklaması yapılacağını göstereceğiz.

## <a name="edit-the-code"></a>Kodu Düzenle

Şimdi bu şablondaki kodu bir Hesaplayıcı uygulamasına açalım.

1. *Hesaplatoröğreticisi. cpp* dosyasında, kodu şu örnekle eşleşecek şekilde düzenleyin:

    ```cpp
    // CalculatorTutorial.cpp : This file contains the 'main' function. Program execution begins and ends there.
    //

    #include <iostream>

    using namespace std;

    int main()
    {
        cout << "Calculator Console Application" << endl << endl;
        cout << "Please enter the operation to perform. Format: a+b | a-b | a*b | a/b"
            << endl;
        return 0;
    }

    // Run program: Ctrl + F5 or Debug > Start Without Debugging menu
    // Debug program: F5 or Debug > Start Debugging menu
    // Tips for Getting Started:
    //   1. Use the Solution Explorer window to add/manage files
    //   2. Use the Team Explorer window to connect to source control
    //   3. Use the Output window to see build output and other messages
    //   4. Use the Error List window to view errors
    //   5. Go to Project > Add New Item to create new code files, or Project > Add Existing Item to add existing code files to the project
    //   6. In the future, to open this project again, go to File > Open > Project and select the .sln file
    ```

   > Kodu anlama:
   >
   > - Deyimleri `#include` , diğer dosyalarda bulunan koda başvuru yapmanıza olanak sağlar. Bazen açılı ayraçlar ( **\<\>** ) ile çevrelenmiş bir dosya adı görebilirsiniz; diğer zamanlarda tırnak işaretleri ( **""** ) ile çevrelenmiş olur. Genel olarak, C++ standart kitaplığa başvurulurken açılı ayraçlar kullanılır, ancak teklifler diğer dosyalar için kullanılır.
   > - Çizgi derleyiciye bu dosyada kullanılan C++ standart kitaplıktan şeyler beklendiğini söyler. `using namespace std;` Bu satır olmadan, bir kitaplıktaki her anahtar sözcüğünün, kapsamını göstermek için önünde bir `std::`ile olması gerekir. Örneğin, bu satır olmadan her başvurunun `cout` olarak `std::cout`yazılması gerekir. Kodun daha temiz görünmesini sağlamak için ifadeeklenir.`using`
   > - Anahtar `cout` sözcüğü, içindeki C++standart çıktıya yazdırmak için kullanılır. **İşleci derleyiciye, standart çıktıya ne olduğunu bildirir. \< \<**
   > - **Endl** anahtar sözcüğü ENTER tuşu gibidir; satırı sonlandırır ve imleci bir sonraki satıra kaydırır. Her zaman arabelleği temizleyerek ve bu çok `\n` küçük `endl` bir uygulama olduğundan, daha iyi bir uygulama olduğundan, dizenin içine (""), aynı şeyi yapmak için bir koymak daha iyi bir uygulamadır. `endl` luğunu.
   > - All C++ deyimlerinin noktalı virgül ile bitmesi ve tüm C++ uygulamaların bir `main()` işlev içermesi gerekir. Bu işlev, programın başlangıçta çalıştığı şeydir. Kullanılabilmesi için tüm koda erişilebilir `main()` olması gerekir.

1. Dosyayı kaydetmek için **CTRL + S**gırın veya IDE 'nin üst kısmına yakın bir şekilde **Kaydet** simgesini, menü çubuğunun altındaki araç çubuğundan disket simgesini seçin.

1. Uygulamayı çalıştırmak için **CTRL + F5** tuşlarına basın veya **hata ayıklama** menüsüne gidin ve **hata ayıklama olmadan Başlat**' ı seçin. Kodda belirtilen metni görüntüleyen bir konsol penceresi görürsünüz.

1. İşiniz bittiğinde konsol penceresini kapatın.

## <a name="add-code-to-do-some-math"></a>Bazı matematik işlemlerini yapmak için kod ekleme

Biraz matematik mantığı ekleme zamanı.

### <a name="to-add-a-calculator-class"></a>Hesaplayıcı sınıfı eklemek için

1. **Proje** menüsüne gidin ve **Sınıf Ekle**' yi seçin. **Sınıf adı** düzenleme kutusuna *Hesaplayıcı*yazın. **Tamam**’ı seçin. Projenize iki yeni dosya eklenir. Değiştirdiğiniz tüm dosyaları aynı anda kaydetmek için **CTRL + SHIFT + S**tuşlarına basın. Bu, **Dosya** > **kaydetme**için bir klavye kısayoludur. Ayrıca, Kaydet düğmesinin yanında bulunan iki disket simgesi olan **Tümünü Kaydet**için bir araç çubuğu düğmesi de vardır. Genel olarak, kaydetme sırasında herhangi bir dosyayı kaçırmamak için sık sık **kaydedilmesi** iyi bir uygulamadır.

   ![Hesaplayıcı sınıfını oluşturma](./media/calc-vs2019-create-calculator-class.png "Hesaplayıcı sınıfını oluşturma")

   Bir sınıf, bir şeyi yapan bir nesne için şema gibidir. Bu durumda, bir Hesaplayıcı ve nasıl çalışması gerektiğini tanımladık. Yukarıda kullandığınız **sınıf ekleme** Sihirbazı, sınıf ile aynı ada sahip. h ve. cpp dosyalarını oluşturdu. Proje dosyalarınızın tam listesini, IDE 'nin yanında görünen **Çözüm Gezgini** penceresinde görebilirsiniz. Pencere görünmüyorsa, menü çubuğundan açabilirsiniz: **Görünüm** > **Çözüm Gezgini**' yi seçin.

   ![Çözüm Gezgini](./media/calc-vs2019-solution-explorer.png "Çözüm Gezgini")

   Düzenleyicide Şu anda üç sekme açık olmalıdır: *Hesaplayıcı Toröğreticisi. cpp*, *Hesaplayıcı. h*ve *Hesaplayıcı. cpp*. Yanlışlıkla bunlardan birini kapatırsanız, **Çözüm Gezgini** penceresinde onu çift tıklayarak yeniden açabilirsiniz.

1. **Hesap makinesi. h**içinde, burada `Calculator();` , `~Calculator();` bunlara ihtiyacınız olmadığından, oluşturulan ve satırları kaldırın. Ardından, dosyanın şimdi şöyle görünmesi için aşağıdaki kod satırını ekleyin:

    ```cpp
    #pragma once
    class Calculator
    {
    public:
        double Calculate(double x, char oper, double y);
    };
    ```

   > Kodu anlama
   >
   > - Eklediğiniz satır, toplama, çıkarma, çarpma ve `Calculate`bölme için matematik işlemlerini çalıştırmak için kullanacağımız yeni bir işlev bildirir.
   > - C++kod, *üstbilgi* (. h) dosyaları ve *kaynak* (. cpp) dosyaları halinde düzenlenir. Çeşitli derleyiciler tarafından desteklenen çeşitli dosya uzantıları şunlardır, ancak bunlar hakkında bilgi sahibi olmak için başlıca değerlerdir. İşlevler ve değişkenler normalde *tanımlanmış*, diğer bir deyişle, bir ad ve tür, başlık dosyalarında, *uygulanan*veya bir tanım verilen kaynak dosyalarında. Başka bir dosyada tanımlanan koda erişmek için, ' filename. `#include "filename.h"`h ' öğesini kullanmak istediğiniz değişkenleri veya işlevleri bildiren dosyanın adı olan ' i kullanabilirsiniz.
   > - Sildiğiniz iki satır, sınıf için bir *Oluşturucu* ve *yıkıcı* bildirdi. Bunun gibi basit bir sınıf için derleyici bunları sizin için oluşturur ve kullanımları Bu öğreticinin kapsamı dışındadır.
   > - Kodunuzu, ne yapacaklarına göre farklı dosyalara düzenlemek iyi bir uygulamadır. bu sayede, daha sonra ihtiyacınız olan kodu kolayca bulabilirsiniz. Bizim örneğimizde, `Calculator` sınıfı `main()` işlevi içeren dosyadan ayrı olarak tanımladık, ancak içinde `Calculator` `main()`sınıfına başvuru planlıyoruz.

1. Altında `Calculate`yeşil renkli bir çizgi görünür. Bunun nedeni, `Calculate` . cpp dosyasında işlevi tanımlamadık. Sözcüğün üzerine gelin, açılan ampule (Bu durumda, bir screwsürücü) tıklayın ve **Hesaplayıcı. cpp ' de ' Calculate ' tanımı oluştur**' u seçin.

   ![Hesaplama tanımı oluştur](./media/calc-vs2019-create-definition.png "Hesaplama tanımı oluştur")

   Diğer dosyada yapılan kod değişikliğinin bir özetini sunan bir açılır pencere görünür. Kod, *Hesaplayıcı. cpp*öğesine eklendi.

   ![Hesaplama tanımıyla açılır pencere](./media/calc-vs2019-pop-up-definition.png "Hesaplama tanımıyla açılır pencere")

   Şu anda yalnızca 0,0 döndürüyor. Bunu değiştirelim. Açılır pencereyi kapatmak için **ESC** tuşuna basın.

1. Düzenleyici penceresindeki *Hesaplayıcı. cpp* dosyasına geçin. Ve bölümlerini kaldırın (. h dosyasında yaptığınız gibi) ve aşağıdaki kodu öğesine `Calculate()`ekleyin: `~Calculator()` `Calculator()`

    ```cpp
    #include "Calculator.h"

    double Calculator::Calculate(double x, char oper, double y)
    {
        switch(oper)
        {
            case '+':
                return x + y;
            case '-':
                return x - y;
            case '*':
                return x * y;
            case '/':
                return x / y;
            default:
                return 0.0;
        }
    }
    ```

   > Kodu anlama
   >
   > - İşlevi `Calculate` bir sayı, bir işleç ve ikinci bir sayı kullanır, ardından istenen işlemi sayılar üzerinde gerçekleştirir.
   > - Switch ifadesinde hangi işlecin sağlandığını kontrol eder ve yalnızca bu işleme karşılık gelen servis talebi yürütülür. Varsayılan: durum, kullanıcının kabul edilmeyen bir işleç yazdığında, dolayısıyla programın kesintiye uğramaması durumunda bir geri dönüş olur. Genel olarak, geçersiz kullanıcı girişini daha zarif bir şekilde işlemek en iyisidir, ancak Bu öğreticinin kapsamı dışındadır.
   > - Anahtar `double` sözcüğü, Onlukları destekleyen bir sayı türünü gösterir. Bu şekilde, hesaplayıcı hem Decimal Math hem de Integer Math işleyebilir. `Calculate` İşlevin ,`double` kodun çok başlangıcında (Bu, işlevin dönüş türünü belirtir), bu nedenle her zaman bir sayının bu tür bir değer döndürmesi gerekir. Bu, varsayılan durumda bile 0,0 getirdiğimiz anlamına gelir.
   > - . H dosyası, derleyicinin hangi parametrelereihtiyacı olduğunu ve bundan beklenen dönüş türünü belirten işlev prototipini bildirir. . Cpp dosyası, işlevin tüm uygulama ayrıntılarına sahiptir.

Kodu bu noktada yeniden oluşturup çalıştırırsanız, hangi işlemin gerçekleştirileceğini soran bir çıkış devam eder. Sonra, bazı hesaplamalar yapmak için `main` işlevini değiştirirsiniz.

### <a name="to-call-the-calculator-class-member-functions"></a>Hesaplayıcı sınıfı üye işlevlerini çağırmak için

1. Şimdi, `main` *hesaplatoröğreticisi. cpp*işlevini güncelleştirelim:

    ```cpp
    // CalculatorTutorial.cpp : This file contains the 'main' function. Program execution begins and ends there.
    //

    #include <iostream>
    #include "Calculator.h"

    using namespace std;

    int main()
    {
        double x = 0.0;
        double y = 0.0;
        double result = 0.0;
        char oper = '+';

        cout << "Calculator Console Application" << endl << endl;
        cout << "Please enter the operation to perform. Format: a+b | a-b | a*b | a/b"
             << endl;

        Calculator c;
        while (true)
        {
            cin >> x >> oper >> y;
            result = c.Calculate(x, oper, y);
            cout << "Result is: " << result << endl;
        }

        return 0;
    }
    ```

   > Kodu anlama
   >
   > - Programlar C++ her zaman `main()` işlevde başladığından, diğer kodumuzu buradan çağırmamız gerekir, bu nedenle bir `#include` ifade gereklidir.
   > - Bazı ilk değişkenler `x` `y` `result` ,, ve sırasıyla ilk Number, İkinci sayı, işleç ve nihai sonucu depolayacak şekilde bildirilmiştir. `oper` Bu, burada yapılan tanımsız davranışlara engel olmak için bazı ilk değerleri vermek her zaman iyi bir uygulamadır.
   > - Satır, `Calculator` sınıfının bir örneği olarak ' c ' adlı bir nesne bildirir. `Calculator c;` Sınıfın kendisi, hesaplayıcıların nasıl çalıştığı hakkında yalnızca bir şema olur; nesnesi, matematik yapan özel Hesaplayıcı ' dır.
   > - `while (true)` İfade bir döngüdür. Döngü içindeki kod, `()` ' ın içindeki koşul doğru olduğu sürece yeniden yürütmeye devam eder. Koşul yalnızca olarak listelendiğinden, her zaman `true`doğru olduğundan, döngü süresiz olarak çalışır. Programı kapatmak için Kullanıcı konsol penceresini el ile kapatması gerekir. Aksi takdirde, program her zaman yeni giriş bekler.
   > - `cin` Anahtar sözcüğü, kullanıcıdan girişi kabul etmek için kullanılır. Bu giriş akışı, konsol penceresinde girilen bir metin satırını işlemek için yeterince akıllı bir işlemdir ve Kullanıcı girişinin gerekli belirtile eşleştiğini varsayarak, listelenen değişkenlerin her birini sırayla yerleştirebilirsiniz. Bu satırı, örneğin iki sayıdan fazla farklı giriş türlerini kabul etmek için değiştirebilir, ancak `Calculate()` işlevin bunu işlemek için de güncelleştirilmeleri gerekir.
   > - İfade, daha önce `Calculate` tanımlanan işlevi çağırır ve girilen giriş değerlerini sağlar. `c.Calculate(x, oper, y);` İşlev daha sonra ' de `result`depolanan bir sayı döndürür.
   > - `result` Son olarak konsola yazdırılır, böylece Kullanıcı hesaplamanın sonucunu görür.

### <a name="build-and-test-the-code-again"></a>Kodu yeniden derleyin ve test edin

Artık, her şeyin düzgün çalıştığından emin olmak için programı yeniden test etme zamanı.

1. Uygulamayı yeniden oluşturmak ve başlatmak için **CTRL + F5** tuşlarına basın.

1. Yazın `5 + 5`ve ENTER tuşunabasın. Sonucun 10 olduğunu doğrulayın.

   ![5 + 5 sonucu](./media/calc-vs2019-five-plus-five.png "5 + 5 sonucu")

## <a name="debug-the-app"></a>Uygulamada hata ayıklama

Kullanıcı konsol penceresine herhangi bir şey yazmadığından ücretsiz olduğundan, hesap makinesinin bazı girişleri beklendiği gibi işlemesini sağlayın. Programı çalıştırmak yerine, bunun yerine hata ayıklaalım, bu nedenle ne yaptığını ayrıntılı olarak inceleyebileceğiniz adım adım.

### <a name="to-run-the-app-in-the-debugger"></a>Uygulamayı hata ayıklayıcıda çalıştırmak için

1. Yalnızca kullanıcıdan giriş sorulduktan `result = c.Calculate(x, oper, y);` sonra, satırda bir kesme noktası ayarlayın. Kesme noktasını ayarlamak için, düzenleyici penceresinin sol kenarındaki gri dikey çubukta bulunan çizgiye tıklayın. Kırmızı bir nokta görünür.

   ![Bir kesme noktası ayarlamak](./media/calc-vs2019-set-breakpoint.png "bir kesme noktası ayarlayın")

   Artık programda hata ayıklaması yaptığımız zaman, bu satırdaki yürütmeyi her zaman duraklatır. Programın basit durumlar için çalışmasına yönelik kaba bir fikrimiz zaten var. Yürütmeyi her seferinde duraklatmak istemediğimiz için, kesme noktasını koşullu hale getirir.

1. Kesme noktasını temsil eden kırmızı noktaya sağ tıklayın ve **koşullar**' ı seçin. Koşulun düzenleme kutusunda, girin `(y == 0) && (oper == '/')`. İşiniz bittiğinde **Kapat** düğmesini seçin. Koşul otomatik olarak kaydedilir.

   ![Koşullu kesme noktası ayarlama](./media/calc-vs2019-conditional-breakpoint.png "Koşullu kesme noktası ayarlama")

   Artık 0 olarak bölme denendiğinde yürütme kesme noktasında yürütmeyi durakladık.

1. Programda hata ayıklamak için **F5**'e basın veya yeşil ok simgesine sahip olan **yerel Windows hata ayıklayıcısı** araç çubuğu düğmesini seçin. Konsol uygulamanızda, "5-0" gibi bir şey girerseniz, program normal şekilde davranır ve çalışır durumda kalır. Ancak, "10/0" yazarsanız, kesme noktasında duraklatılır. Operatör ve rakamlar arasında da herhangi bir sayıda boşluk koyabilirsiniz: `cin` girişi uygun şekilde ayrıştırmaya yetecek kadar akıllı bir değer.

   ![Koşullu kesme noktasında Duraklat](./media/calc-vs2019-debug-breakpoint.png "Koşullu kesme noktasında Duraklat")

### <a name="useful-windows-in-the-debugger"></a>Hata ayıklayıcıda yararlı pencereler

Kodunuzda hata ayıkladığınızda, bazı yeni pencerelerin göründüğünü fark edebilirsiniz. Bu pencereler hata ayıklama deneyiminize yardımcı olabilir. **Oto** penceresine göz atın. **Oto** penceresinde, geçerli satıra en az üç satır önce kullanılan değişkenlerin geçerli değerlerini gösterir. Bu işlevden tüm değişkenleri görmek için **Yereller** penceresine geçin. Bu değişkenlerin değerlerini hata ayıklama sırasında değiştirebilir ve programda neler olacağını görebilirsiniz. Bu durumda, bunları tek başına bırakacağız.

   ![Yereller penceresi](./media/calc-vs2019-debug-locals.png "Yereller penceresi")

Ayrıca, yürütmenin Şu anda duraklatıldığı geçerli değerlerini görmek için yalnızca kodun kendisindeki değişkenlerin üzerine gelebilmeniz gerekir. Önce üzerine tıklayarak düzenleyici penceresinin odaklandığından emin olun.

   ![Geçerli değişken değerlerini görüntülemek Için üzerine gelin](./media/calc-vs2019-hover-tooltip.png "Geçerli değişken değerlerini görüntülemek Için üzerine gelin")

### <a name="to-continue-debugging"></a>Hata ayıklamaya devam etmek için

1. Sol taraftaki sarı çizgi, geçerli yürütme noktasını gösterir. Geçerli satırı çağırır `Calculate`, bu nedenle işlev **içine** dönmek için **F11** tuşuna basın. Kendi kendinize `Calculate` işlevin gövdesinde bulacaksınız. **Adımla**ilgili dikkatli olun; Bunu çok fazla yaparsanız, çok sayıda atık hale gelebilir. Standart Kitaplık işlevleri dahil olmak üzere, üzerinde olduğunuz satırda kullandığınız herhangi bir koda gider.

1. Yürütme noktası `Calculate` işlevin başlangıcında olduğuna göre, program yürütmesinin sonraki satırına geçmek için **F10** tuşuna basın. **F10** , **adım adım**olarak da bilinir. Satırdaki her bir bölümde gerçekleşdiklerin ayrıntılarına odaklanmadan satırdan satıra geçiş yapmak için **Step Over** ' u kullanabilirsiniz. Genel olarak, başka bir yerde Çağrılmakta olan kodu daha ayrıntılı bir şekilde incelemek istemediğiniz sürece (' ın `Calculate`gövdesine ulaştığınız gibi) daha fazla bilgi almak istiyorsanız, ' ın **içine adımla**yerine **adımını** kullanmanız gerekir.

1. Diğer `main()` dosyadakiişlevegeridönüpsatırüzerindeduranakadarherbirsatırdaadımadımilerleyin.`cout`

   Program beklenildiği gibi görünüyor: ilk sayıyı alır ve ikinciden böler. Satırda, `result` değişkenin üzerine gelin `result` veya oto penceresinde bir göz atın. `cout` Değerin "INF" olarak listelendiğini görürsünüz ve bu, doğru görünmüyor ve bunu çözeceğiz. Satır, ' de `result`hangi değerin depolandığını gösterir. bu nedenle, F10 kullanarak ileri bir satır daha ilerlememeniz halinde konsol penceresi şunu görüntüler: `cout`

   ![Sıfıra bölme sonucu](./media/calc-vs2019-divide-by-zero-fail.png "Sıfıra bölme sonucu")

   Bu sonuç, sıfıra bölme tanımsız olduğundan, programın istenen işleme bir sayısal yanıtı olmadığından meydana gelir.

### <a name="to-fix-the-divide-by-zero-error"></a>"Sıfıra bölme" hatasını onarmak için

Daha düzgün bir şekilde bölme yaparak, bir Kullanıcı sorunu anlayabiliyor.

1. *Hesaplatoröğreticisi. cpp*' de aşağıdaki değişiklikleri yapın. ( **Düzenle ve devam et**adlı bir hata ayıklayıcı özelliği sayesinde programı düzenlediğiniz şekilde çalışır durumda bırakabilirsiniz):

    ```cpp
    // CalculatorTutorial.cpp : This file contains the 'main' function. Program execution begins and ends there.
    //

    #include <iostream>
    #include "Calculator.h"

    using namespace std;

    int main()
    {
        double x = 0.0;
        double y = 0.0;
        double result = 0.0;
        char oper = '+';

        cout << "Calculator Console Application" << endl << endl;
        cout << "Please enter the operation to perform. Format: a+b | a-b | a*b | a/b" << endl;

        Calculator c;
        while (true)
        {
            cin  >> x  >> oper  >> y;
            if (oper == '/' && y == 0)
            {
                cout << "Division by 0 exception" << endl;
                continue;
            }
            else
            {
                result = c.Calculate(x, oper, y);
            }
            cout << "Result is: " << result << endl;
        }

        return 0;
    }
    ```

1. Şimdi **F5** tuşuna basın. Program yürütme, Kullanıcı girişi istemek için duraklamaya kadar tüm şekilde devam eder. Yeniden `10 / 0` girin. Şimdi, daha yararlı bir ileti yazdırılır. Kullanıcıdan daha fazla giriş istenir ve program normal yürütülmeye devam eder.

   ![Değişikliklerden sonraki nihai sonuç](./media/calc-vs2019-final-verification.png "Değişikliklerden sonraki nihai sonuç")

   > [!Note]
   > Hata ayıklama modundayken kodu düzenlerken, kodun eskimiş olma riski vardır. Bu durum, hata ayıklayıcı eski kodunuzu çalıştırmakta olduğunda ve henüz değişikliklerinizi güncelleştirmemişse oluşur. Hata ayıklayıcı, bu gerçekleştiğinde sizi bilgilendirmek için bir iletişim kutusu açılır. Bazen, yürütülen kodu yenilemek için **F5** tuşuna basmanız gerekebilir. Özellikle, bir işlev içinde bir değişiklik yaparsanız, yürütme noktası bu işlevin içindeyse, işlevin dışına dönerek güncelleştirilmiş kodu almak için yeniden tekrar açmanız gerekir. Bu bir nedenden dolayı işe yaramazsa ve bir hata iletisi görürseniz, IDE 'nin en üstündeki menülerin altında bulunan araç çubuğunda kırmızı kareye tıklayarak hata ayıklamayı durdurabilirsiniz ve ardından **F5** tuşuna basarak veya s 'nin yanındaki yeşil "Oynat" okunu seçerek hata ayıklamayı yeniden başlatabilirsiniz. araç çubuğundaki üst düğmesi.

   > Çalıştırma ve hata ayıklama kısayollarını anlama
   >
   > - **F5** (veya > hata ayıklama**başlatma hata ayıklaması**), bir hata ayıklama oturumu başlatır ve bir kesme noktasına ulaşılana veya program kullanıcı girişine ihtiyaç duyana kadar programı çalıştırır. Kullanıcı girişi gerekmiyorsa ve isabet almak için kullanılabilir kesme noktası yoksa, program sonlanır ve program çalışmayı bitirdiğinde konsol penceresi kendisini kapatır. Çalıştırmak üzere bir "Merhaba Dünya" programı varsa, pencereyi açık tutmak için **F5** tuşuna girmeden önce **CTRL + F5** kullanın veya bir kesme noktası ayarlayın.
   > - **CTRL + F5** (veya > hata ayıklama**olmadan Başlat**), hata ayıklama moduna geçmeden uygulamayı çalıştırır. Bu, hata ayıklamadan biraz daha hızlıdır ve program yürütmeyi tamamladıktan sonra konsol penceresi açık kalır.
   > - **F10** ( **adım adım**olarak bilinir) kod içinde, satır içinde yinelemenize ve kodun nasıl çalıştırılacağını ve her yürütme adımında değişken değerlerinin ne olduğunu görselleştirmenizi sağlar.
   > - **F11** ( **adım**olarak bilinir), yürütme sırasında çağrılan herhangi bir Işleve adım adım olmak üzere, **adımla**aynı şekilde çalışır. Örneğin, yürütülenmekte olan satır bir işlev çağırırsa, **F11** tuşuna basıldığında işaretçiyi işlevin gövdesine taşıdıkça işlevin kodunu, başlattığınız satıra geri gelmeden önce, çalıştırılan işlevin kodunu takip edebilirsiniz. İşlev çağrısının üzerindeki **F10** adımlara basmak ve yalnızca sonraki satıra gitme; işlev çağrısı hala gerçekleşir, ancak program ne yaptığını göstermek için duraklamaz.

### <a name="close-the-app"></a>Uygulamayı kapat

- Hala çalışıyorsa, hesaplayıcı uygulamasının konsol penceresini kapatın.

## <a name="the-finished-app"></a>Tamamlanmış uygulama

Tebrikler! Hesaplayıcı uygulamasının kodunu tamamladınız, Visual Studio 'da oluşturulup hata ayıklaması yaptınız.

## <a name="next-steps"></a>Sonraki adımlar

[İçin Visual Studio hakkında daha fazla bilgi edininC++](https://blogs.msdn.microsoft.com/vcblog/2017/04/21/getting-started-with-visual-studio-for-c-and-cpp-development/)

::: moniker-end

::: moniker range="<vs-2019"

C++ Programcı için olağan başlangıç noktası "Merhaba, Dünya!" komut satırında çalışan uygulama. Bu makalede Visual Studio 'da oluşturacağınız şey, daha zorlayıcı bir işlem hesaplayıcısı: bir Hesaplayıcı uygulaması.

## <a name="prerequisites"></a>Önkoşullar

- Bilgisayarınızda yüklü ve çalışır şekilde çalışan iş yüküyle Visual Studio ile **masaüstü geliştirme C++**  yapın. Henüz yüklenmemişse bkz. [Visual Studio 'da destek yükleme C++ ](../build/vscpp-step-0-installation.md).

## <a name="create-your-app-project"></a>Uygulama projenizi oluşturma

Visual Studio kullanan *projeleri* bir uygulama için kod düzenleme ve *çözümleri* projelerinizi düzenlemek için. Bir proje, tüm seçenekleri, yapılandırmaları ve uygulamalarınızı oluşturmak için kullanılan kuralları içerir. Tüm proje dosyaları ve dış dosyaları arasındaki ilişki da yönetir. Uygulamanızı oluşturmak için önce yeni bir proje ve çözüm oluşturacaksınız.

1. Visual Studio 'daki menü çubuğundan **Dosya** > **Yeni** > **Proje**' yi seçin. **Yeni proje** penceresi açılır.

2. Sol kenar çubuğunda **görsel C++**  ' ün seçili olduğundan emin olun. Merkezinde **Windows konsol uygulaması**' nı seçin.

3. Alttaki **ad** düzenleme kutusunda, yeni proje *hesaplatoronu*adlandırın, sonra **Tamam**' ı seçin.

   ![Yeni proje iletişim kutusu](./media/calculator-new-project-dialog.png "Yeni proje iletişim kutusu")

   Boş C++ bir Windows konsol uygulaması oluşturulur. Konsol uygulamaları, çıktıyı göstermek ve Kullanıcı girişini kabul etmek için bir Windows konsol penceresi kullanır. Visual Studio 'da bir düzenleyici penceresi açılır ve oluşturulan kodu gösterir:

    ```cpp
    // CalculatorTutorial.cpp : This file contains the 'main' function. Program execution begins and ends there.
    //

    #include "pch.h"
    #include <iostream>

    int main()
    {
        std::cout << "Hello World!\n"; 
    }

    // Run program: Ctrl + F5 or Debug > Start Without Debugging menu
    // Debug program: F5 or Debug > Start Debugging menu

    // Tips for Getting Started: 
    //   1. Use the Solution Explorer window to add/manage files
    //   2. Use the Team Explorer window to connect to source control
    //   3. Use the Output window to see build output and other messages
    //   4. Use the Error List window to view errors
    //   5. Go to Project > Add New Item to create new code files, or Project > Add Existing Item to add existing code files to the project
    //   6. In the future, to open this project again, go to File > Open > Project and select the .sln file
    ```

## <a name="verify-that-your-new-app-builds-and-runs"></a>Yeni uygulamanızın derlemediğini ve çalıştığını doğrulayın

Yeni bir Windows konsol uygulaması şablonu basit C++ bir "Merhaba Dünya" uygulaması oluşturur. Bu noktada, Visual Studio 'Nun IDE 'den doğrudan oluşturduğunuz uygulamaları nasıl oluşturup yürüttüğünde daha fazla bilgi alabilirsiniz.

1. Projenizi derlemek için **derleme** menüsünden **çözüm oluştur** ' u seçin. **Çıkış** penceresi, derleme işleminin sonuçlarını gösterir.

   ![Projeyi derleme](./media/calculator-initial-build-output.png "Projeyi derleme")

1. Kodu çalıştırmak için, menü çubuğunda **Hata Ayıkla**, **hata ayıklama olmadan Başlat**' ı seçin.

   ![Projeyi Başlat](./media/calculator-hello-world-console.png "Projeyi Başlat")

   Konsol penceresi açılır ve uygulamanızı çalıştırır. Visual Studio 'da bir konsol uygulaması başlattığınızda, kodunuzu çalıştırır ve ardından devam etmek için herhangi bir tuşa basın. biçimindeki telefon numarasıdır. ." çıktıyı görmeniz için bir şans sağlamak üzere. Tebrikler! İlk "Hello, World!" dosyanızı oluşturdunuz Visual Studio 'da konsol uygulaması!

1. Konsol penceresini kapatmak ve Visual Studio 'ya dönmek için bir tuşa basın.

Artık, kodun beklendiği gibi çalıştığını doğrulamak için her değişiklikten sonra uygulamanızı derleyip çalıştırmaya yönelik araçlara sahipsiniz. Daha sonra, bu değilse nasıl hata ayıklaması yapılacağını göstereceğiz.

## <a name="edit-the-code"></a>Kodu Düzenle

Şimdi bu şablondaki kodu bir Hesaplayıcı uygulamasına açalım.

1. *Hesaplatoröğreticisi. cpp* dosyasında, kodu şu örnekle eşleşecek şekilde düzenleyin:

    ```cpp
    // CalculatorTutorial.cpp : This file contains the 'main' function. Program execution begins and ends there.
    //

    #include "pch.h"
    #include <iostream>

    using namespace std;

    int main()
    {
        cout << "Calculator Console Application" << endl << endl;
        cout << "Please enter the operation to perform. Format: a+b | a-b | a*b | a/b"
            << endl;
        return 0;
    }

    // Run program: Ctrl + F5 or Debug > Start Without Debugging menu
    // Debug program: F5 or Debug > Start Debugging menu
    // Tips for Getting Started:
    //   1. Use the Solution Explorer window to add/manage files
    //   2. Use the Team Explorer window to connect to source control
    //   3. Use the Output window to see build output and other messages
    //   4. Use the Error List window to view errors
    //   5. Go to Project > Add New Item to create new code files, or Project > Add Existing Item to add existing code files to the project
    //   6. In the future, to open this project again, go to File > Open > Project and select the .sln file
    ```

   > Kodu anlama:
   >
   > - Deyimleri `#include` , diğer dosyalarda bulunan koda başvuru yapmanıza olanak sağlar. Bazen açılı ayraçlar ( **\<\>** ) ile çevrelenmiş bir dosya adı görebilirsiniz; diğer zamanlarda tırnak işaretleri ( **""** ) ile çevrelenmiş olur. Genel olarak, C++ standart kitaplığa başvurulurken açılı ayraçlar kullanılır, ancak teklifler diğer dosyalar için kullanılır.
   > - (Veya Visual Studio 2017 ve `#include "stdafx.h"`önceki sürümler) satırında önceden derlenmiş üst bilgi olarak bilinen bir şey bulunuyor. `#include "pch.h"` Bunlar genellikle profesyonel programcılar tarafından derleme sürelerini geliştirmek için kullanılır, ancak Bu öğreticinin kapsamı dışındadır.
   > - Çizgi derleyiciye bu dosyada kullanılan C++ standart kitaplıktan şeyler beklendiğini söyler. `using namespace std;` Bu satır olmadan, bir kitaplıktaki her anahtar sözcüğünün, kapsamını göstermek için önünde bir `std::`ile olması gerekir. Örneğin, bu satır olmadan her başvurunun `cout` olarak `std::cout`yazılması gerekir. Kodun daha temiz görünmesini sağlamak için ifadeeklenir.`using`
   > - Anahtar `cout` sözcüğü, içindeki C++standart çıktıya yazdırmak için kullanılır. **İşleci derleyiciye, standart çıktıya ne olduğunu bildirir. \< \<**
   > - **Endl** anahtar sözcüğü ENTER tuşu gibidir; satırı sonlandırır ve imleci bir sonraki satıra kaydırır. Her zaman arabelleği temizleyerek ve bu çok `\n` küçük `endl` bir uygulama olduğundan, daha iyi bir uygulama olduğundan, dizenin içine (""), aynı şeyi yapmak için bir koymak daha iyi bir uygulamadır. `endl` luğunu.
   > - All C++ deyimlerinin noktalı virgül ile bitmesi ve tüm C++ uygulamaların bir `main()` işlev içermesi gerekir. Bu işlev, programın başlangıçta çalıştığı şeydir. Kullanılabilmesi için tüm koda erişilebilir `main()` olması gerekir.

1. Dosyayı kaydetmek için **CTRL + S**gırın veya IDE 'nin üst kısmına yakın bir şekilde **Kaydet** simgesini, menü çubuğunun altındaki araç çubuğundan disket simgesini seçin.

1. Uygulamayı çalıştırmak için **CTRL + F5** tuşlarına basın veya **hata ayıklama** menüsüne gidin ve **hata ayıklama olmadan Başlat**' ı seçin. **Bu projenin güncel**olmadığını belirten bir açılır pencere alırsanız, **Bu iletişim kutusunu bir daha gösterme**seçeneğini belirleyip uygulamanızı derlemek için **Evet** ' i seçebilirsiniz. Kodda belirtilen metni görüntüleyen bir konsol penceresi görürsünüz.

   ![Uygulamanızı derleyin ve başlatın](./media/calculator-first-launch.gif "Uygulamanızı derleyin ve başlatın")

1. İşiniz bittiğinde konsol penceresini kapatın.

## <a name="add-code-to-do-some-math"></a>Bazı matematik işlemlerini yapmak için kod ekleme

Biraz matematik mantığı ekleme zamanı.

### <a name="to-add-a-calculator-class"></a>Hesaplayıcı sınıfı eklemek için

1. **Proje** menüsüne gidin ve **Sınıf Ekle**' yi seçin. **Sınıf adı** düzenleme kutusuna *Hesaplayıcı*yazın. **Tamam**’ı seçin. Projenize iki yeni dosya eklenir. Değiştirdiğiniz tüm dosyaları aynı anda kaydetmek için **CTRL + SHIFT + S**tuşlarına basın. Bu, **Dosya** > **kaydetme**için bir klavye kısayoludur. Ayrıca, Kaydet düğmesinin yanında bulunan iki disket simgesi olan **Tümünü Kaydet**için bir araç çubuğu düğmesi de vardır. Genel olarak, kaydetme sırasında herhangi bir dosyayı kaçırmamak için sık sık **kaydedilmesi** iyi bir uygulamadır.

   ![Hesaplayıcı sınıfını oluşturma](./media/calculator-create-class.gif "Hesaplayıcı sınıfını oluşturma")

   Bir sınıf, bir şeyi yapan bir nesne için şema gibidir. Bu durumda, bir Hesaplayıcı ve nasıl çalışması gerektiğini tanımladık. Yukarıda kullandığınız **sınıf ekleme** Sihirbazı, sınıf ile aynı ada sahip. h ve. cpp dosyalarını oluşturdu. Proje dosyalarınızın tam listesini, IDE 'nin yanında görünen **Çözüm Gezgini** penceresinde görebilirsiniz. Pencere görünmüyorsa, menü çubuğundan açabilirsiniz: **Görünüm** > **Çözüm Gezgini**' yi seçin.

   ![Çözüm Gezgini](./media/calculator-solution-explorer.png "Çözüm Gezgini")

   Düzenleyicide Şu anda üç sekme açık olmalıdır: *Hesaplayıcı Toröğreticisi. cpp*, *Hesaplayıcı. h*ve *Hesaplayıcı. cpp*. Yanlışlıkla bunlardan birini kapatırsanız, **Çözüm Gezgini** penceresinde onu çift tıklayarak yeniden açabilirsiniz.

1. **Hesap makinesi. h**içinde, burada `Calculator();` , `~Calculator();` bunlara ihtiyacınız olmadığından, oluşturulan ve satırları kaldırın. Ardından, dosyanın şimdi şöyle görünmesi için aşağıdaki kod satırını ekleyin:

    ```cpp
    #pragma once
    class Calculator
    {
    public:
        double Calculate(double x, char oper, double y);
    };
    ```

   > Kodu anlama
   >
   > - Eklediğiniz satır, toplama, çıkarma, çarpma ve `Calculate`bölme için matematik işlemlerini çalıştırmak için kullanacağımız yeni bir işlev bildirir.
   > - C++kod, *üstbilgi* (. h) dosyaları ve *kaynak* (. cpp) dosyaları halinde düzenlenir. Çeşitli derleyiciler tarafından desteklenen çeşitli dosya uzantıları şunlardır, ancak bunlar hakkında bilgi sahibi olmak için başlıca değerlerdir. İşlevler ve değişkenler normalde *tanımlanmış*, diğer bir deyişle, bir ad ve tür, başlık dosyalarında, *uygulanan*veya bir tanım verilen kaynak dosyalarında. Başka bir dosyada tanımlanan koda erişmek için, ' filename. `#include "filename.h"`h ' öğesini kullanmak istediğiniz değişkenleri veya işlevleri bildiren dosyanın adı olan ' i kullanabilirsiniz.
   > - Sildiğiniz iki satır, sınıf için bir *Oluşturucu* ve *yıkıcı* bildirdi. Bunun gibi basit bir sınıf için derleyici bunları sizin için oluşturur ve kullanımları Bu öğreticinin kapsamı dışındadır.
   > - Kodunuzu, ne yapacaklarına göre farklı dosyalara düzenlemek iyi bir uygulamadır. bu sayede, daha sonra ihtiyacınız olan kodu kolayca bulabilirsiniz. Bizim örneğimizde, `Calculator` sınıfı `main()` işlevi içeren dosyadan ayrı olarak tanımladık, ancak içinde `Calculator` `main()`sınıfına başvuru planlıyoruz.

1. Altında `Calculate`yeşil renkli bir çizgi görünür. Bunun nedeni, `Calculate` . cpp dosyasında işlevi tanımlamadık. Sözcüğün üzerine gelin, açılan açık ampul ' e tıklayın ve **Hesaplayıcı. cpp ' de ' Calculate ' tanımı oluştur**' u seçin. Diğer dosyada yapılan kod değişikliğinin bir özetini sunan bir açılır pencere görünür. Kod, *Hesaplayıcı. cpp*öğesine eklendi.

   ![Hesaplama tanımı oluştur](./media/calculator-create-definition.gif "Hesaplama tanımı oluştur")

   Şu anda yalnızca 0,0 döndürüyor. Bunu değiştirelim. Açılır pencereyi kapatmak için **ESC** tuşuna basın.

1. Düzenleyici penceresindeki *Hesaplayıcı. cpp* dosyasına geçin. Ve bölümlerini kaldırın (. h dosyasında yaptığınız gibi) ve aşağıdaki kodu öğesine `Calculate()`ekleyin: `~Calculator()` `Calculator()`

    ```cpp
    #include "pch.h"
    #include "Calculator.h"

    double Calculator::Calculate(double x, char oper, double y)
    {
        switch(oper)
        {
            case '+':
                return x + y;
            case '-':
                return x - y;
            case '*':
                return x * y;
            case '/':
                return x / y;
            default:
                return 0.0;
        }
    }
    ```

   > Kodu anlama
   >
   > - İşlevi `Calculate` bir sayı, bir işleç ve ikinci bir sayı kullanır, ardından istenen işlemi sayılar üzerinde gerçekleştirir.
   > - Switch ifadesinde hangi işlecin sağlandığını kontrol eder ve yalnızca bu işleme karşılık gelen servis talebi yürütülür. Varsayılan: durum, kullanıcının kabul edilmeyen bir işleç yazdığında, dolayısıyla programın kesintiye uğramaması durumunda bir geri dönüş olur. Genel olarak, geçersiz kullanıcı girişini daha zarif bir şekilde işlemek en iyisidir, ancak Bu öğreticinin kapsamı dışındadır.
   > - Anahtar `double` sözcüğü, Onlukları destekleyen bir sayı türünü gösterir. Bu şekilde, hesaplayıcı hem Decimal Math hem de Integer Math işleyebilir. `Calculate` İşlevin ,`double` kodun çok başlangıcında (Bu, işlevin dönüş türünü belirtir), bu nedenle her zaman bir sayının bu tür bir değer döndürmesi gerekir. Bu, varsayılan durumda bile 0,0 getirdiğimiz anlamına gelir.
   > - . H dosyası, derleyicinin hangi parametrelereihtiyacı olduğunu ve bundan beklenen dönüş türünü belirten işlev prototipini bildirir. . Cpp dosyası, işlevin tüm uygulama ayrıntılarına sahiptir.

Kodu bu noktada yeniden oluşturup çalıştırırsanız, hangi işlemin gerçekleştirileceğini soran bir çıkış devam eder. Sonra, bazı hesaplamalar yapmak için `main` işlevini değiştirirsiniz.

### <a name="to-call-the-calculator-class-member-functions"></a>Hesaplayıcı sınıfı üye işlevlerini çağırmak için

1. Şimdi, `main` *hesaplatoröğreticisi. cpp*işlevini güncelleştirelim:

    ```cpp
    // CalculatorTutorial.cpp : This file contains the 'main' function. Program execution begins and ends there.
    //

    #include "pch.h"
    #include <iostream>
    #include "Calculator.h"

    using namespace std;

    int main()
    {
        double x = 0.0;
        double y = 0.0;
        double result = 0.0;
        char oper = '+';

        cout << "Calculator Console Application" << endl << endl;
        cout << "Please enter the operation to perform. Format: a+b | a-b | a*b | a/b"
             << endl;

        Calculator c;
        while (true)
        {
            cin >> x >> oper >> y;
            result = c.Calculate(x, oper, y);
            cout << "Result is: " << result << endl;
        }

        return 0;
    }
    ```

   > Kodu anlama
   >
   > - Programlar C++ her zaman `main()` işlevde başladığından, diğer kodumuzu buradan çağırmamız gerekir, bu nedenle bir `#include` ifade gereklidir.
   > - Bazı ilk değişkenler `x` `y` `result` ,, ve sırasıyla ilk Number, İkinci sayı, işleç ve nihai sonucu depolayacak şekilde bildirilmiştir. `oper` Bu, burada yapılan tanımsız davranışlara engel olmak için bazı ilk değerleri vermek her zaman iyi bir uygulamadır.
   > - Satır, `Calculator` sınıfının bir örneği olarak ' c ' adlı bir nesne bildirir. `Calculator c;` Sınıfın kendisi, hesaplayıcıların nasıl çalıştığı hakkında yalnızca bir şema olur; nesnesi, matematik yapan özel Hesaplayıcı ' dır.
   > - `while (true)` İfade bir döngüdür. Döngü içindeki kod, `()` ' ın içindeki koşul doğru olduğu sürece yeniden yürütmeye devam eder. Koşul yalnızca olarak listelendiğinden, her zaman `true`doğru olduğundan, döngü süresiz olarak çalışır. Programı kapatmak için Kullanıcı konsol penceresini el ile kapatması gerekir. Aksi takdirde, program her zaman yeni giriş bekler.
   > - `cin` Anahtar sözcüğü, kullanıcıdan girişi kabul etmek için kullanılır. Bu giriş akışı, konsol penceresinde girilen bir metin satırını işlemek için yeterince akıllı bir işlemdir ve Kullanıcı girişinin gerekli belirtile eşleştiğini varsayarak, listelenen değişkenlerin her birini sırayla yerleştirebilirsiniz. Bu satırı, örneğin iki sayıdan fazla farklı giriş türlerini kabul etmek için değiştirebilir, ancak `Calculate()` işlevin bunu işlemek için de güncelleştirilmeleri gerekir.
   > - İfade, daha önce `Calculate` tanımlanan işlevi çağırır ve girilen giriş değerlerini sağlar. `c.Calculate(x, oper, y);` İşlev daha sonra ' de `result`depolanan bir sayı döndürür.
   > - `result` Son olarak konsola yazdırılır, böylece Kullanıcı hesaplamanın sonucunu görür.

### <a name="build-and-test-the-code-again"></a>Kodu yeniden derleyin ve test edin

Artık, her şeyin düzgün çalıştığından emin olmak için programı yeniden test etme zamanı.

1. Uygulamayı yeniden oluşturmak ve başlatmak için **CTRL + F5** tuşlarına basın.

1. Yazın `5 + 5`ve ENTER tuşunabasın. Sonucun 10 olduğunu doğrulayın.

   ![5 + 5 sonucu](./media/calculator-five-plus-five.png "5 + 5 sonucu")

## <a name="debug-the-app"></a>Uygulamada hata ayıklama

Kullanıcı konsol penceresine herhangi bir şey yazmadığından ücretsiz olduğundan, hesap makinesinin bazı girişleri beklendiği gibi işlemesini sağlayın. Programı çalıştırmak yerine, bunun yerine hata ayıklaalım, bu nedenle ne yaptığını ayrıntılı olarak inceleyebileceğiniz adım adım.

### <a name="to-run-the-app-in-the-debugger"></a>Uygulamayı hata ayıklayıcıda çalıştırmak için

1. Yalnızca kullanıcıdan giriş sorulduktan `result = c.Calculate(x, oper, y);` sonra, satırda bir kesme noktası ayarlayın. Kesme noktasını ayarlamak için, düzenleyici penceresinin sol kenarındaki gri dikey çubukta bulunan çizgiye tıklayın. Kırmızı bir nokta görünür.

   ![Bir kesme noktası ayarlamak](./media/calculator-set-breakpoint.gif "bir kesme noktası ayarlayın")

   Artık programda hata ayıklaması yaptığımız zaman, bu satırdaki yürütmeyi her zaman duraklatır. Programın basit durumlar için çalışmasına yönelik kaba bir fikrimiz zaten var. Yürütmeyi her seferinde duraklatmak istemediğimiz için, kesme noktasını koşullu hale getirir.

1. Kesme noktasını temsil eden kırmızı noktaya sağ tıklayın ve **koşullar**' ı seçin. Koşulun düzenleme kutusunda, girin `(y == 0) && (oper == '/')`. İşiniz bittiğinde **Kapat** düğmesini seçin. Koşul otomatik olarak kaydedilir.

   ![Koşullu kesme noktası ayarlama](./media/calculator-conditional-breakpoint.gif "Koşullu kesme noktası ayarlama")

   Artık 0 olarak bölme denendiğinde yürütme kesme noktasında yürütmeyi durakladık.

1. Programda hata ayıklamak için **F5**'e basın veya yeşil ok simgesine sahip olan **yerel Windows hata ayıklayıcısı** araç çubuğu düğmesini seçin. Konsol uygulamanızda, "5-0" gibi bir şey girerseniz, program normal şekilde davranır ve çalışır durumda kalır. Ancak, "10/0" yazarsanız, kesme noktasında duraklatılır. İşleç ve sayı arasında istediğiniz sayıda boşluk da koyabilirsiniz; `cin` girişi uygun şekilde ayrıştırmaya yetecek kadar akıllı bir değer.

   ![Koşullu kesme noktasında Duraklat](./media/calculator-debug-conditional.gif "Koşullu kesme noktasında Duraklat")

### <a name="useful-windows-in-the-debugger"></a>Hata ayıklayıcıda yararlı pencereler

Kodunuzda hata ayıkladığınızda, bazı yeni pencerelerin göründüğünü fark edebilirsiniz. Bu pencereler hata ayıklama deneyiminize yardımcı olabilir. **Oto** penceresine göz atın. **Oto** penceresinde, geçerli satıra en az üç satır önce kullanılan değişkenlerin geçerli değerlerini gösterir.

   ![Oto penceresi](./media/calculator-autos.png "Oto penceresi")

Bu işlevden tüm değişkenleri görmek için **Yereller** penceresine geçin. Bu değişkenlerin değerlerini hata ayıklama sırasında değiştirebilir ve programda neler olacağını görebilirsiniz. Bu durumda, bunları tek başına bırakacağız.

   ![Yereller penceresi](./media/calculator-locals.png "Yereller penceresi")

Ayrıca, yürütmenin Şu anda duraklatıldığı geçerli değerlerini görmek için yalnızca kodun kendisindeki değişkenlerin üzerine gelebilmeniz gerekir. Önce üzerine tıklayarak düzenleyici penceresinin odaklandığından emin olun.

   ![Geçerli değişken değerlerini görüntülemek Için üzerine gelin](./media/calculator-hover-tooltip.gif "Geçerli değişken değerlerini görüntülemek Için üzerine gelin")

### <a name="to-continue-debugging"></a>Hata ayıklamaya devam etmek için

1. Sol taraftaki sarı çizgi, geçerli yürütme noktasını gösterir. Geçerli satırı çağırır `Calculate`, bu nedenle işlev **içine** dönmek için **F11** tuşuna basın. Kendi kendinize `Calculate` işlevin gövdesinde bulacaksınız. **Adımla**ilgili dikkatli olun; Bunu çok fazla yaparsanız, çok sayıda atık hale gelebilir. Standart Kitaplık işlevleri dahil olmak üzere, üzerinde olduğunuz satırda kullandığınız herhangi bir koda gider.

1. Yürütme noktası `Calculate` işlevin başlangıcında olduğuna göre, program yürütmesinin sonraki satırına geçmek için **F10** tuşuna basın. **F10** , **adım adım**olarak da bilinir. Satırdaki her bir bölümde gerçekleşdiklerin ayrıntılarına odaklanmadan satırdan satıra geçiş yapmak için **Step Over** ' u kullanabilirsiniz. Genel olarak, başka bir yerde Çağrılmakta olan kodu daha ayrıntılı bir şekilde incelemek istemediğiniz sürece (' ın `Calculate`gövdesine ulaştığınız gibi) daha fazla bilgi almak istiyorsanız, ' ın **içine adımla**yerine **adımını** kullanmanız gerekir.

1. Diğer `main()` dosyadakiişlevegeridönüpsatırüzerindeduranakadarherbirsatırdaadımadımilerleyin.`cout`

   ![Hesaplama ve denetim sonucunu adımla](./media/calculator-undefined-zero.gif "Hesaplama ve denetim sonucunu adımla")

   Program beklenildiği gibi görünüyor: ilk sayıyı alır ve ikinciden böler. Satırda, `result` değişkenin üzerine gelin `result` veya oto penceresinde bir göz atın. `cout` Değerin "INF" olarak listelendiğini görürsünüz ve bu, doğru görünmüyor ve bunu çözeceğiz. Satır, ' de `result`hangi değerin depolandığını gösterir. bu nedenle, F10 kullanarak ileri bir satır daha ilerlememeniz halinde konsol penceresi şunu görüntüler: `cout`

   ![Sıfıra bölme sonucu](./media/calculator-divide-by-zero-fail.png "Sıfıra bölme sonucu")

   Bu sonuç, sıfıra bölme tanımsız olduğundan, programın istenen işleme bir sayısal yanıtı olmadığından meydana gelir.

### <a name="to-fix-the-divide-by-zero-error"></a>"Sıfıra bölme" hatasını onarmak için

Daha düzgün bir şekilde bölme yaparak, bir Kullanıcı sorunu anlayabiliyor.

1. *Hesaplatoröğreticisi. cpp*' de aşağıdaki değişiklikleri yapın. ( **Düzenle ve devam et**adlı bir hata ayıklayıcı özelliği sayesinde programı düzenlediğiniz şekilde çalışır durumda bırakabilirsiniz):

    ```cpp
    // CalculatorTutorial.cpp : This file contains the 'main' function. Program execution begins and ends there.
    //

    #include "pch.h"
    #include <iostream>
    #include "Calculator.h"

    using namespace std;

    int main()
    {
        double x = 0.0;
        double y = 0.0;
        double result = 0.0;
        char oper = '+';

        cout << "Calculator Console Application" << endl << endl;
        cout << "Please enter the operation to perform. Format: a+b | a-b | a*b | a/b" << endl;

        Calculator c;
        while (true)
        {
            cin  >> x  >> oper  >> y;
            if (oper == '/' && y == 0)
            {
                cout << "Division by 0 exception" << endl;
                continue;
            }
            else
            {
                result = c.Calculate(x, oper, y);
            }
            cout << "Result is: " << result << endl;
        }

        return 0;
    }
    ```

1. Şimdi **F5** tuşuna basın. Program yürütme, Kullanıcı girişi istemek için duraklamaya kadar tüm şekilde devam eder. Yeniden `10 / 0` girin. Şimdi, daha yararlı bir ileti yazdırılır. Kullanıcıdan daha fazla giriş istenir ve program normal yürütülmeye devam eder.

   ![Değişikliklerden sonraki nihai sonuç](./media/calculator-final-verification.gif "Değişikliklerden sonraki nihai sonuç")

   > [!Note]
   > Hata ayıklama modundayken kodu düzenlerken, kodun eskimiş olma riski vardır. Bu durum, hata ayıklayıcı eski kodunuzu çalıştırmakta olduğunda ve henüz değişikliklerinizi güncelleştirmemişse oluşur. Hata ayıklayıcı, bu gerçekleştiğinde sizi bilgilendirmek için bir iletişim kutusu açılır. Bazen, yürütülen kodu yenilemek için **F5** tuşuna basmanız gerekebilir. Özellikle, bir işlev içinde bir değişiklik yaparsanız, yürütme noktası bu işlevin içindeyse, işlevin dışına dönerek güncelleştirilmiş kodu almak için yeniden tekrar açmanız gerekir. Bu bir nedenden dolayı işe yaramazsa ve bir hata iletisi görürseniz, IDE 'nin en üstündeki menülerin altında bulunan araç çubuğunda kırmızı kareye tıklayarak hata ayıklamayı durdurabilirsiniz ve ardından **F5** tuşuna basarak veya s 'nin yanındaki yeşil "Oynat" okunu seçerek hata ayıklamayı yeniden başlatabilirsiniz. araç çubuğundaki üst düğmesi.
   
   > Çalıştırma ve hata ayıklama kısayollarını anlama
   >
   > - **F5** (veya > hata ayıklama**başlatma hata ayıklaması**), bir hata ayıklama oturumu başlatır ve bir kesme noktasına ulaşılana veya program kullanıcı girişine ihtiyaç duyana kadar programı çalıştırır. Kullanıcı girişi gerekmiyorsa ve isabet almak için kullanılabilir kesme noktası yoksa, program sonlanır ve program çalışmayı bitirdiğinde konsol penceresi kendisini kapatır. Çalıştırmak üzere bir "Merhaba Dünya" programı varsa, pencereyi açık tutmak için **F5** tuşuna girmeden önce **CTRL + F5** kullanın veya bir kesme noktası ayarlayın.
   > - **CTRL + F5** (veya > hata ayıklama**olmadan Başlat**), hata ayıklama moduna geçmeden uygulamayı çalıştırır. Bu, hata ayıklamadan biraz daha hızlıdır ve program yürütmeyi tamamladıktan sonra konsol penceresi açık kalır.
   > - **F10** ( **adım adım**olarak bilinir) kod içinde, satır içinde yinelemenize ve kodun nasıl çalıştırılacağını ve her yürütme adımında değişken değerlerinin ne olduğunu görselleştirmenizi sağlar.
   > - **F11** ( **adım**olarak bilinir), yürütme sırasında çağrılan herhangi bir Işleve adım adım olmak üzere, **adımla**aynı şekilde çalışır. Örneğin, yürütülenmekte olan satır bir işlev çağırırsa, **F11** tuşuna basıldığında işaretçiyi işlevin gövdesine taşıdıkça işlevin kodunu, başlattığınız satıra geri gelmeden önce, çalıştırılan işlevin kodunu takip edebilirsiniz. İşlev çağrısının üzerindeki **F10** adımlara basmak ve yalnızca sonraki satıra gitme; işlev çağrısı hala gerçekleşir, ancak program ne yaptığını göstermek için duraklamaz.

### <a name="close-the-app"></a>Uygulamayı kapat

- Hala çalışıyorsa, hesaplayıcı uygulamasının konsol penceresini kapatın.

## <a name="the-finished-app"></a>Tamamlanmış uygulama

Tebrikler! Hesaplayıcı uygulamasının kodunu tamamladınız, Visual Studio 'da oluşturulup hata ayıklaması yaptınız.

## <a name="next-steps"></a>Sonraki adımlar

[İçin Visual Studio hakkında daha fazla bilgi edininC++](https://blogs.msdn.microsoft.com/vcblog/2017/04/21/getting-started-with-visual-studio-for-c-and-cpp-development/)

::: moniker-end
