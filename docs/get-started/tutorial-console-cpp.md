---
title: C++ konsol uygulama projesi oluşturma
description: Visual C++'da Hello World konsol uygulaması ve hesap makinesi uygulaması oluşturun
ms.custom: mvc
ms.date: 08/19/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 27522a6960546dc935ea3d9bce974eb36789c0aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "80079283"
---
# <a name="create-a-c-console-app-project"></a>C++ konsol uygulama projesi oluşturma

::: moniker range=">=vs-2019"

Bir C++ programcısı için her zamanki başlangıç noktası "Merhaba, dünya!" komut satırında çalışan uygulama. Bu makalede Visual Studio'da bunu yaratacağınız şey bu, ve sonra daha zorlu bir şeye geçeceğiz: bir hesap makinesi uygulaması.

## <a name="prerequisites"></a>Ön koşullar

- **C++** iş yükü yüklü ve bilgisayarınızda çalışan Masaüstü geliştirme ile Visual Studio var. Henüz yüklenmediyse Visual [Studio'da C++ desteği yükle'ye](../build/vscpp-step-0-installation.md)bakın.

## <a name="create-your-app-project"></a>Uygulama projenizi oluşturun

Visual Studio, bir uygulamanın kodunu düzenlemek için *projeler* ve projelerinizi düzenlemek için *çözümler* kullanır. Proje, uygulamalarınızı oluşturmak için kullanılan tüm seçenekleri, yapılandırmaları ve kuralları içerir. Ayrıca, projenin tüm dosyaları ve dış dosyalar arasındaki ilişkiyi yönetir. Uygulamanızı oluşturmak için öncelikle yeni bir proje ve çözüm oluşturursunuz.

1. Visual Studio'ya yeni başladıysanız Visual Studio 2019 iletişim kutusunu görürsünüz. Başlamak için **yeni bir proje oluştur'u** seçin.

   ![Visual Studio 2019 başlangıç iletişim kutusu](./media/calc-vs2019-initial-dialog.png "Visual Studio 2019 başlangıç iletişim kutusu")

   Aksi takdirde, Visual Studio'daki menü çubuğunda**Yeni** >  **Dosya** > **Yı**seçin. **Yeni proje oluştur** penceresi açılır.

1. Proje şablonları listesinde Konsol **Uygulaması'nı**seçin ve **ardından İleri'yi**seçin.

   ![Konsol Uygulaması şablonu seçin](./media/calc-vs2019-choose-console-app.png "Konsol Uygulaması şablonu seçin")

   > [!Important]
   > **Konsol Uygulaması** şablonunun C++ sürümünü seçtiğinizden emin olun. **C++**, **Windows**ve **Console** etiketleri vardır ve simgenin köşesinde "++" vardır.

1. Yeni proje iletişim **kutunuzu Yapılandır'** **da, Proje adı** düzenlemesi kutusunu seçin, yeni proje *Hesap Layıcı Öğreticinizi*adlandırın, ardından **Oluştur'u**seçin.

   ![Yeni proje iletişim günlüğüne Yapıla'da projenizi adlandırın](./media/calc-vs2019-name-your-project.png "Yeni proje iletişim günlüğüne Yapıla'da projenizi adlandırın")

   Boş bir C++ Windows konsol uygulaması oluşturulur. Konsol uygulamaları, çıktıyı görüntülemek ve kullanıcı girişini kabul etmek için windows konsol penceresi kullanır. Visual Studio'da bir düzenleyici penceresi açılır ve oluşturulan kodu gösterir:

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

## <a name="verify-that-your-new-app-builds-and-runs"></a>Yeni uygulamanızın oluşturduğunu ve çalıştığını doğrulayın

Yeni bir Windows konsol uygulaması için şablon basit bir C++ "Hello World" uygulaması oluşturur. Bu noktada Visual Studio'nun oluşturduğunuz uygulamaları nasıl oluşturduğunu ve çalıştırdığını IDE'den görebilirsiniz.

1. Projenizi oluşturmak için **Yapı** menüsünden **Çözüm Oluştur'u** seçin. **Çıktı** penceresi yapı işleminin sonuçlarını gösterir.

   ![Projeyi derleme](./media/calc-vs2019-build-your-project.png "Projeyi derleme")

1. Kodu çalıştırmak için menü çubuğunda **Hata**Ayıklama'yı seçin, **hata ayıklama dan başlat.**

   ![Projeyi başlatın](./media/calc-vs2019-hello-world-console.png "Projeyi başlatın")

   Bir konsol penceresi açılır ve ardından uygulamanızı çalıştırır. Visual Studio'da bir konsol uygulaması başlattığınızda, kodunuzu çalıştırır ve "Bu pencereyi kapatmak için herhangi bir tuşa basın. . ." çıktıyı görme şansı vermek için. Tebrikler! İlk "Merhaba, dünya!" Visual Studio konsol uygulaması!

1. Konsol penceresini kapatmak ve Visual Studio'ya dönmek için bir tuşa basın.

Artık, kodun hala beklediğiniz gibi çalıştığını doğrulamak için her değişiklikten sonra uygulamanızı oluşturmak ve çalıştırmak için araçlara sahipsiniz. Daha sonra, değilse nasıl hata ayıklama göstereceğiz.

## <a name="edit-the-code"></a>Kodu edin

Şimdi bu şablondaki kodu bir hesap makinesi uygulamasına dönüştürelim.

1. *CalculatorTutorial.cpp* dosyasında, kodu aşağıdaki örneğe uyacak şekilde edin:

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
   > - İfadeler, `#include` diğer dosyalarda bulunan koda başvuru göndermenizi sağlar. Bazen, açı parantezi ile çevrili bir**\<** dosya adı görebilirsiniz ( ); diğer zamanlarda, tırnak ile çevrilidir (**" " ).** Genel olarak, C++ Standart Kitaplığı'na başvururken açı ayraçları kullanılırken, diğer dosyalar için tırnak işaretleri kullanılır.
   > - Satır `using namespace std;` derleyiciye C++ Standart Kitaplığı'ndan gelen şeylerin bu dosyada kullanılmasını beklemesini söyler. Bu satır olmadan, kitaplıktaki her anahtar kelimenin `std::`kapsamını belirtmek için bir , önce olması gerekir. Örneğin, bu satır olmadan, `cout` her başvuru olarak `std::cout`yazılması gerekir . İfade, `using` kodun daha temiz görünmesi için eklenir.
   > - `cout` Anahtar kelime, C++'da standart çıktıyazdırmak için kullanılır. Operatör ** \< ** derleyiciye, sağındaki her şeyi standart çıktıya göndermesini söyler.
   > - **Endl** anahtar kelimesi Enter tuşu gibidir; satırı sona erdirir ve imleci bir sonraki satıra taşır. Her `\n` `endl` zaman tampon temizler ve programın performansını zarar verebilir, aynı şeyi yapmak için dize ("" tarafından bulunan) içine koymak için daha `endl` iyi bir uygulamadır, ancak bu çok küçük bir uygulama olduğu için, daha iyi okunabilirlik için kullanılır.
   > - Tüm C++ deyimleri yarı nokta nokta ile sona ermeli ve tüm C++ uygulamaları bir `main()` işlev içermelidir. Bu işlev, programın başlangıçta çalıştırılabır. Kullanılabilmesi için tüm `main()` kodlardan erişilebilir olması gerekir.

1. Dosyayı kaydetmek için **Ctrl+S**girin veya menü çubuğunun altındaki araç çubuğundaki disket simgesi olan IDE'nin üst kısmındaki **Kaydet** simgesini seçin.

1. Uygulamayı çalıştırmak için **Ctrl+F5** tuşuna basın veya **Hata Ayıklama** menüsüne gidin ve **Hata Ayıklama olmadan Başlat'ı**seçin. Kodda belirtilen metni görüntüleyen bir konsol penceresi görmeniz gerekir.

1. Bitirdiğinizde konsol penceresini kapatın.

## <a name="add-code-to-do-some-math"></a>Bazı matematik yapmak için kod ekleme

Biraz matematik mantığı eklemenin zamanı.

### <a name="to-add-a-calculator-class"></a>Hesap Makinesi sınıfı eklemek için

1. **Proje** menüsüne gidin ve **Sınıf Ekle'yi**seçin. Sınıf **Adı** edit kutusuna *Hesap Makinesi'ni*girin. **Tamam'ı**seçin. Projenize iki yeni dosya eklenir. Değiştirilen tüm dosyalarınızı aynı anda kaydetmek için **Ctrl+Shift+S**tuşuna basın. **Tümlerini** > **Kaydet**için bir klavye kısayolu. Save butonunun yanında bulunan iki disket simgesi olan **Tümleri Kaydet**için bir araç çubuğu düğmesi de vardır. **Save** Genel olarak, tümlerini sık sık **kaydet** yapmak iyi bir uygulamadır, böylece kaydederken hiçbir dosyayı kaçırmazsınız.

   ![Hesap Makinesi sınıfını oluşturma](./media/calc-vs2019-create-calculator-class.png "Hesap Makinesi sınıfını oluşturma")

   Sınıf, bir şey yapan bir nesnenin planı gibidir. Bu durumda, bir hesap makinesi ve nasıl çalışması gerektiğini tanımlar. Yukarıda kullandığınız **Sınıf Ekle** sihirbazı, sınıfla aynı ada sahip .h ve .cpp dosyalarını oluşturdu. IDE'nin yan tarafında görünen **Çözüm Gezgini** penceresinde proje dosyalarınızın tam listesini görebilirsiniz. Pencere görünmüyorsa, menü çubuğundan açabilirsiniz:**Çözüm Gezgini** **Görüntüle'yi** > seçin.

   ![Çözüm Gezgini](./media/calc-vs2019-solution-explorer.png "Çözüm Gezgini")

   Şimdi editör açık üç sekmeleri olmalıdır: *CalculatorTutorial.cpp*, *Calculator.h*, ve *Calculator.cpp*. Bunlardan birini yanlışlıkla kapatırsanız, **Çözüm Gezgini** penceresinde çift tıklatarak yeniden açabilirsiniz.

1. **Calculator.h'de,** `Calculator();` burada `~Calculator();` ihtiyacınız olmayacağından oluşturulan satırları ve satırları kaldırın. Ardından, dosyanın şimdi şuna benzemesi için aşağıdaki kod satırını ekleyin:

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
   > - Eklediğiniz satır, toplama, çıkarma, çarpma ve bölme için matematik işlemlerini çalıştırmak için kullanacağımız yeni bir işlev bildirir. `Calculate`
   > - C++ kodu *üstbilgi* (.h) dosyaları ve *kaynak* (.cpp) dosyaları olarak düzenlenir. Diğer birkaç dosya uzantıları çeşitli derleyiciler tarafından desteklenir, ancak bunlar hakkında bilinmesi gereken ana olanlar dır. İşlevler ve değişkenler *normalde,* yani üstbilgi dosyalarında bir ad ve tür verilir ve kaynak dosyalarında *uygulanır*veya bir tanım verilir. Başka bir dosyada tanımlanan koda `#include "filename.h"`erişmek için, 'filename.h'nin kullanmak istediğiniz değişkenleri veya işlevleri bildiren dosyanın adı olduğu bir durum kullanabilirsiniz.
   > - Sildiğiniz iki satır, sınıf için *bir oluşturucu* ve *yıkıcı* olarak bildirilir. Bunun gibi basit bir sınıf için derleyici bunları sizin için oluşturur ve kullanımları bu öğreticinin kapsamı dışındadır.
   > - Kodunuzu ne yaptığına göre farklı dosyalarhalinde düzenlemek iyi bir uygulamadır, bu nedenle daha sonra gereksinim duyduğunuz kodu kolayca bulabilirsiniz. Bizim `Calculator` durumumuzda, sınıfı `main()` işlevi içeren dosyadan ayrı olarak tanımlarız, `Calculator` ancak `main()`'deki sınıfa başvurmayı planlıyoruz.

1. Altında yeşil bir dalgalı belirir. `Calculate` Çünkü .cpp dosyasındaki `Calculate` işlevi tanımlamadık. Kelimenin üzerine yıkın, açılan ampulü (bu durumda bir tornavida) tıklatın ve **Calculator.cpp'de 'Hesapla' tanımını oluştur'u**seçin.

   ![Hesapla tanımı nı oluştur](./media/calc-vs2019-create-definition.png "Hesapla tanımı nı oluştur")

   Diğer dosyada yapılan kod değişikliğine göz atmanızı sağlayan bir açılır pencere görüntülenir. Kod *Hesap Makinesi.cpp*eklendi.

   ![Hesapla tanımı ile açılır pencere](./media/calc-vs2019-pop-up-definition.png "Hesapla tanımı ile açılır pencere")

   Şu anda, sadece 0.0 döndürür. Şimdi bunu değiştirelim. Açılır pencereyi kapatmak için **Esc** tuşuna basın.

1. Düzenleyici penceresindeki *Hesap Makinesi.cpp* dosyasına geçin. Bölümleri `Calculator()` ve `~Calculator()` bölümleri kaldırın (.h dosyasında yaptığınız gibi) `Calculate()`ve aşağıdaki kodu ekleyin:

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
   > - İşlev `Calculate` bir sayı, bir işleç ve ikinci bir sayı tüketir, sonra sayılar üzerinde istenen işlemi gerçekleştirir.
   > - Anahtar deyimi hangi işlecinin sağlandığını denetler ve yalnızca bu işlek karşılık gelen servis talebiyürütür. Varsayılan: servis talebi, kullanıcının kabul edilmeyen bir işleç tipleme ihtimaline karşı bir geri dönüştür, bu nedenle program kırılmaz. Genel olarak, geçersiz kullanıcı girişlerini daha zarif bir şekilde işlemek en iyisidir, ancak bu, bu öğreticinin kapsamı dışındadır.
   > - Anahtar `double` kelime, ondalık sayıları destekleyen bir sayı türünü gösterir. Bu şekilde, hesap makinesi hem ondalık matematik hem de tamsayı matematiği işleyebilir. İşlev, `Calculate` kodun en başında (bu `double` işlevin dönüş türünü gösterir) nedeniyle her zaman böyle bir sayıyı döndürmek için gereklidir, bu nedenle varsayılan durumda bile 0.0 döndürürüz.
   > - .h dosyası, derleyiciye hangi parametreleri gerektirdiğini ve hangi iade türünü ondan bekleyeceğini önceden söyleyen işlev *prototipini*bildirir. .cpp dosyası işlevin tüm uygulama ayrıntılarına sahiptir.

Bu noktada kodu yeniden oluşturur ve çalıştırın, hangi işlemi gerçekleştireceğini sorduktan sonra yine çıkar. Ardından, bazı hesaplamalar `main` yapmak için işlevi değiştirirsiniz.

### <a name="to-call-the-calculator-class-member-functions"></a>Hesap Makinesi sınıfı üye işlevlerini aramak için

1. Şimdi `main` *CalculatorTutorial.cpp*işlevini güncelleştirelim:

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
   > - C++ programları her zaman `main()` işlevden başladığı için, diğer kodumuzu `#include` oradan aramamız gerekir, bu nedenle bir ifade gereklidir.
   > - Bazı ilk `x` `y`değişkenler, , , `oper`ve `result` sırasıyla ilk sayı, ikinci sayı, işleç ve nihai sonucu depolamak için bildirilir. Tanımsız davranışlardan kaçınmak için onlara bazı başlangıç değerleri vermek her zaman iyi bir uygulamadır, ki bu da burada yapılan şeydir.
   > - Satır `Calculator c;` sınıfın bir örneği `Calculator` olarak 'c' adlı bir nesne bildirir. Sınıfın kendisi, hesap makinelerinin nasıl çalıştığına yönelik bir plandır; nesne, matematiği yapan özel hesap makinesidir.
   > - `while (true)` İfade bir döngüdür. Döngü içindeki kod, içindeki koşul doğru olduğu sürece tekrar `()` tekrar yürütmeye devam ediyor. Durum sadece olarak `true`listelenen bu yana , her zaman doğrudur, bu yüzden döngü sonsuza kadar çalışır. Programı kapatmak için, kullanıcının konsol penceresini el ile kapatması gerekir. Aksi takdirde, program her zaman yeni giriş bekler.
   > - `cin` Anahtar kelime, kullanıcıdan giriş kabul etmek için kullanılır. Bu giriş akışı, konsol penceresine girilen bir metin satırını işlemek ve kullanıcı girişinin gerekli belirtimle eşleştiğini varsayarak sırayla listelenen değişkenlerin her birine yerleştirmek için yeterince akıllıdır. Bu satırı, örneğin ikiden fazla sayı yı kabul edecek şekilde değiştirebilirsiniz, ancak işlevin `Calculate()` de bunu işlemek için güncelleştirilmesi gerekir.
   > - İfade `c.Calculate(x, oper, y);` daha `Calculate` önce tanımlanan işlevi çağırır ve girilen giriş değerlerini sağlar. İşlev daha sonra depolanan bir `result`sayı döndürür.
   > - Son `result` olarak, konsola yazdırılır, böylece kullanıcı hesaplama sonucunu görür.

### <a name="build-and-test-the-code-again"></a>Kodu yeniden oluşturma ve test edin

Şimdi her şeyin düzgün çalıştığından emin olmak için programı tekrar test etme zamanı.

1. Uygulamayı yeniden oluşturmak ve başlatmak için **Ctrl+F5** tuşuna basın.

1. Girin `5 + 5`ve **Enter**tuşuna basın. Sonucun 10 olduğunu doğrulayın.

   ![5 + 5 sonucu](./media/calc-vs2019-five-plus-five.png "5 + 5 sonucu")

## <a name="debug-the-app"></a>Uygulamayı hata ayıklama

Kullanıcı konsol penceresine bir şey yazmakta özgür olduğundan, hesap makinesinin beklendiği gibi bazı girdileri işlediğinden emin olalım. Programı çalıştırmak yerine, bunun yerine hata ayıklayalım, böylece ne yaptığını ayrıntılı olarak inceleyelim, adım adım.

### <a name="to-run-the-app-in-the-debugger"></a>Uygulamayı hata ayıklamada çalıştırmak için

1. Kullanıcıdan `result = c.Calculate(x, oper, y);` giriş istendikten hemen sonra, satırda bir kesme noktası ayarlayın. Kesme noktasını ayarlamak için, düzenleyici penceresinin sol kenarındaki gri dikey çubuktaki satırın yanına tıklayın. Kırmızı bir nokta belirir.

   ![Kesme noktası ayarlama](./media/calc-vs2019-set-breakpoint.png "Kesme noktası ayarlama")

   Şimdi programı hata ayıklamamız, her zaman bu satırda yürütme duraklar. Biz zaten program basit durumlarda çalışır kaba bir fikir var. Yürütmeyi her seferinde duraklatmak istemediğimiz için, kırılma noktasını koşullu hale getirelim.

1. Kesme noktasını temsil eden kırmızı noktayı sağ tıklatın ve **Koşullar'ı**seçin. Durum için edit kutusuna `(y == 0) && (oper == '/')`girin. Bittiğinde **Kapat** düğmesini seçin. Koşul otomatik olarak kaydedilir.

   ![Koşullu bir kesme noktası ayarlama](./media/calc-vs2019-conditional-breakpoint.png "Koşullu bir kesme noktası ayarlama")

   Şimdi, özellikle 0'a kadar bir bölme denenmişse, kesme noktasında yürütmeyi duraklatıyoruz.

1. Programı hata ayıklamak için **F5**tuşuna basın veya yeşil ok simgesine sahip **Yerel Windows Hata Ayıklayıcı** araç çubuğu nu seçin. Konsol uygulamanızda , "5 - 0" gibi bir şey girerseniz, program normal şekilde çalışır ve çalışmaya devam eder. Ancak, "10 / 0" yazarsanız, kesme noktasında duraklar. Operatör ve sayılar arasında herhangi bir sayıda `cin` boşluk bile koyabilirsiniz: girişi uygun şekilde ayrıştıracak kadar akıllıdır.

   ![Koşullu kesme noktasında duraklatma](./media/calc-vs2019-debug-breakpoint.png "Koşullu kesme noktasında duraklatma")

### <a name="useful-windows-in-the-debugger"></a>Hata ayıklamada kullanışlı pencereler

Kodunuzu hata ayıklamanızda, bazı yeni pencerelerin göründüğünü fark edebilirsiniz. Bu pencereler hata ayıklama deneyiminize yardımcı olabilir. **Autos** penceresine bir göz atın. **Otomatik Ayar** penceresi, geçerli satırdan önce ve en fazla üç satır da kullanılan değişkenlerin geçerli değerlerini gösterir. Bu işlevdeki tüm değişkenleri görmek için **Yereller** penceresine geçin. Hata ayıklama sırasında bu değişkenlerin değerlerini değiştirerek program üzerinde nasıl bir etki yaratacağını görebilirsiniz. Bu durumda, onları rahat bırakacağız.

   ![Yerel ler penceresi](./media/calc-vs2019-debug-locals.png "Yerel ler penceresi")

Ayrıca, yürütmenin şu anda duraklatılmış olduğu geçerli değerlerini görmek için kodun kendisindeki değişkenlerin üzerinde gezinmeniz de mümkündür. Önce üzerine tıklayarak düzenleyici penceresinin odakta olduğundan emin olun.

   ![Geçerli değişken değerlerini görüntülemek için gezinme](./media/calc-vs2019-hover-tooltip.png "Geçerli değişken değerlerini görüntülemek için gezinme")

### <a name="to-continue-debugging"></a>Hata ayıklama devam etmek için

1. Soldaki sarı çizgi geçerli yürütme noktasını gösterir. Geçerli satır `Calculate`çağrıları, bu nedenle işlevin **içine adım** **f11** tuşuna basın. Kendini `Calculate` fonksiyonun bedeninde bulacaksın. **Step Into**ile dikkatli olun ; Eğer çok fazla yaparsanız, çok fazla zaman kaybedebilirsiniz. Standart kitaplık işlevleri de dahil olmak üzere, kullandığınız herhangi bir koda gider.

1. Yürütme noktası `Calculate` işlevin başlangıcında olduğuna göre, programın yürütülmesinde bir sonraki satıra geçmek için **F10** tuşuna basın. **F10,** Step **Over**olarak da bilinir. Satırın her bölümünde meydana gelen ayrıntıları delving olmadan, satırdan satıra taşımak için **Adım Üzerinde** kullanabilirsiniz. Genel olarak **Step Into**yerine Step `Calculate` **Over'ı** kullanmalısınız , eğer başka bir yerden çağrılan koda daha derinden dalmak istemiyorsanız (vücuduna ulaşmak için yaptığınız gibi).

1. Diğer dosyadaki `main()` işleve geri dönene kadar **F10'u** her satırın `cout` **üzerine** basmak için kullanmaya devam edin ve satırı durdurun.

   Program bekleneni yapıyor gibi görünüyor: ilk sayıyı alır ve ikinciye böler. Satırda, `cout` değişkenin üzerine `result` doğru gezin `result` veya **Otomatik Ler** penceresinden bir göz atın. Değerinin "inf" olarak listelendiğini göreceksiniz, bu da doğru görünmüyor, bu yüzden düzeltelim. Satır `cout` sadece hangi değer depolanırsa `result`depolanır, bu yüzden **F10**kullanarak bir satır daha ileri adım attığınızda, konsol penceresi görüntüler:

   ![Sıfıra bölmenin sonucu](./media/calc-vs2019-divide-by-zero-fail.png "Sıfıra bölmenin sonucu")

   Bu sonuç, sıfıra bölme tanımlı olduğundan, programın istenen işlem için sayısal bir yanıtı olmadığından ortaya çıkan sonuçtur.

### <a name="to-fix-the-divide-by-zero-error"></a>"Sıfıra böl" hatasını düzeltmek için

Bölümü sıfıra göre daha ince likle ele alalım, böylece kullanıcı sorunu anlayabilir.

1. *CalculatorTutorial.cpp'de*aşağıdaki değişiklikleri yapın. **(Edit ve Continue**adlı hata ayıklama özelliği sayesinde programı düzenledikçe çalışır durumda bırakabilirsiniz):

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

1. Şimdi bir kez **F5 tuşuna** basın. Program yürütme kullanıcı girişi istemek için duraklatmak zorunda kadar tüm yol boyunca devam ediyor. Tekrar `10 / 0` girin. Şimdi, daha yararlı bir ileti yazdırılır. Kullanıcıdan daha fazla giriş istenir ve program normal olarak yürütmeye devam edilir.

   ![Değişikliklerden sonraki nihai sonuç](./media/calc-vs2019-final-verification.png "Değişikliklerden sonraki nihai sonuç")

   > [!Note]
   > Hata ayıklama modundayken kodu değiştirdiğinizde, kodun eskime riski vardır. Bu, hata ayıklayıcı eski kodunuzu çalıştırmaya devam ettiğinde ve değişiklikleriniz ile henüz güncelleştirmiyorsa gerçekleşir. Hata ayıklama, bu durumda sizi bilgilendirmek için bir iletişim kutusu açılır. Bazen, yürütülmekte olan kodu yenilemek için **F5** tuşuna basmanız gerekebilir. Özellikle, yürütme noktası bu işlevin içindeyken bir işlev in içinde bir değişiklik yaparsanız, güncelleştirilmiş kodu almak için işlevin dışına çıkmanız ve ardından yeniden bu işleve geri dönmeniz gerekir. Bu bir nedenle işe yaramazsa ve bir hata iletisi görüyorsanız, IDE'nin üst kısmındaki menülerin altındaki araç çubuğundaki kırmızı kareyi tıklatarak hata ayıklamayı durdurabilirsiniz, ardından **F5** girerek veya araç çubuğundaki dur düğmesinin yanındaki yeşil "play" okunu seçerek yeniden hata ayıklamaya başlayabilirsiniz.

   > Çalıştır ve Hata Ayıklama kısayollarını anlama
   >
   > - **F5** (veya **Hata Ayıklama** > **Hata Ayıklama)** biri zaten etkin değilse hata ayıklama oturumu başlatır ve bir kesme noktası vurulana veya programın kullanıcı girişine ihtiyacı olana kadar programı çalıştırUr. Kullanıcı girişi gerekmezse ve vurmak için bir kesme noktası yoksa, program sonlandırır ve program çalışırken bittiğinde konsol penceresi kendini kapatır. Çalıştırmak için "Hello World" programı gibi bir şey varsa, pencereaçık tutmak için **F5** girmeden önce **Ctrl+F5** kullanın veya bir kesme noktası ayarlayın.
   > - **Ctrl+F5** (veya Hata **Ayıklama** > Olmadan Hata**Ayıklama)** hata ayıklama moduna girmeden uygulamayı çalıştırır. Bu hata ayıklama biraz daha hızlı ve program yürütme tamamladıktan sonra konsol penceresi açık kalır.
   > - **F10** **(Adım Ataşma**olarak bilinir) kod, satır satır gezinmenizi ve kodun nasıl çalıştırıldığını ve yürütmenin her adımında hangi değişken değerlerinin olduğunu görselleştirmenize olanak tanır.
   > - **F11** **(Step Into**olarak da bilinir) **Step Over'a**benzer şekilde çalışır, ancak yürütme satırında çağrılan işlevlere adım atar. Örneğin, yürütülen satır bir işlevi çağırırsa, **F11** tuşuna basıldığında işaretçiyi işlevin gövdesine taşır, böylece başladığınız satıra geri dönmeden önce işlevin kodunun çalıştırıldığını izleyebilirsiniz. **F10** tuşuna basarak işlev çağrısının üzerine basar ve bir sonraki satıra geçer; işlev çağrısı yine de gerçekleşir, ancak program ne yaptığını göstermek için duraklatmaz.

### <a name="close-the-app"></a>Uygulamayı kapat

- Çalışıyorsa, hesap makinesi uygulaması için konsol penceresini kapatın.

## <a name="the-finished-app"></a>Bitmiş uygulama

Tebrikler! Hesap makinesi uygulamasının kodunu tamamladınız ve Visual Studio'da oluşturup debugged.

## <a name="next-steps"></a>Sonraki adımlar

[C++ için Visual Studio hakkında daha fazla bilgi edinin](https://blogs.msdn.microsoft.com/vcblog/2017/04/21/getting-started-with-visual-studio-for-c-and-cpp-development/)

::: moniker-end

::: moniker range="<vs-2019"

Bir C++ programcısı için her zamanki başlangıç noktası "Merhaba, dünya!" komut satırında çalışan uygulama. Bu makalede Visual Studio'da bunu yaratacağınız şey bu, ve sonra daha zorlu bir şeye geçeceğiz: bir hesap makinesi uygulaması.

## <a name="prerequisites"></a>Ön koşullar

- **C++** iş yükü yüklü ve bilgisayarınızda çalışan Masaüstü geliştirme ile Visual Studio var. Henüz yüklenmediyse Visual [Studio'da C++ desteği yükle'ye](../build/vscpp-step-0-installation.md)bakın.

## <a name="create-your-app-project"></a>Uygulama projenizi oluşturun

Visual Studio, bir uygulamanın kodunu düzenlemek için *projeler* ve projelerinizi düzenlemek için *çözümler* kullanır. Proje, uygulamalarınızı oluşturmak için kullanılan tüm seçenekleri, yapılandırmaları ve kuralları içerir. Ayrıca, projenin tüm dosyaları ve dış dosyalar arasındaki ilişkiyi yönetir. Uygulamanızı oluşturmak için öncelikle yeni bir proje ve çözüm oluşturursunuz.

1. Visual Studio'daki menü çubuğunda**Yeni** >  **Dosya** > **Projesi'ni**seçin. **Yeni Proje** penceresi açılır.

2. Sol kenar çubuğunda **Visual C++** seçildiğinden emin olun. **Merkezde, Windows Console Uygulaması'nı**seçin.

3. Alttaki **Ad** düzenlemesi kutusunda, yeni proje *Hesap Makinesi Öğretici*adını, sonra **Tamam'ı**seçin.

   ![Yeni Proje iletişim kutusu](./media/calculator-new-project-dialog.png "Yeni Proje iletişim kutusu")

   Boş bir C++ Windows konsol uygulaması oluşturulur. Konsol uygulamaları, çıktıyı görüntülemek ve kullanıcı girişini kabul etmek için windows konsol penceresi kullanır. Visual Studio'da bir düzenleyici penceresi açılır ve oluşturulan kodu gösterir:

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

## <a name="verify-that-your-new-app-builds-and-runs"></a>Yeni uygulamanızın oluşturduğunu ve çalıştığını doğrulayın

Yeni bir windows konsolu uygulaması için şablon basit bir C++ "Hello World" uygulaması oluşturur. Bu noktada Visual Studio'nun oluşturduğunuz uygulamaları nasıl oluşturduğunu ve çalıştırdığını IDE'den görebilirsiniz.

1. Projenizi oluşturmak için **Yapı** menüsünden **Çözüm Oluştur'u** seçin. **Çıktı** penceresi yapı işleminin sonuçlarını gösterir.

   ![Projeyi derleme](./media/calculator-initial-build-output.png "Projeyi derleme")

1. Kodu çalıştırmak için menü çubuğunda **Hata**Ayıklama'yı seçin, **hata ayıklama dan başlat.**

   ![Projeyi başlatın](./media/calculator-hello-world-console.png "Projeyi başlatın")

   Bir konsol penceresi açılır ve ardından uygulamanızı çalıştırır. Visual Studio'da bir konsol uygulaması başlattığınızda, kodunuzu çalıştırır ve ardından "Devam etmek için herhangi bir tuşa basın. . ." çıktıyı görme şansı vermek için. Tebrikler! İlk "Merhaba, dünya!" Visual Studio konsol uygulaması!

1. Konsol penceresini kapatmak ve Visual Studio'ya dönmek için bir tuşa basın.

Artık, kodun hala beklediğiniz gibi çalıştığını doğrulamak için her değişiklikten sonra uygulamanızı oluşturmak ve çalıştırmak için araçlara sahipsiniz. Daha sonra, değilse nasıl hata ayıklama göstereceğiz.

## <a name="edit-the-code"></a>Kodu edin

Şimdi bu şablondaki kodu bir hesap makinesi uygulamasına dönüştürelim.

1. *CalculatorTutorial.cpp* dosyasında, kodu aşağıdaki örneğe uyacak şekilde edin:

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
   > - İfadeler, `#include` diğer dosyalarda bulunan koda başvuru göndermenizi sağlar. Bazen, açı parantezi ile çevrili bir**\<** dosya adı görebilirsiniz ( ); diğer zamanlarda, tırnak ile çevrilidir (**" " ).** Genel olarak, C++ Standart Kitaplığı'na başvururken açı ayraçları kullanılırken, diğer dosyalar için tırnak işaretleri kullanılır.
   > - `#include "pch.h"` (veya Visual Studio 2017 ve `#include "stdafx.h"`önceki) satırı önceden derlenmiş üstbilgi olarak bilinen bir şeye başvurur. Bunlar genellikle derleme sürelerini geliştirmek için profesyonel programcılar tarafından kullanılır, ancak bu öğreticikapsamı dışındadır.
   > - Satır `using namespace std;` derleyiciye C++ Standart Kitaplığı'ndan gelen şeylerin bu dosyada kullanılmasını beklemesini söyler. Bu satır olmadan, kitaplıktaki her anahtar kelimenin `std::`kapsamını belirtmek için bir , önce olması gerekir. Örneğin, bu satır olmadan, `cout` her başvuru olarak `std::cout`yazılması gerekir . İfade, `using` kodun daha temiz görünmesi için eklenir.
   > - `cout` Anahtar kelime, C++'da standart çıktıyazdırmak için kullanılır. Operatör ** \< ** derleyiciye, sağındaki her şeyi standart çıktıya göndermesini söyler.
   > - **Endl** anahtar kelimesi Enter tuşu gibidir; satırı sona erdirir ve imleci bir sonraki satıra taşır. Her `\n` `endl` zaman tampon temizler ve programın performansını zarar verebilir, aynı şeyi yapmak için dize ("" tarafından bulunan) içine koymak için daha `endl` iyi bir uygulamadır, ancak bu çok küçük bir uygulama olduğu için, daha iyi okunabilirlik için kullanılır.
   > - Tüm C++ deyimleri yarı nokta nokta ile sona ermeli ve tüm C++ uygulamaları bir `main()` işlev içermelidir. Bu işlev, programın başlangıçta çalıştırılabır. Kullanılabilmesi için tüm `main()` kodlardan erişilebilir olması gerekir.

1. Dosyayı kaydetmek için **Ctrl+S**girin veya menü çubuğunun altındaki araç çubuğundaki disket simgesi olan IDE'nin üst kısmındaki **Kaydet** simgesini seçin.

1. Uygulamayı çalıştırmak için **Ctrl+F5** tuşuna basın veya **Hata Ayıklama** menüsüne gidin ve **Hata Ayıklama olmadan Başlat'ı**seçin. **Bu projenin güncel olmadığını**belirten bir açılır pencere alırsanız, bu iletişim kutusunu tekrar **gösterme'yi**seçebilir ve ardından uygulamanızı oluşturmak için **Evet'i** seçebilirsiniz. Kodda belirtilen metni görüntüleyen bir konsol penceresi görmeniz gerekir.

   ![Uygulamanızı oluşturun ve başlatın](./media/calculator-first-launch.gif "Uygulamanızı oluşturun ve başlatın")

1. Bitirdiğinizde konsol penceresini kapatın.

## <a name="add-code-to-do-some-math"></a>Bazı matematik yapmak için kod ekleme

Biraz matematik mantığı eklemenin zamanı.

### <a name="to-add-a-calculator-class"></a>Hesap Makinesi sınıfı eklemek için

1. **Proje** menüsüne gidin ve **Sınıf Ekle'yi**seçin. Sınıf **Adı** edit kutusuna *Hesap Makinesi'ni*girin. **Tamam'ı**seçin. Projenize iki yeni dosya eklenir. Değiştirilen tüm dosyalarınızı aynı anda kaydetmek için **Ctrl+Shift+S**tuşuna basın. **Tümlerini** > **Kaydet**için bir klavye kısayolu. Save butonunun yanında bulunan iki disket simgesi olan **Tümleri Kaydet**için bir araç çubuğu düğmesi de vardır. **Save** Genel olarak, tümlerini sık sık **kaydet** yapmak iyi bir uygulamadır, böylece kaydederken hiçbir dosyayı kaçırmazsınız.

   ![Hesap Makinesi sınıfını oluşturma](./media/calculator-create-class.gif "Hesap Makinesi sınıfını oluşturma")

   Sınıf, bir şey yapan bir nesnenin planı gibidir. Bu durumda, bir hesap makinesi ve nasıl çalışması gerektiğini tanımlar. Yukarıda kullandığınız **Sınıf Ekle** sihirbazı, sınıfla aynı ada sahip .h ve .cpp dosyalarını oluşturdu. IDE'nin yan tarafında görünen **Çözüm Gezgini** penceresinde proje dosyalarınızın tam listesini görebilirsiniz. Pencere görünmüyorsa, menü çubuğundan açabilirsiniz:**Çözüm Gezgini** **Görüntüle'yi** > seçin.

   ![Çözüm Gezgini](./media/calculator-solution-explorer.png "Çözüm Gezgini")

   Şimdi editör açık üç sekmeleri olmalıdır: *CalculatorTutorial.cpp*, *Calculator.h*, ve *Calculator.cpp*. Bunlardan birini yanlışlıkla kapatırsanız, **Çözüm Gezgini** penceresinde çift tıklatarak yeniden açabilirsiniz.

1. **Calculator.h'de,** `Calculator();` burada `~Calculator();` ihtiyacınız olmayacağından oluşturulan satırları ve satırları kaldırın. Ardından, dosyanın şimdi şuna benzemesi için aşağıdaki kod satırını ekleyin:

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
   > - Eklediğiniz satır, toplama, çıkarma, çarpma ve bölme için matematik işlemlerini çalıştırmak için kullanacağımız yeni bir işlev bildirir. `Calculate`
   > - C++ kodu *üstbilgi* (.h) dosyaları ve *kaynak* (.cpp) dosyaları olarak düzenlenir. Diğer birkaç dosya uzantıları çeşitli derleyiciler tarafından desteklenir, ancak bunlar hakkında bilinmesi gereken ana olanlar dır. İşlevler ve değişkenler *normalde,* yani üstbilgi dosyalarında bir ad ve tür verilir ve kaynak dosyalarında *uygulanır*veya bir tanım verilir. Başka bir dosyada tanımlanan koda `#include "filename.h"`erişmek için, 'filename.h'nin kullanmak istediğiniz değişkenleri veya işlevleri bildiren dosyanın adı olduğu bir durum kullanabilirsiniz.
   > - Sildiğiniz iki satır, sınıf için *bir oluşturucu* ve *yıkıcı* olarak bildirilir. Bunun gibi basit bir sınıf için derleyici bunları sizin için oluşturur ve kullanımları bu öğreticinin kapsamı dışındadır.
   > - Kodunuzu ne yaptığına göre farklı dosyalarhalinde düzenlemek iyi bir uygulamadır, bu nedenle daha sonra gereksinim duyduğunuz kodu kolayca bulabilirsiniz. Bizim `Calculator` durumumuzda, sınıfı `main()` işlevi içeren dosyadan ayrı olarak tanımlarız, `Calculator` ancak `main()`'deki sınıfa başvurmayı planlıyoruz.

1. Altında yeşil bir dalgalı belirir. `Calculate` Çünkü .cpp dosyasındaki `Calculate` işlevi tanımlamadık. Kelimenin üzerine yıkın, açılan ampulü tıklatın ve **Hesap Makinesi.cpp'de 'Hesapla' tanımını oluştur'u**seçin. Diğer dosyada yapılan kod değişikliğine göz atmanızı sağlayan bir açılır pencere görüntülenir. Kod *Hesap Makinesi.cpp*eklendi.

   ![Hesapla tanımı nı oluştur](./media/calculator-create-definition.gif "Hesapla tanımı nı oluştur")

   Şu anda, sadece 0.0 döndürür. Şimdi bunu değiştirelim. Açılır pencereyi kapatmak için **Esc** tuşuna basın.

1. Düzenleyici penceresindeki *Hesap Makinesi.cpp* dosyasına geçin. Bölümleri `Calculator()` ve `~Calculator()` bölümleri kaldırın (.h dosyasında yaptığınız gibi) `Calculate()`ve aşağıdaki kodu ekleyin:

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
   > - İşlev `Calculate` bir sayı, bir işleç ve ikinci bir sayı tüketir, sonra sayılar üzerinde istenen işlemi gerçekleştirir.
   > - Anahtar deyimi hangi işlecinin sağlandığını denetler ve yalnızca bu işlek karşılık gelen servis talebiyürütür. Varsayılan: servis talebi, kullanıcının kabul edilmeyen bir işleç tipleme ihtimaline karşı bir geri dönüştür, bu nedenle program kırılmaz. Genel olarak, geçersiz kullanıcı girişlerini daha zarif bir şekilde işlemek en iyisidir, ancak bu, bu öğreticinin kapsamı dışındadır.
   > - Anahtar `double` kelime, ondalık sayıları destekleyen bir sayı türünü gösterir. Bu şekilde, hesap makinesi hem ondalık matematik hem de tamsayı matematiği işleyebilir. İşlev, `Calculate` kodun en başında (bu `double` işlevin dönüş türünü gösterir) nedeniyle her zaman böyle bir sayıyı döndürmek için gereklidir, bu nedenle varsayılan durumda bile 0.0 döndürürüz.
   > - .h dosyası, derleyiciye hangi parametreleri gerektirdiğini ve hangi iade türünü ondan bekleyeceğini önceden söyleyen işlev *prototipini*bildirir. .cpp dosyası işlevin tüm uygulama ayrıntılarına sahiptir.

Bu noktada kodu yeniden oluşturur ve çalıştırın, hangi işlemi gerçekleştireceğini sorduktan sonra yine çıkar. Ardından, bazı hesaplamalar `main` yapmak için işlevi değiştirirsiniz.

### <a name="to-call-the-calculator-class-member-functions"></a>Hesap Makinesi sınıfı üye işlevlerini aramak için

1. Şimdi `main` *CalculatorTutorial.cpp*işlevini güncelleştirelim:

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
   > - C++ programları her zaman `main()` işlevden başladığı için, diğer kodumuzu `#include` oradan aramamız gerekir, bu nedenle bir ifade gereklidir.
   > - Bazı ilk `x` `y`değişkenler, , , `oper`ve `result` sırasıyla ilk sayı, ikinci sayı, işleç ve nihai sonucu depolamak için bildirilir. Tanımsız davranışlardan kaçınmak için onlara bazı başlangıç değerleri vermek her zaman iyi bir uygulamadır, ki bu da burada yapılan şeydir.
   > - Satır `Calculator c;` sınıfın bir örneği `Calculator` olarak 'c' adlı bir nesne bildirir. Sınıfın kendisi, hesap makinelerinin nasıl çalıştığına yönelik bir plandır; nesne, matematiği yapan özel hesap makinesidir.
   > - `while (true)` İfade bir döngüdür. Döngü içindeki kod, içindeki koşul doğru olduğu sürece tekrar `()` tekrar yürütmeye devam ediyor. Durum sadece olarak `true`listelenen bu yana , her zaman doğrudur, bu yüzden döngü sonsuza kadar çalışır. Programı kapatmak için, kullanıcının konsol penceresini el ile kapatması gerekir. Aksi takdirde, program her zaman yeni giriş bekler.
   > - `cin` Anahtar kelime, kullanıcıdan giriş kabul etmek için kullanılır. Bu giriş akışı, konsol penceresine girilen bir metin satırını işlemek ve kullanıcı girişinin gerekli belirtimle eşleştiğini varsayarak sırayla listelenen değişkenlerin her birine yerleştirmek için yeterince akıllıdır. Bu satırı, örneğin ikiden fazla sayı yı kabul edecek şekilde değiştirebilirsiniz, ancak işlevin `Calculate()` de bunu işlemek için güncelleştirilmesi gerekir.
   > - İfade `c.Calculate(x, oper, y);` daha `Calculate` önce tanımlanan işlevi çağırır ve girilen giriş değerlerini sağlar. İşlev daha sonra depolanan bir `result`sayı döndürür.
   > - Son `result` olarak, konsola yazdırılır, böylece kullanıcı hesaplama sonucunu görür.

### <a name="build-and-test-the-code-again"></a>Kodu yeniden oluşturma ve test edin

Şimdi her şeyin düzgün çalıştığından emin olmak için programı tekrar test etme zamanı.

1. Uygulamayı yeniden oluşturmak ve başlatmak için **Ctrl+F5** tuşuna basın.

1. Girin `5 + 5`ve **Enter**tuşuna basın. Sonucun 10 olduğunu doğrulayın.

   ![5 + 5 sonucu](./media/calculator-five-plus-five.png "5 + 5 sonucu")

## <a name="debug-the-app"></a>Uygulamayı hata ayıklama

Kullanıcı konsol penceresine bir şey yazmakta özgür olduğundan, hesap makinesinin beklendiği gibi bazı girdileri işlediğinden emin olalım. Programı çalıştırmak yerine, bunun yerine hata ayıklayalım, böylece ne yaptığını ayrıntılı olarak inceleyelim, adım adım.

### <a name="to-run-the-app-in-the-debugger"></a>Uygulamayı hata ayıklamada çalıştırmak için

1. Kullanıcıdan `result = c.Calculate(x, oper, y);` giriş istendikten hemen sonra, satırda bir kesme noktası ayarlayın. Kesme noktasını ayarlamak için, düzenleyici penceresinin sol kenarındaki gri dikey çubuktaki satırın yanına tıklayın. Kırmızı bir nokta belirir.

   ![Kesme noktası ayarlama](./media/calculator-set-breakpoint.gif "Kesme noktası ayarlama")

   Şimdi programı hata ayıklamamız, her zaman bu satırda yürütme duraklar. Biz zaten program basit durumlarda çalışır kaba bir fikir var. Yürütmeyi her seferinde duraklatmak istemediğimiz için, kırılma noktasını koşullu hale getirelim.

1. Kesme noktasını temsil eden kırmızı noktayı sağ tıklatın ve **Koşullar'ı**seçin. Durum için edit kutusuna `(y == 0) && (oper == '/')`girin. Bittiğinde **Kapat** düğmesini seçin. Koşul otomatik olarak kaydedilir.

   ![Koşullu bir kesme noktası ayarlama](./media/calculator-conditional-breakpoint.gif "Koşullu bir kesme noktası ayarlama")

   Şimdi, özellikle 0'a kadar bir bölme denenmişse, kesme noktasında yürütmeyi duraklatıyoruz.

1. Programı hata ayıklamak için **F5**tuşuna basın veya yeşil ok simgesine sahip **Yerel Windows Hata Ayıklayıcı** araç çubuğu nu seçin. Konsol uygulamanızda , "5 - 0" gibi bir şey girerseniz, program normal şekilde çalışır ve çalışmaya devam eder. Ancak, "10 / 0" yazarsanız, kesme noktasında duraklar. Hatta operatör ve sayılar arasında herhangi bir sayıda boşluk koyabilirsiniz; `cin` girişi uygun şekilde ayrıştıracak kadar akıllıdır.

   ![Koşullu kesme noktasında duraklatma](./media/calculator-debug-conditional.gif "Koşullu kesme noktasında duraklatma")

### <a name="useful-windows-in-the-debugger"></a>Hata ayıklamada kullanışlı pencereler

Kodunuzu hata ayıklamanızda, bazı yeni pencerelerin göründüğünü fark edebilirsiniz. Bu pencereler hata ayıklama deneyiminize yardımcı olabilir. **Autos** penceresine bir göz atın. **Otomatik Ayar** penceresi, geçerli satırdan önce ve en fazla üç satır da kullanılan değişkenlerin geçerli değerlerini gösterir.

   ![Otomatik ler penceresi](./media/calculator-autos.png "Otomatik ler penceresi")

Bu işlevdeki tüm değişkenleri görmek için **Yereller** penceresine geçin. Hata ayıklama sırasında bu değişkenlerin değerlerini değiştirerek program üzerinde nasıl bir etki yaratacağını görebilirsiniz. Bu durumda, onları rahat bırakacağız.

   ![Yerel ler penceresi](./media/calculator-locals.png "Yerel ler penceresi")

Ayrıca, yürütmenin şu anda duraklatılmış olduğu geçerli değerlerini görmek için kodun kendisindeki değişkenlerin üzerinde gezinmeniz de mümkündür. Önce üzerine tıklayarak düzenleyici penceresinin odakta olduğundan emin olun.

   ![Geçerli değişken değerlerini görüntülemek için gezinme](./media/calculator-hover-tooltip.gif "Geçerli değişken değerlerini görüntülemek için gezinme")

### <a name="to-continue-debugging"></a>Hata ayıklama devam etmek için

1. Soldaki sarı çizgi geçerli yürütme noktasını gösterir. Geçerli satır `Calculate`çağrıları, bu nedenle işlevin **içine adım** **f11** tuşuna basın. Kendini `Calculate` fonksiyonun bedeninde bulacaksın. **Step Into**ile dikkatli olun ; Eğer çok fazla yaparsanız, çok fazla zaman kaybedebilirsiniz. Standart kitaplık işlevleri de dahil olmak üzere, kullandığınız herhangi bir koda gider.

1. Yürütme noktası `Calculate` işlevin başlangıcında olduğuna göre, programın yürütülmesinde bir sonraki satıra geçmek için **F10** tuşuna basın. **F10,** Step **Over**olarak da bilinir. Satırın her bölümünde meydana gelen ayrıntıları delving olmadan, satırdan satıra taşımak için **Adım Üzerinde** kullanabilirsiniz. Genel olarak **Step Into**yerine Step `Calculate` **Over'ı** kullanmalısınız , eğer başka bir yerden çağrılan koda daha derinden dalmak istemiyorsanız (vücuduna ulaşmak için yaptığınız gibi).

1. Diğer dosyadaki `main()` işleve geri dönene kadar **F10'u** her satırın `cout` **üzerine** basmak için kullanmaya devam edin ve satırı durdurun.

   ![Hesapla'dan çıkın ve sonucu kontrol edin](./media/calculator-undefined-zero.gif "Hesapla'dan çıkın ve sonucu kontrol edin")

   Program bekleneni yapıyor gibi görünüyor: ilk sayıyı alır ve ikinciye böler. Satırda, `cout` değişkenin üzerine `result` doğru gezin `result` veya **Otomatik Ler** penceresinden bir göz atın. Değerinin "inf" olarak listelendiğini göreceksiniz, bu da doğru görünmüyor, bu yüzden düzeltelim. Satır `cout` sadece hangi değer depolanırsa `result`depolanır, bu yüzden **F10**kullanarak bir satır daha ileri adım attığınızda, konsol penceresi görüntüler:

   ![Sıfıra bölmenin sonucu](./media/calculator-divide-by-zero-fail.png "Sıfıra bölmenin sonucu")

   Bu sonuç, sıfıra bölme tanımlı olduğundan, programın istenen işlem için sayısal bir yanıtı olmadığından ortaya çıkan sonuçtur.

### <a name="to-fix-the-divide-by-zero-error"></a>"Sıfıra böl" hatasını düzeltmek için

Bölümü sıfıra göre daha ince likle ele alalım, böylece kullanıcı sorunu anlayabilir.

1. *CalculatorTutorial.cpp'de*aşağıdaki değişiklikleri yapın. **(Edit ve Continue**adlı hata ayıklama özelliği sayesinde programı düzenledikçe çalışır durumda bırakabilirsiniz):

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

1. Şimdi bir kez **F5 tuşuna** basın. Program yürütme kullanıcı girişi istemek için duraklatmak zorunda kadar tüm yol boyunca devam ediyor. Tekrar `10 / 0` girin. Şimdi, daha yararlı bir ileti yazdırılır. Kullanıcıdan daha fazla giriş istenir ve program normal olarak yürütmeye devam edilir.

   ![Değişikliklerden sonraki nihai sonuç](./media/calculator-final-verification.gif "Değişikliklerden sonraki nihai sonuç")

   > [!Note]
   > Hata ayıklama modundayken kodu değiştirdiğinizde, kodun eskime riski vardır. Bu, hata ayıklayıcı eski kodunuzu çalıştırmaya devam ettiğinde ve değişiklikleriniz ile henüz güncelleştirmiyorsa gerçekleşir. Hata ayıklama, bu durumda sizi bilgilendirmek için bir iletişim kutusu açılır. Bazen, yürütülmekte olan kodu yenilemek için **F5** tuşuna basmanız gerekebilir. Özellikle, yürütme noktası bu işlevin içindeyken bir işlev in içinde bir değişiklik yaparsanız, güncelleştirilmiş kodu almak için işlevin dışına çıkmanız ve ardından yeniden bu işleve geri dönmeniz gerekir. Bu bir nedenle işe yaramazsa ve bir hata iletisi görüyorsanız, IDE'nin üst kısmındaki menülerin altındaki araç çubuğundaki kırmızı kareyi tıklatarak hata ayıklamayı durdurabilirsiniz, ardından **F5** girerek veya araç çubuğundaki dur düğmesinin yanındaki yeşil "play" okunu seçerek yeniden hata ayıklamaya başlayabilirsiniz.

   > Çalıştır ve Hata Ayıklama kısayollarını anlama
   >
   > - **F5** (veya **Hata Ayıklama** > **Hata Ayıklama)** biri zaten etkin değilse hata ayıklama oturumu başlatır ve bir kesme noktası vurulana veya programın kullanıcı girişine ihtiyacı olana kadar programı çalıştırUr. Kullanıcı girişi gerekmezse ve vurmak için bir kesme noktası yoksa, program sonlandırır ve program çalışırken bittiğinde konsol penceresi kendini kapatır. Çalıştırmak için "Hello World" programı gibi bir şey varsa, pencereaçık tutmak için **F5** girmeden önce **Ctrl+F5** kullanın veya bir kesme noktası ayarlayın.
   > - **Ctrl+F5** (veya Hata **Ayıklama** > Olmadan Hata**Ayıklama)** hata ayıklama moduna girmeden uygulamayı çalıştırır. Bu hata ayıklama biraz daha hızlı ve program yürütme tamamladıktan sonra konsol penceresi açık kalır.
   > - **F10** **(Adım Ataşma**olarak bilinir) kod, satır satır gezinmenizi ve kodun nasıl çalıştırıldığını ve yürütmenin her adımında hangi değişken değerlerinin olduğunu görselleştirmenize olanak tanır.
   > - **F11** **(Step Into**olarak da bilinir) **Step Over'a**benzer şekilde çalışır, ancak yürütme satırında çağrılan işlevlere adım atar. Örneğin, yürütülen satır bir işlevi çağırırsa, **F11** tuşuna basıldığında işaretçiyi işlevin gövdesine taşır, böylece başladığınız satıra geri dönmeden önce işlevin kodunun çalıştırıldığını izleyebilirsiniz. **F10** tuşuna basarak işlev çağrısının üzerine basar ve bir sonraki satıra geçer; işlev çağrısı yine de gerçekleşir, ancak program ne yaptığını göstermek için duraklatmaz.

### <a name="close-the-app"></a>Uygulamayı kapat

- Çalışıyorsa, hesap makinesi uygulaması için konsol penceresini kapatın.

## <a name="the-finished-app"></a>Bitmiş uygulama

Tebrikler! Hesap makinesi uygulamasının kodunu tamamladınız ve Visual Studio'da oluşturup debugged.

## <a name="next-steps"></a>Sonraki adımlar

[C++ için Visual Studio hakkında daha fazla bilgi edinin](https://blogs.msdn.microsoft.com/vcblog/2017/04/21/getting-started-with-visual-studio-for-c-and-cpp-development/)

::: moniker-end
