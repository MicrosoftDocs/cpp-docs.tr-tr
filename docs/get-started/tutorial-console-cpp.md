---
title: C++ konsol uygulama projesi oluşturma
description: Visual c++'ta bir Hello World konsol uygulaması oluşturma
ms.custom: mvc
ms.date: 03/25/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 1b2fe7b95ec27a559de73673412cb2d28507b656
ms.sourcegitcommit: 6e4dd21759caaed262a7255735cf8d6e8fb9f4d7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58476883"
---
# <a name="create-a-c-console-app-project"></a>C++ konsol uygulama projesi oluşturma

Her zamanki başlangıç noktası C++ programcısı için bir "Hello, world!" komut satırı üzerinde çalışan uygulama. Hangi Visual Studio'da bu makaledeki oluşturacağınız olmasıdır.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio ile masaüstü geliştirme, yüklü ve bilgisayarınızda çalışan C++ iş yükünde sahip. Henüz yüklü değilse, bkz. [Visual Studio 2017'de C++ yükleme desteği](../build/vscpp-step-0-installation.md).

## <a name="create-your-app-project"></a>Uygulama projenizi oluşturun

Visual Studio kullanan *projeleri* bir uygulama için kod düzenleme ve *çözümleri* projelerinizi düzenlemek için. Bir proje, tüm seçenekleri, yapılandırmaları ve uygulamalarınızı oluşturmak için kullanılan kuralları içerir. Tüm proje dosyaları ve dış dosyaları arasındaki ilişki da yönetir. Uygulamanızı oluşturmak için ilk olarak, yeni proje ve çözüm oluşturacaksınız.

1. Visual Studio menü seçin **dosya** > **yeni** > **proje**. **Yeni proje** penceresi açılır.

2. Sol Kenar çubuğunda emin **Visual C++** seçilir. Merkezinde **Windows konsol uygulaması**.

3. İçinde **adı** alttaki düzenleme, yeni proje adını *CalculatorTutorial*, ardından **Tamam**.

   ![Yeni Proje iletişim](./media/calculator-new-project-dialog.png "yeni proje iletişim kutusu")

   Boş bir C++ Windows konsol uygulaması oluşturulur. Konsol uygulamaları, bir Windows konsol penceresi çıkışını görüntülemek ve kullanıcı girişi kabul etmek için kullanın. Visual Studio'da bir düzenleyici penceresi açılır ve oluşturulan kodun gösterir:

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

## <a name="verify-that-your-new-app-builds-and-runs"></a>Yeni uygulamanız derlenir ve çalışır olduğunu doğrulayın

Yeni bir windows konsol uygulaması şablonu, basit bir C++ "Hello World" uygulaması oluşturur. Bu noktada, Visual Studio nasıl oluşturur ve doğrudan IDE'den oluşturduğunuz uygulamalar çalıştıran görebilirsiniz.

1. Projenizi tercih **Çözümü Derle** gelen **derleme** menüsü. **Çıkış** penceresi yapı işleminin sonuçlarını gösterir.

   ![Proje derleme](./media/calculator-initial-build-output.png "projeyi oluşturun")

1. Menü çubuğunda kodu çalıştırmak için tercih **hata ayıklama**, **ayıklamadan Başlat**.

   ![Proje başlangıç](./media/calculator-hello-world-console.png "projeyi Başlat")

   Bir konsol penceresi açar ve ardından uygulamanızı çalıştırır. Visual Studio'da konsol uygulaması başlattığınızda, kodunuz çalışır ve ardından baskı siparişi "devam etmek için herhangi bir tuşa basın. biçimindeki telefon numarasıdır. ." Çıktıyı görmek için bir fırsat vermek için. Tebrikler! İlk oluşturduğunuz "Hello, world!" Visual Studio'da konsol uygulaması!

1. Konsol penceresini kapatın ve Visual Studio'ya dönmek için bir tuşa basın.

Artık derleme ve beklediğiniz gibi kodu hala çalışır durumda olduğunu doğrulamak için her değişiklikten sonra uygulamanızı çalıştırmak için araçlar vardır. Daha sonra bu gereksinimleri karşılamıyorsa hata ayıklama göstereceğiz.

## <a name="edit-the-code"></a>Kodu düzenleme

Artık kod hesaplayıcı uygulamaya bu şablonda dönelim.

1. İçinde *CalculatorTutorial.cpp* dosya, bu örnekle eşleşmesi için kodu düzenleyin:

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

   > Kod anlama:
   >
   > - `#include` Deyimleri diğer dosyalarında bulunan koduna başvuru sağlar. Bazı durumlarda, açılı ayraç içine bir dosya adı görebilirsiniz (**\<\>**); diğer durumlarda, tırnak işareti içine alınmış (**""**). Genel olarak, açılı ayraçlar diğer dosyalar için tırnak işaretleri kullanılırken, C++ Standart Kitaplığı başvururken kullanılır.
   > - `#include "pch.h"` (Veya Visual Studio'nun eski sürümlerinde `#include "stdafx.h"`) satırı önceden derlenmiş üst bilgi olarak bilinen bir sorun başvuruyor. Bunlar genellikle profesyonel programcılar tarafından derlemeyi sürelerini geliştirmek için kullanılır, ancak bunlar Bu öğreticinin kapsamı dışındadır.
   > - `using namespace std;` Satırı öğe bu dosyada kullanılan C++ Standart Kitaplığı'ndan beklenir derleyiciye. Bu satırı kitaplığından her anahtar sözcüğü ile öncesinde zorunda bir `std::`kapsamını belirtmek için. Örneğin, bu satırı her başvuru `cout` olarak yazılması gerekir `std::cout`. `using` Deyimi daha temiz arayın kodun eklenir.
   > - `cout` Anahtar sözcüğü, c++ standart çıktıya yazdırmak için kullanılır. **\< \<** İşleci sağındaki bunu standart çıktıya ne olursa olsun göndermek için derleyiciye.
   > - **Endl** anahtar sözcüğü, gibi Enter tuşuna; satır sona erer ve imleci sonraki satıra taşır. Koymak için daha iyi bir uygulamadır bir `\n` dizenin içine (tarafından bulunan "") olarak aynı şeyi yapmak için `endl` her zaman arabelleği temizler ve programın, ancak bu çok küçük bir uygulama olduğu için performansı olumsuz etkileyebilir `endl` daha iyi için bunun yerine kullanılır Okunabilirlik.
   > - Tüm C++ deyimleri, noktalı virgül ile bitmelidir ve tüm C++ uygulamalarını içermesi gereken bir `main()` işlevi. Bu işlev, program başlangıcında çalıştırılanlar kullanılır. Tüm kod erişilebilir `main()` kullanılabilmesi için.

1. Dosyayı kaydetmek için girin **Ctrl + S**, ya da seçin **Kaydet** IDE, araç çubuğundaki menü çubuğunun altındaki disket simgesini üst kısmındaki simgesi.

1. Uygulamayı çalıştırmak için basın **Ctrl + F5** veya Git **hata ayıklama** menüsünü seçip **hata ayıklama olmadan Başlat**. Bildiren bir açılır pencere alırsanız **bu proje güncel değil**, seçtiğiniz **bu iletişim kutusunu bir daha gösterme**ve ardından **Evet** uygulamanızı oluşturmak için. Kod içinde belirtilen metni görüntüleyen bir konsol penceresi görünür görmeniz gerekir.

   ![Derleme ve uygulamanızı başlatın](./media/calculator-first-launch.gif "oluşturun ve uygulamanızı başlatın")

1. İşiniz bittiğinde, konsol penceresini kapatın.

## <a name="add-code-to-do-some-math"></a>Bazı matematik için kod ekleyin

Bu, bazı matematik mantığı ekleme zamanı geldi.

### <a name="to-add-a-calculator-class"></a>Hesaplayıcı sınıfı eklemek için

1. Git **proje** menüsünü seçip **sınıfı Ekle**. İçinde **sınıf adı** düzenleme kutusu, girin *hesaplayıcı*. **Tamam**’ı seçin. İki yeni dosyayı projenize eklenir. Tek seferde tüm değiştirilen dosyaları kaydetmek için basın **Ctrl + Shift + S**. Bir klavye kısayol bulunur **dosya** > **Tümünü Kaydet**. Toolbar düğmesi için de mevcuttur **Tümünü Kaydet**, simge yanında bulunan iki disket disk **Kaydet** düğmesi. Genel olarak, bunu yapmak için iyi bir uygulamadır **Tümünü Kaydet** sık, bu nedenle, yoksa kaçırmayın dosyalarla kaydettiğinizde.

   ![Hesaplayıcı sınıfı oluşturmak](./media/calculator-create-class.gif "hesaplayıcı sınıfı oluşturma")

   Blueprint işi yapan bir nesne için bir sınıf gibidir. Bu durumda, bir hesap makinesi ve nasıl çalışması gereken tanımlarız. **Sınıfı Ekle** yukarıda kullanılan sihirbaz oluşturulan sınıf aynı ada sahip .h ve .cpp dosyaları. Proje dosyalarınızı tam listesini görebilirsiniz **Çözüm Gezgini** penceresi, IDE'nin kenarındaki görünür. Pencerenin görünür değilse, menü çubuğundan açabilirsiniz: seçin **görünümü** > **Çözüm Gezgini**.

   ![Çözüm Gezgini](./media/calculator-solution-explorer.png "Çözüm Gezgini")

   Artık üç sekme düzenleyicide açık olması gerekir: *CalculatorTutorial.cpp*, *Calculator.h*, ve *Calculator.cpp*. Bunlardan birini yanlışlıkla kapatırsanız, bu çift tıklayarak açabilirsiniz **Çözüm Gezgini** penceresi.

1. İçinde **Calculator.h**, kaldırma `Calculator();` ve `~Calculator();` burada gerekmez bu yana, oluşturulan satır. Ardından, dosyayı şimdi şuna benzer şekilde aşağıdaki kod satırını ekleyin:

    ```cpp
    #pragma once
    class Calculator
    {
    public:
        double Calculate(double x, char oper, double y);
    };
    ```

   > Kod anlama
   >
   > - Eklediğiniz satırı olarak adlandırılan yeni bir işlev bildirir `Calculate`, hangi toplama, çıkarma, çarpma ve bölme matematik işlemlerini çalıştırmak için kullanacağız.
   > - C++ kod içine düzenlenir *üstbilgi* (.h) dosyaları ve *kaynak* (.cpp) dosyaları. Birkaç diğer dosya uzantıları çeşitli derleyiciler tarafından desteklenir, ancak bunlar hakkında bilgi edinmek için ana olanlardır. İşlevler ve değişkenler olan normalde *bildirilen*, diğer bir deyişle, verilen bir ad ve başlık dosyaları içinde bir tür ve *uygulanan*, veya kaynak dosyalarında bir tanımını ele alalım. Başka bir dosyada tanımlanan erişim kodu için kullanabileceğiniz `#include "filename.h"`, burada 'filename.h' değişkenleri veya kullanmak istediğiniz işlevleri bildirir dosyanın adıdır.
   > - Sildiğiniz satırlarını bildirilen bir *Oluşturucusu* ve *yok Edicisi* sınıfı. Bunun gibi basit bir sınıf, derleyici bunları sizin için oluşturur ve bu öğreticinin kapsamı dışındadır kullanımları şunlardır.
   > - Kodunuzun ne işe yaradığını üzerinde daha sonra ihtiyacınız olan kod bulmak kolaydır bağlı olarak farklı dosyaları düzenlemek için iyi bir uygulamadır. Bu örnekte, tanımlarız `Calculator` sınıfı içeren dosyanın listesinden `main()` işlevi, ancak planlama başvurmak `Calculator` sınıfını `main()`.

1. Altında görünür bir yeşil dalgalı göreceğiniz `Calculate`. Henüz tanımladığımız çünkü `Calculate` .cpp dosyası işlevi. Word'ün gelin, açılır ampule ve seçme **'Hesapla' tanımı içinde Calculator.cpp oluşturma**. Diğer dosyada yapılan kod değişikliğinin bir Özet sunan bir açılır pencere görüntülenir. Kod eklendi *Calculator.cpp*.

   ![Calculate tanımını oluşturma](./media/calculator-create-definition.gif "Calculate tanımını oluşturun")

   Şu anda yalnızca 0,0 döndürür. Değiştirelim. Tuşuna **Esc** açılan pencereyi kapatın.

1. Geçiş *Calculator.cpp* düzenleyici penceresinde dosya. Kaldırma `Calculator()` ve `~Calculator()` bölümleri (.h dosyasındaki yaptığınız gibi) ve aşağıdaki kodu ekleyin `Calculate()`:

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

   > Kod anlama
   >
   > - İşlev `Calculate` bir sayı, bir işleç ve ikinci sayı kullanır ve sayı üzerinde istenen işlemi gerçekleştirir.
   > - Hangi işleci sağlanan ve yalnızca switch deyimi denetimleri, bu işlem için karşılık gelen durum yürütür. Varsayılan: durumda program sonu gelmez bir şekilde kabul değil, operatör kullanıcı türleri bir geri dönüş durum geçerlidir. Genel olarak, daha zarif bir şekilde geçersiz kullanıcı girişlerini işler en iyisidir ancak bu, bu öğreticinin kapsamı dışındadır.
   > - `double` Anahtar sözcüğü destekleyen ondalık sayı türü gösterir. Bu şekilde, ondalık matematik hem tamsayı matematiğini hesaplayıcı başa çıkabilir. `Calculate` İşlevi her zaman böyle bir sayıya son döndürmek için gerekli `double` olmasının nedeni çok başlangıcında (Bu gösterir işlevin dönüş türü), kod biz 0,0 varsayılan durumda bile döndürür.
   > - .H dosyası işlev bildirir *prototip*gerektiren parametreleri derleyici önceden bildirir ve hangi dönüş türünü bekleyebilir. İşlevin tüm uygulama ayrıntılarını .cpp dosyası vardır.

Oluşturun ve tekrar bu noktada kod çalıştırmak, konsolda "Hello World" yine de gösterilir. Ardından, değiştireceksiniz `main` bazı hesaplamalar yapmak için işlevi.

### <a name="to-call-the-calculator-class-member-functions"></a>Hesaplayıcı sınıf üyesi işlevleri çağırmak için

1. Artık güncelleştirelim `main` işlevi *CalculatorTutorial.cpp*:

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

   > Kod anlama
   >
   > - C++ programları, her zaman başlangıcından itibaren `main()` işlevi, biz diğer kodumuz buradan, bu nedenle çağırmak için gereken bir `#include` deyimi gereklidir.
   > - Bazı başlangıç değişkenleri `x`, `y`, `oper`, ve `result` ilk sayısı, ikinci sayı, işleci ve nihai sonucu sırasıyla depolamak için bildirilir. Bu her zaman burada yapılır olan tanımlanmamış davranışı önlemek için bazı başlangıç değerleri vermek iyi yöntemdir.
   > - `Calculator c;` Satır bir örneğini 'c' adlı bir nesne bildirir `Calculator` sınıfı. Sınıf hesaplayıcıları nasıl çalıştığı için yalnızca bir plandır; Matematik yapan belirli hesaplayıcı nesnedir.
   > - `while (true)` Deyimi, döngü. Döngü içinde kod tekrar tekrar olduğu sürece koşul içinde yürütmeye devam eder. `()` geçerlidir. Koşul olarak yalnızca listelenen beri `true`, bu nedenle sonsuz döngü çalıştırılır her zaman true olur. Programı kapatmak için kullanıcı el ile konsol penceresini kapatmalısınız. Aksi takdirde, program her zaman için yeni giriş bekler.
   > - `cin` Anahtar sözcüğü, kullanıcı girişi kabul etmek için kullanılır. Bu giriş akışı, konsol penceresinde girilen metin satırı işleyebilir ve her bir değişken, kullanıcı giriş eşleşmeleri gerekli belirtime varsayılarak sırayla yeniden listelenmiş içine yerleştirmek akıllıca olur. Farklı tür giriş kabul etmek için bu satırı değiştirebilirsiniz, örneğin, ikiden fazla, ancak sayı `Calculate()` işlevi da bu durumu çözmek için güncelleştirilmesi gerekir.
   > - `c.Calculate(x, oper, y);` Deyim aramaları `Calculate` işlevi daha önce tanımlanan ve kaynakları girilen giriş değerleri. İşlev ardından depolanan bir sayı döndürür `result`.
   > - Son olarak, `result` hesaplama sonucu kullanıcının gördüğü şekilde konsola yazdırılır.

### <a name="build-and-test-the-code-again"></a>Derleme ve kod yeniden test edin

Artık bu program yeniden her şeyin düzgün çalıştığından emin olmak için test etme vakti.

1. Tuşuna **Ctrl + F5** oluşturmak ve uygulamayı başlatmak için.

1. ENTER `5 + 5`basın **Enter**. Sonucu 10 olduğundan emin olun.

   ![5 + 5 sonucunu](./media/calculator-five-plus-five.png "5 + 5 sonucu")

## <a name="debug-the-app"></a>Uygulamasında hata ayıklama

Kullanıcının herhangi bir şey konsol penceresine yazmak ücretsiz olduğundan, hesap makinesi beklendiği gibi bazı giriş işleme emin olalım. Biz ayrıntılı, adım adım neler incelemek için programı çalıştırmak yerine şimdi, bunun yerine, hata ayıklayın.

### <a name="to-run-the-app-in-the-debugger"></a>Hata ayıklayıcıda uygulamayı çalıştırmak için

1. Bir kesme noktası ayarlamak `result = c.Calculate(x, oper, y);` satır sonra yalnızca kullanıcı girişi için istendi. Kesme noktası ayarlamak için gri dikey çubuk Düzenleyicisi penceresinin sol kenarda satır İleri'yi tıklatın. Kırmızı bir nokta belirir.

   ![Bir kesme noktası ayarlamak](./media/calculator-set-breakpoint.gif "bir kesme noktası ayarlayın")

   Artık programın hata ayıklama, her zaman bu satırındaki yürütülmesine duraklatır. Basit durumlar için program çalışıyor üzerine kaba bir fikriniz zaten sahibiz. Her yürütme duraklatmak istemediğiniz olduğundan, kesme noktası koşullu olalım.

1. Kesme noktasını temsil eden kırmızı nokta sağ tıklatıp seçin **koşullar**. Koşul için düzenleme kutusuna girin `(y == 0) && (oper == '/')`. Seçin **Kapat** işiniz bittiğinde düğmesi. Koşul otomatik olarak kaydedilir.

   ![Koşullu kesme noktası ayarlamak](./media/calculator-conditional-breakpoint.gif "koşullu kesme noktası ayarlayın")

   Artık 0 ile bölme özellikle yapılmaya çalışılırsa biz yürütme kesme noktasında duraklatın.

1. Programda hata ayıklamak için basın **F5**, ya da seçin **yerel Windows hata ayıklayıcı** yeşil ok simgesi olan araç çubuğu düğmesi. Konsol uygulamanıza "5-0" gibi bir şey girerseniz, programın normal şekilde davranır ve çalışmaya devam eder. Ancak, yazarsanız, "10 / 0", kesme noktasında duraklatır. Herhangi bir sayıda işleci ve sayılar arasında boşluk koymak getirebilirsiniz; `cin` giriş uygun şekilde ayrıştırmak akıllıca olur.

   ![Koşullu kesme noktası konumunda duraklama](./media/calculator-debug-conditional.gif "koşullu kesme noktasında Duraklat")

### <a name="useful-windows-in-the-debugger"></a>Yararlı windows hata ayıklayıcısı

Kodunuzdaki hataları ayıklamanıza olduğunda, bazı yeni windows göründüğünü fark edebilirsiniz. Bu windows hata ayıklama deneyiminizi yardımcı olabilir. Bir göz atın **Otolar** penceresi. **Otolar** penceresi gösterir, değişkenlerin geçerli değerleri önce ve geçerli satıra kadar en az üç satırlarında kullanılır.

   ![Otomatik değişkenler penceresi](./media/calculator-autos.png "otomatik değişkenler penceresi")

Tüm bu işlevden değişkenlerin görmek için geçiş **Yereller** penceresi. Aslında bu değişkenlerin değerleri, hata ayıklama sırasında programa sahip etkisini görmek için değiştirebilirsiniz. Bu durumda, bunları tek başına bırakacağız.

   ![Yerel öğeler penceresinde](./media/calculator-locals.png "yerel öğeler penceresi")

Ayrıca kodun kendisi nerede yürütülmesi şu anda duraklatıldı geçerli değerlerini görmek için değişkenleri üzerine gelerek. İlk tıklayarak düzenleyici penceresinde odağı olduğundan emin olun.

   ![Geçerli değişken değerlerini görüntülemek için üzerine gelindiğinde kullanılacak](./media/calculator-hover-tooltip.gif "geçerli değişken değerlerini görüntülemek için üzerine gelme")

### <a name="to-continue-debugging"></a>Hata ayıklamaya devam etmek için

1. Sol taraftaki sarı satırın geçerli yürütme noktasını gösterir. Geçerli satırı çağrıları `Calculate`, bu nedenle basın **F11** için **içine adımla** işlevi. Kendiniz gövdesinde bulabilirsiniz `Calculate` işlevi. Dikkatli olmanız **içine adımla**; çok fazla yaparsanız çok zaman boşa harcanmasına neden olabilir. Temel, standart kitaplık işlevleri dahil olmak üzere olduğunuz satırında kullandığınız herhangi bir kod girer.

1. Yürütme noktası başlangıcında olduğuna göre `Calculate` işlev, basın **F10** program yürütmesinde sonraki satıra taşımak için. **F10** olarak da bilinen **Step Over**. Kullanabileceğiniz **Step Over** ne satırın her bir parçası oluşma ayrıntılara delving olmadan gelen satırı taşımak için. Genel olarak kullanmanız gereken **Step Over** yerine **içine adımla**, başka bir yerden çağrılan kodu daha derinlemesine istemediğiniz sürece (gövdesinin ulaşmak için yaptığınız gibi `Calculate`).

1. Kullanmaya devam **F10** için **Step Over** geri gelene kadar her bir satır `main()` işlev diğer dosyasında ve durdurmayı `cout` satır.

   ![Adım dışında Calculate ve sonucunu denetle](./media/calculator-undefined-zero.gif "adım dışında Calculate ve sonucunu denetle")

1. Beklenen değer program yapıyor gibi görünüyor: ilk sayı alır ve saniye böldüğünü. Üzerinde `cout` satır, üzerine `result` değişkeni veya göz atın `result` içinde **Otolar** penceresi. Değeri doğru görünmüyor, "bilgi" şimdi düzeltmek listelendiğini görürsünüz. `cout` Satır yalnızca çıkarır ne olursa olsun değer depolanan `result`, kaldığında, bir veya daha fazla satır iletecek şekilde kullanarak **F10**, konsol penceresinde görüntüler:

   ![Sıfıra sonucunu](./media/calculator-divide-by-zero-fail.png "sıfıra sonucu")

   Bunun nedeni, sıfıra bölünme tanımsızdır program istenen işlemi için sayısal bir yanıt yok. Bu nedenle bu sonucu kullanmasıdır.

### <a name="to-fix-the-divide-by-zero-error"></a>"Sıfıra" hatayı düzeltmek için

Şimdi sorun bir kullanıcı anlayabilmeniz sıfıra bölme daha düzgün bir şekilde işleyin.

1. Aşağıdaki değişiklikleri yapın *CalculatorTutorial.cpp*. (Düzenlerken adlı bir hata ayıklayıcı özelliği sayesinde çalışan bir program bırakabilirsiniz **Düzenle ve devam et**):

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

1. Şimdi basın **F5** sonra. Tüm kullanıcı girişi isteyebilir duraklatmak sahip oluncaya kadar program yürütme devam eder. Girin `10 / 0` yeniden. Şimdi daha yararlı bir ileti yazdırılır. Kullanıcı için daha fazla giriş sorulur ve program normalde yürütme devam eder.

   ![Değişikliklerden sonra nihai sonucu](./media/calculator-final-verification.gif "değişikliklerden sonra nihai sonucu")

   > ! [Not] Hata ayıklama modunda çalışırken kod düzenleme, kod Eskitme riski yoktur. Hata ayıklayıcı hala eski kodunuzu çalışıyor ve henüz yaptığınız değişikliklerle güncelleştirmemiş kullandığınızda ortaya çıkar. Hata ayıklayıcı bu durumda bildiren bir iletişim kutusu açılır. Bazı durumlarda, basmanız gerekebilir **F5** yürütülen kod yenilenemedi. Yürütme noktası iç işlevi, işlev dışında adım gerektiğini olmakla birlikte bir işlev içinde bir değişiklik yaparsanız, özellikle, ardından buna güncelleştirilen kodun yeniden almak için yedekleyin. Herhangi bir nedenden dolayı çalışmaz ve bir hata iletisi görürsünüz, araç çubuğunda IDE üst kısmındaki menülerinin altında kırmızı bir kare tıklayarak hata ayıklamayı durdurmak ve ardından tekrar girerek hata ayıklamayı Başlat **F5** yeşil seçerek veya " durdurma düğmesi yanındaki oku araç çubuğunda "yürütün.

   > Çalıştırma ve hata ayıklama kısayolları anlama
   >
   > - **F5** (veya **hata ayıklama** > **hata ayıklamayı Başlat**) bir hata ayıklama oturumu zaten etkin değil ve bir kesme noktasına isabet kadar program çalıştırılır başlatır veya program gereksinimlerini kullanıcı girişi. Kullanıcı müdahalesi gerekli değildir ve hiçbir kesme noktası isabet kullanılabilir, program sona erer ve programın çalışması tamamlandığında konsol penceresini kendisi kapatır. Bir "Merhaba Dünya" programı çalıştırmak için benzer bir şey varsa, **Ctrl + F5** veya girdiğiniz önce bir kesme noktası ayarlamak **F5** penceresi açık tutmak için.
   > - **CTRL + F5** (veya **hata ayıklama** > **hata ayıklama olmadan Başlat**) hata ayıklama moduna geçmeden uygulamayı çalıştırır. Bu hata ayıklama değerinden biraz daha hızlıdır ve programın yürütülmesi tamamlandıktan sonra konsol penceresi açık kalır.
   > - **F10** (olarak bilinen **Step Over**) aracılığıyla yineleme sağlar-satır satır, kod ve kod nasıl çalışır ve her adımda yürütme değişken değerleri nelerdir görselleştirin.
   > - **F11** (olarak bilinen **içine adımla**) benzer şekilde çalışır **Step Over**yürütme satırında herhangi bir işlevler halinde adımları dışında. Örneğin, çalıştırılan satır bir işlevi çağırıyorsa tuşuna basarak **F11** işlev gövdesine işaretçiyi hareket, işlevin kod satırına geri dönmeyi önce çalıştırılan izleyebilmeniz öğesinde başladı. Tuşuna basarak **F10** adımları ve yalnızca işlev çağrısı üzerinden, sonraki satıra taşır; işlev çağrısı yine de gerçekleşir, ancak ne yaptığını göstermek için programı duraklatmak değil.

### <a name="close-the-app"></a>Uygulamayı kapatın

1. Hala çalışıyorsa hesaplayıcısı uygulaması için konsol penceresini kapatın.

1. Visual Studio'da **Ctrl**+**S** uygulamanızı kaydetmek için.

## <a name="the-finished-app"></a>Tamamlanmış uygulama

Tebrikler! Siz hesaplayıcı uygulama kodunu ve yerleşik tamamlayıp Visual Studio'da hata ayıklaması.

![Hesap Makinesi konsol uygulaması](./media/calculator-app.gif "hesap makinesi konsol uygulaması")

## <a name="next-steps"></a>Sonraki adımlar

[C++ için Visual Studio hakkında daha fazla bilgi edinin](https://blogs.msdn.microsoft.com/vcblog/2017/04/21/getting-started-with-visual-studio-for-c-and-cpp-development/)
