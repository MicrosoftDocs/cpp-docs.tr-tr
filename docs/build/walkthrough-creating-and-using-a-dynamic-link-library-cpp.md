---
title: 'İzlenecek yol: Oluşturma ve kullanma kendi dinamik bağlantı kitaplığı (C++)'
ms.custom: conceptual
ms.date: 09/24/2018
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
ms.openlocfilehash: 44a2f1da6a02444c79247178c34281e39731f0f3
ms.sourcegitcommit: 6e4dd21759caaed262a7255735cf8d6e8fb9f4d7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58476935"
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>İzlenecek yol: Oluşturma ve kullanma kendi dinamik bağlantı kitaplığı (C++)

Bu adım adım izlenecek yol, C++ ile yazılmış kendi dinamik bağlantı kitaplığı (DLL) oluşturmak için Visual Studio IDE kullanın ve ardından başka bir C++ uygulamasından kullanma işlemi gösterilmektedir. DLL'leri Windows bileşenleri en kullanışlı türlerini biridir. Bunları bir şekilde kod ve kaynakları paylaşmak için uygulamalarınızı boyutunu küçültmek ve hizmet ve uygulamalarınızı genişletin daha kolay hale getirmek için kullanabilirsiniz. Bu kılavuzda, bazı matematik işlevleri uygulayan bir DLL'yi oluşturmak ve ardından DLL işlevlerini kullanan bir konsol uygulaması oluşturacaksınız. Bu doğrultuda, bazı programlama teknikleri ve Windows DLL'leri kullanılan kuralları giriş yapın.

Bu izlenecek yol bu görevleri kapsar:

- Visual Studio'da bir DLL projesi oluşturma.

- Dışarı aktarılan işlevleri ve değişkenler DLL'ye ekleyin.

- Visual Studio'da konsol uygulaması projesi oluşturun.

- Konsol uygulaması, DLL içeri aktarılan değişkenleri ve işlevleri kullanın.

- Tamamlanmış uygulamayı çalıştırın.

Gibi statik olarak bağlı bir kitaplığı, bir DLL _aktarır_ değişkenler, İşlevler ve kaynak adı ve uygulamanız tarafından _aktarır_ bu adları bu değişkenler, İşlevler ve kaynakları kullanın. Statik olarak bağlı bir kitaplığı, Windows uygulamanızı Imports dışarı aktarmaları DLL'de yükleme zamanında ya da bunları bağlantı zamanında bağlanmak yerine çalışma zamanında bağlanır. Windows, bu bağlantılar kurmak için standart C++ derleme modelinin bir parçası olmayan ek bilgi gerektirir. MSVC derleyicisi, bu ek bilgi sağlamak için C++ bazı Microsoft'a özel uzantıları uygular. Biz kullandıkça Biz bu uzantıları açıklar.

Bu kılavuz iki Visual Studio çözümü oluşturur. bir DDL oluşturur ve bir istemci uygulaması oluşturur. Platform çağırma ve kuralları bağlama eşleştiği sürece diğer diller kullanılarak oluşturulan uygulamalardan çağrılabilen bir DLL C çağırma kuralı kullanır. İstemci uygulama kullandığı _örtük bağlama_, burada Windows uygulama DLL yükleme zamanında bağlar. Bu bağlama, DLL tarafından sağlanan işlevleri gibi statik olarak bağlı bir kitaplıkta işlevlerini uygulamanın sağlar.

Bu izlenecek yol, bazı yaygın durumlar ele alınmamıştır. Bu, diğer programlama dilleri tarafından C++ DLL'leri kullanımını göstermez. Bu, yalnızca kaynak DLL oluşturma göstermez. Ayrıca, çalışma zamanında yerine yükleme zamanı dll yüklenecek açık bağlama kullanımını da göstermez. Visual C++ tüm bunları yapmak için kullanabileceğiniz içiniz rahat olsun. DLL'ler hakkında daha fazla bilgi için bağlantılar için bkz: [Visual C++'ta DLL'ler](dlls-in-visual-cpp.md). Örtük bağlama ve açık bağlama hakkında daha fazla bilgi için bkz. [belirleme hangi bağlama yöntemini kullanacağınızı](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use). C dili bağlantı kurallarının kullanan programlama ile kullanmak için C++ DLL'leri oluşturma hakkında daha fazla bilgi için bkz: [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md). .NET dilleri ile kullanılmak üzere DLL'leri oluşturma hakkında daha fazla bilgi için bkz: [Visual Basic uygulamalarından DLL işlevleri çağırma](calling-dll-functions-from-visual-basic-applications.md).

Bu kılavuzda Visual Studio 2017 kullanılır, ancak kodu ve yönergeleri çoğu önceki sürümleri için geçerlidir. Visual Studio 2017 sürüm 15.3 başlayarak yeni projeler oluşturma adımlarını değiştirildi. Bu izlenecek yol için eski ve yeni sürümlerini proje nasıl oluşturulacağını açıklar. Visual Studio sürümünüze uygun adımları arayın.

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Windows 7 veya sonraki sürümleri çalıştıran bir bilgisayar. Windows 10 için en iyi geliştirme deneyimi öneririz.

- Visual Studio 2017 bir kopyası. Visual Studio yükleyip hakkında daha fazla bilgi için bkz. [Visual Studio 2017'yi yükleme](/visualstudio/install/install-visual-studio). Yükleyici çalıştırdığınızda emin **C++ ile masaüstü geliştirme** iş yükü denetlenir. Visual Studio yüklediğinizde bu iş yükü yüklenmediyse, endişelenmeyin. Yükleyiciyi yeniden çalıştırın ve şimdi yükleyin.

   ![C++ ile masaüstü geliştirme](media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

- Visual Studio IDE kullanmanın temellerini olma. Windows Masaüstü uygulamaları önce kullandıysanız, büyük olasılıkla tutabilirsiniz. Bir giriş için bkz [Visual Studio IDE özellik Turu](/visualstudio/ide/visual-studio-ide).

- Bir anlayış yeterli örneği takip etmek için C++ dilinin temellerini. Merak etmeyin, biz vermekten hiçbir şey yapmaz.

## <a name="create-the-dll-project"></a>DLL projesi oluşturma

Görevlerin bu kümesindeki DLL dosyanız için bir proje oluşturun, kod ekleyin ve derleyin. Başlamak için Visual Studio IDE başlatın ve gerekirse oturum açın. Visual Studio 2017 sürüm 15.3 yönergelerini ilk gelir. Önceki sürümler için yönergeler daha sonra gelir, bu nedenle, gerekirse İleri atlayabilirsiniz.

### <a name="to-create-a-dll-project-in-visual-studio-2017-version-153-or-later"></a>Bir DLL proje Visual Studio 2017 sürüm 15.3 veya üzeri oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje** açmak için **yeni proje** iletişim kutusu.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü** ve **Visual C++** gerekirse ve ardından **Windows Masaüstü** . Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**. Girin `MathLibrary` içinde **adı** kutusunu proje için bir ad belirtin.

   ![MathLibrary projesini adlandırın](media/mathlibrary-new-project-name-153.png "MathLibrary projesini adlandırın")

1. Seçin **Tamam** kapatmak için düğme **yeni proje** iletişim ve başlangıç **Windows Masaüstü projesi** Sihirbazı.

1. İçinde **Windows Masaüstü projesi** altında Sihirbazı **uygulama türü**seçin **dinamik bağlantı kitaplığı (.dll)**.

   ![Windows Masaüstü Proje Sihirbazı'nda DLL'yi oluşturmak](media/mathlibrary-desktop-project-wizard-dll.png "Windows Masaüstü Proje Sihirbazı'nda DLL oluşturma")

1. Seçin **Tamam** projeyi oluşturmak için.

> [!NOTE]
> Visual Studio 2017 sürüm 15.3 bir sorunu düzeltmek için ek adımlar gereklidir. Bu değişiklik gerekip gerekmediğini görmek için bu yönergeleri izleyin.
>
>1. İçinde **Çözüm Gezgini**, zaten değilse seçildiğinden **MathLibrary** altındaki proje **çözüm 'MathLibrary'**.
>
>1. Menü çubuğunda, **proje** > **özellikleri**.
>
>1. Sol bölmesinde **özellik sayfaları** iletişim kutusunda **önişlemci** altında **yapılandırma özellikleri** > **C/C++**. İçeriğini denetlemek **önişlemci tanımları** özelliği.<br/><br/>![Önişlemci tanımları özelliğini denetleyin](media/mathlibrary-153bug-preprocessor-definitions-check.png "önişlemci tanımları özelliğini denetleyin")<br/><br/>Görürseniz **MATHLIBRARY&#95;dışarı AKTARMALARI** içinde **önişlemci tanımları** listesinde, daha sonra herhangi bir ayarı değiştirmek gerekmez. Görürseniz **MathLibrary&#95;dışarı AKTARMALARI** bunun yerine, aşağıdaki adımları uygulamaya sonra devam edin.
>
>1. Üst kısmındaki **özellik sayfaları** iletişim kutusunda değişiklik **yapılandırma** açılan **yapılandırmalarında**.
>
>1. Düzenleme kutusu yanındaki aşağı açılır denetimin özellik bölmesinde seçin **önişlemci tanımları**ve ardından **Düzenle**.<br/><br/>![Önişlemci tanımları özelliğini Düzenle](media/mathlibrary-153bug-preprocessor-definitions-property.png "önişlemci tanımları özelliğini Düzenle")
>
>1. Üst bölmesindeki **önişlemci tanımları** iletişim kutusunda, yeni bir simge eklemek `MATHLIBRARY_EXPORTS`.<br/><br/>![MATHLIBRARY_EXPORTS simgesini](media/mathlibrary-153bug-preprocessor-definitions-dialog.png "MATHLIBRARY_EXPORTS simgesi Ekle")
>
>1. Seçin **Tamam** kapatmak için **önişlemci tanımları** iletişim kutusunda ve ardından **Tamam** proje özelliklerine yaptığınız değişiklikleri kaydedin.

### <a name="to-create-a-dll-project-in-older-versions-of-visual-studio"></a>Visual Studio'nun eski sürümlerini bir DLL projesi oluşturma

1. Menü çubuğunda, **dosya** > **yeni** > **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü** > **şablonları**seçip **Visual C++**, ve Orta bölmede, ardından **Win32 konsol uygulaması**. Girin `MathLibrary` içinde **adı** düzenleme kutusuna proje için bir ad belirtmek için.

   ![MathLibrary projesini adlandırın](media/mathlibrary-project-name.png "MathLibrary projesini adlandırın")

1. Seçin **Tamam** kapatmak için düğme **yeni proje** iletişim ve başlangıç **Win32 Uygulama Sihirbazı**.

   ![Win32 Uygulama Sihirbazı genel bakış](media/mathlibrary-project-wizard-1.png "Win32 Uygulama Sihirbazı genel bakış")

1. Seçin **sonraki** düğmesi. Üzerinde **uygulama ayarları** sayfasındaki **uygulama türü**seçin **DLL**.

   ![Win32 Uygulama Sihirbazı'nda DLL'yi oluşturmak](media/mathlibrary-project-wizard-2.png "Win32 Uygulama Sihirbazı'nda DLL oluşturma")

1. Seçin **son** projeyi oluşturmak için.

Çözüm sihirbaz tamamlandığında, oluşturulan proje ve kaynak dosyaları görebilirsiniz **Çözüm Gezgini** Visual Studio'daki.

![Çözümü Visual Studio'da oluşturulan](media/mathlibrary-solution-explorer-153.png "çözümü Visual Studio'da oluşturulan")

Sağdaki şimdi bu DLL çok fazla yapmaz. DLL işlevleri bildirmek için bir üstbilgi dosyası ardından, oluşturduğunuz dışarı aktarır ve ardından daha kullanışlı hale getirmek için DLL için işlev tanımları ekleyin.

### <a name="to-add-a-header-file-to-the-dll"></a>DLL için bir üstbilgi dosyasını eklemek için

1. Menü çubuğunda, işlevleriniz için bir üstbilgi dosyası oluşturmak için seçin **proje** > **Yeni Öğe Ekle**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda, sol bölmede, select **Visual C++**. Orta bölmede seçin **üst bilgi dosyası (.h)**. Belirtin `MathLibrary.h` olarak üst bilgi dosyasının adı.

   ![Yeni Öğe Ekle iletişim kutusunda üst bilgi Ekle](media/mathlibrary-add-new-item-header-file.png "Yeni Öğe Ekle iletişim kutusunda üstbilgi Dosya Ekle")

1. Seçin **Ekle** yeni bir düzenleyici penceresinde görüntülenen bir boş üstbilgi dosyası oluşturmak için düğme.

   ![Boş MathLibrary.h dosyayı Düzenleyicide](media/edit-empty-mathlibrary-header.png "boş MathLibrary.h dosyayı düzenleyicide")

1. Üst bilgi dosyasının içeriği şu kodla değiştirin:

   ```cpp
   // MathLibrary.h - Contains declarations of math functions
   #pragma once

   #ifdef MATHLIBRARY_EXPORTS
   #define MATHLIBRARY_API __declspec(dllexport)
   #else
   #define MATHLIBRARY_API __declspec(dllimport)
   #endif

   // The Fibonacci recurrence relation describes a sequence F
   // where F(n) is { n = 0, a
   //               { n = 1, b
   //               { n > 1, F(n-2) + F(n-1)
   // for some initial integral values a and b.
   // If the sequence is initialized F(0) = 1, F(1) = 1,
   // then this relation produces the well-known Fibonacci
   // sequence: 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

   // Initialize a Fibonacci relation sequence
   // such that F(0) = a, F(1) = b.
   // This function must be called before any other function.
   extern "C" MATHLIBRARY_API void fibonacci_init(
       const unsigned long long a, const unsigned long long b);

   // Produce the next value in the sequence.
   // Returns true on success and updates current value and index;
   // false on overflow, leaves current value and index unchanged.
   extern "C" MATHLIBRARY_API bool fibonacci_next();

   // Get the current value in the sequence.
   extern "C" MATHLIBRARY_API unsigned long long fibonacci_current();

   // Get the position of the current value in the sequence.
   extern "C" MATHLIBRARY_API unsigned fibonacci_index();
   ```

Bu başlık dosyasının genelleştirilmiş bir Fibonacci dizisi olan iki verilen ilk değer üretmek için bazı işlevleri bildirir. Bir çağrı `fibonacci_init(1, 1)` tanıdık Fibonacci sayı dizisi oluşturur.

Önişlemci deyimini dosyanın üst dikkat edin. Varsayılan olarak, bir DLL için yeni bir proje şablonu ekler  **<em>PROJECTNAME</em>&#95;dışarı AKTARMALARI** DLL projesi için tanımlanan Önişlemci makroları. Bu örnekte, Visual Studio tanımlar **MATHLIBRARY&#95;dışarı AKTARMALARI** MathLibrary DLL projeniz ne zaman oluşturulur. (Visual Studio 2017 sürüm 15.3 sihirbazda bu sembol tanımı büyük harf için zorlamaz. Projeniz "MathLibrary" ad sonra tanımlanmış simgenin MathLibrary olup&#95;dışarı AKTARMALARI MATHLIBRARY yerine&#95;dışa AKTARIR. That's vardır neden ek adımlar bu simge eklemek için yukarıdaki.)

Zaman **MATHLIBRARY&#95;dışarı AKTARMALARI** makrosu tanımlanan **MATHLIBRARY&#95;API** makrosu kümeleri `__declspec(dllexport)` işlev bildirimleri değiştiricisi. Bu değiştirici, derleyici ve böylece diğer uygulamalar tarafından kullanılan bir işlev veya değişkeni DLL'den dışarı aktarmak için bağlayıcı söyler. Zaman **MATHLIBRARY&#95;dışarı AKTARMALARI** üstbilgi dosyasını bir istemci uygulaması tarafından eklendiğinde Örneğin, tanımsızdır **MATHLIBRARY&#95;API** geçerlidir `__declspec(dllimport)` değiştiriciyi bildirimleri. Bu değiştirici, işlev veya değişkeni bir uygulamada alma iyileştirir. Daha fazla bilgi için [dllexport, dllimport](../cpp/dllexport-dllimport.md).

### <a name="to-add-an-implementation-to-the-dll"></a>DLL için bir uygulama eklemek için

1. Düzenleyici penceresinde için sekmesinde **MathLibrary.cpp** zaten açıksa. Aksi halde, **Çözüm Gezgini**açın **MathLibrary.cpp** içinde **kaynak dosyaları** klasörü **MathLibrary** proje.

1. Düzenleyici'de MathLibrary.cpp dosyasının içeriğini aşağıdaki kodla değiştirin:

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "stdafx.h"
   #include <utility>
   #include <limits.h>
   #include "MathLibrary.h"

   // DLL internal state variables:
   static unsigned long long previous_;  // Previous value, if any
   static unsigned long long current_;   // Current sequence value
   static unsigned index_;               // Current seq. position

   // Initialize a Fibonacci relation sequence
   // such that F(0) = a, F(1) = b.
   // This function must be called before any other function.
   void fibonacci_init(
       const unsigned long long a,
       const unsigned long long b)
   {
       index_ = 0;
       current_ = a;
       previous_ = b; // see special case when initialized
   }

   // Produce the next value in the sequence.
   // Returns true on success, false on overflow.
   bool fibonacci_next()
   {
       // check to see if we'd overflow result or position
       if ((ULLONG_MAX - previous_ < current_) ||
           (UINT_MAX == index_))
       {
           return false;
       }

       // Special case when index == 0, just return b value
       if (index_ > 0)
       {
           // otherwise, calculate next sequence value
           previous_ += current_;
       }
       std::swap(current_, previous_);
       ++index_;
       return true;
   }

   // Get the current value in the sequence.
   unsigned long long fibonacci_current()
   {
       return current_;
   }

   // Get the current index position in the sequence.
   unsigned fibonacci_index()
   {
       return index_;
   }
   ```

Her şeyin kadar çalıştığını doğrulamak için dinamik bağlantı kitaplığını derleyin. Derlemek için seçin **derleme** > **Çözümü Derle** menü çubuğundaki. Çıktı aşağıdakine benzer görünmelidir:

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>stdafx.cpp
1>MathLibrary.cpp
1>dllmain.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.pdb (Partial PDB)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Tebrikler, Visual C++ kullanarak bir DLL'nin oluşturdunuz! Ardından, DLL tarafından dışarı aktarılan işlevlerin kullanan bir istemci uygulaması oluşturacaksınız.

## <a name="create-a-client-app-that-uses-the-dll"></a>DLL kullanan bir istemci uygulaması oluşturma

DLL oluştururken nasıl DLL'niz kullanılabileceğini hakkında düşünmeniz gerekir. Bir DLL tarafından dışarı aktarılan işlevleri çağıran kodu derlemek için istemci kaynak kodunda bildirimleri eklenmesi gerekir. DLL işlevleri çağrıları olduğunda çözülmüş, bağlantı zamanında bağlayıcı olmalıdır bir *kitaplığına*, gerçek kod yerine işlevlerin bulunacağı hakkında bilgi için Windows içeren özel bir kitaplık dosyası. Ve DLL çalışma zamanında, işletim sistemi bulabilirsiniz bir konumda bir istemci için kullanılabilir olmalıdır.

Bir DLL kullanmak için olup olmadığını, sahip olduğunuz veya bir üçüncü taraf DLL istemci uygulaması projenize DLL bildirmek üstbilgileri dışarı aktarır, bağlayıcı ve DLL için içeri aktarma kitaplıkları bulmanız gerekir. Bir yolu, tüm bu dosyalar istemci projenize kopyalayın oluşturmaktır. İstemci geliştirme olmakla birlikte değişme olasılığı olan üçüncü parti DLL'ler için bu yöntemi kullanabilmesi için en iyi yolu olabilir. Ancak, bir DLL de oluştururken yinelemesinden kaçınmak daha iyi olacaktır. Geliştirilme aşamasındadır DLL dosyalarının bir kopyasını yaparsanız, yanlışlıkla bir üstbilgi dosyasında bir kopya, ancak diğer değiştirme, güncel olmayan bir kitaplık kullanabilir veya. Bu sorunu önlemek için DLL projesinden DLL üstbilgi dosyalarını eklemek, istemci projenizdeki yoluna ayarlamanızı öneririz. Ayrıca, DLL projesinden DLL içeri aktarma kitaplıkları dahil etmek için istemci projenizdeki kitaplık yolunu ayarlayın. Ve son olarak, DLL projesinden derlenmiş DLL, yapı çıktı dizinine kopyalayın. Bu adım, yapı aynı DLL kodu kullanmak için istemci uygulamanızı sağlar.

### <a name="to-create-a-client-app-in-visual-studio-2017-version-153-or-later"></a>Bir istemci uygulaması Visual Studio 2017 sürüm 15.3 veya üzeri oluşturmak için

1. Menü çubuğunda, oluşturduğunuz DLL'yi kullanan C++ uygulaması oluşturmak için Seç **dosya** > **yeni** > **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **Windows Masaüstü** altında **yüklü** > **Visual C++**. Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**. Proje için adı belirtin `MathClient`, **adı** düzenleme kutusu.

   ![İstemci projesini adlandırın](media/mathclient-new-project-name-153.png "istemci projesini adlandırın")

1. Seçin **Tamam** başlatmak için **Windows Masaüstü projesi** Sihirbazı. Sihirbazda seçtiğiniz **Tamam** istemci uygulaması projesi oluşturmak için.

### <a name="to-create-a-client-app-in-older-versions-of-visual-studio-2017"></a>Visual Studio 2017'in eski sürümlerinde bir istemci uygulaması oluşturmak için

1. Menü çubuğunda, oluşturduğunuz DLL'yi kullanan C++ uygulaması oluşturmak için Seç **dosya** > **yeni** > **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **Win32** altında **yüklü** > **şablonları**  >  **Visual C++**. Orta bölmede seçin **Win32 konsol uygulaması**. Proje için adı belirtin `MathClient`, **adı** düzenleme kutusu.

   ![İstemci projesini adlandırın](media/mathclient-project-name.png "istemci projesini adlandırın")

1. Seçin **Tamam** kapatmak için düğme **yeni proje** iletişim ve başlangıç **Win32 Uygulama Sihirbazı**. Üzerinde **genel bakış** sayfasının **Win32 Uygulama Sihirbazı** iletişim kutusunda **sonraki** düğmesi.

1. Üzerinde **uygulama ayarları** sayfasındaki **uygulama türü**seçin **konsol uygulaması** zaten seçili değilse.

1. Seçin **son** projeyi oluşturmak için.

Sihirbaz sona erdiğinde, sizin için en az bir konsol uygulama projesi oluşturulur. Ana kaynak dosyasının adı daha önce girdiğiniz bir proje adı ile aynıdır. Bu örnekte, adlı **MathClient.cpp**. Oluşturabilirsiniz, ancak henüz DLL'niz kullanmaz.

Ardından, kaynak kodunuzu MathLibrary işlevleri çağırmak için projenizi MathLibrary.h dosyası içermelidir. Bu başlık dosyasının istemci uygulaması projenize kopyalamasını ardından Proje var olan bir öğe eklemek. Bu yöntem, üçüncü taraf kitaplıklar için iyi bir seçim olabilir. Kod, DLL için aynı anda istemci çalışıyorsanız, ancak, bir üst bilgi dosyası, diğer gösterilmeyen değişikliklere neden olabilir. Bu sorunu önlemek için değiştirebileceğiniz **ek içerik dizinleri** özgün üstbilgisi yolu eklemek için projenizdeki yolu.

### <a name="to-add-the-dll-header-to-your-include-path"></a>DLL üstbilgiye eklenecek, yolunu Ekle

1. Açık **özellik sayfaları** iletişim kutusu için **MathClient** proje.

1. İçinde **yapılandırma** açılan kutusunda **yapılandırmalarında** zaten seçili değilse.

1. Sol bölmede seçin **genel** altında **yapılandırma özellikleri** > **C/C++**.

1. Özellik bölmesinde aşağı açılır denetimin yanındaki seçin **ek içerik dizinleri** düzenleme kutusuna ve ardından **Düzenle**.

   ![Ek İçerik dizinleri özelliğini Düzenle](media/mathclient-additional-include-directories-property.png "ek içerik dizinleri özelliğini Düzenle")

1. Üst bölmede çift **ek içerik dizinleri** bir düzenleme denetimi etkinleştirmek için iletişim kutusu.

1. Düzenleme denetiminde konumunun yolunu belirtin **MathLibrary.h** üst bilgi dosyası. Bu durumda, .cpp dosyalarınızdan DLL projesinde .h dosyasını içeren klasöre istemci projesindeki içeren klasöründen göreli bir yol kullanabilirsiniz. DLL çözümle aynı klasörde ayrı bir çözümde istemci projeniz ise göreli yol şöyle görünmelidir:

   `..\..\MathLibrary\MathLibrary`

   Ardından, DLL ve istemci projeleri aynı çözüm içinde ya da devre dışı çözümlerini farklı klasörlerde bulunan, göreli yolunu uygun şekilde ayarlamanız gerekir.

   ![Başlık konumu ek içerik dizinleri özellik ekleyin](media/mathclient-additional-include-directories.png "üstbilgi konumunu ek içerik dizinleri özelliğini ekleyin")

1. Üst bilgi dosyasında yolu girdikten sonra **ek içerik dizinleri** iletişim kutusunda **Tamam** dönmek için düğme **özellik sayfaları** iletişim kutusu, ve ardından **Tamam** düğmesini yaptığınız değişiklikleri kaydedin.

Artık içerebilir **MathLibrary.h** dosya ve istemci uygulamanızda bildirir işlevlerini kullanın. Öğesinin içeriğini değiştirin **MathClient.cpp** bu kodu kullanarak:

```cpp
// MathClient.cpp : Client app for MathLibrary DLL.
#include "pch.h"
#include <iostream>
#include "MathLibrary.h"

int main()
{
    // Initialize a Fibonacci relation sequence.
    fibonacci_init(1, 1);
    // Write out the sequence values until overflow.
    do {
        std::cout << fibonacci_index() << ": "
            << fibonacci_current() << std::endl;
    } while (fibonacci_next());
    // Report count of values written before overflow.
    std::cout << fibonacci_index() + 1 <<
        " Fibonacci sequence values fit in an " <<
        "unsigned 64-bit integer." << std::endl;
}
```

Bu kodu derlenmiş ancak henüz uygulama oluşturmak için gerekli içeri aktarma kitaplığı bağlayıcı bulamadığından, bağlı değil. Bağlayıcı başarıyla bağlamak için MathLibrary.lib dosyasını bulmanız gerekir. Ayarlayarak MathLibrary.lib dosyanın yapı ekleme **ek bağımlılıklar** özelliği. Bir kez daha, kitaplık dosyasını istemci uygulaması projenize kopyalamasını, ancak Kitaplığı hem istemci uygulaması geliştirme altında ise, bir kopya diğer gösterilmeyen değişikliklere neden olabilir. Bu sorunu önlemek için değiştirebileceğiniz **ek kitaplık dizinleri** bağlantı oluşturduğunuzda, özgün kitaplık yolu eklemek için projenizdeki yolu.

### <a name="to-add-the-dll-import-library-to-your-project"></a>DLL içeri aktarma kitaplığını projenize eklemek için

1. Açık **özellik sayfaları** iletişim kutusu için **MathClient** proje.

1. İçinde **yapılandırma** açılan kutusunda **yapılandırmalarında** zaten seçili değilse.

1. Sol bölmede seçin **giriş** altında **yapılandırma özellikleri** > **bağlayıcı**. Özellik bölmesinde aşağı açılır denetimin yanındaki seçin **ek bağımlılıklar** düzenleme kutusuna ve ardından **Düzenle**.

   ![Ek Bağımlılıklar özelliğini Düzenle](media/mathclient-additional-dependencies-property.png "ek bağımlılıklar özelliğini Düzenle")

1. İçinde **ek bağımlılıklar** iletişim kutusunda, eklemek `MathLibrary.lib` listesine üst düzen denetimi.

   ![Kitaplık bağımlılığı eklemek](media/mathclient-additional-dependencies.png "kitaplığı bağımlılık Ekle")

1. Seçin **Tamam** dönmek için **özellik sayfaları** iletişim kutusu.

1. Sol bölmede seçin **genel** altında **yapılandırma özellikleri** > **bağlayıcı**. Özellik bölmesinde aşağı açılır denetimin yanındaki seçin **ek kitaplık dizinleri** düzenleme kutusuna ve ardından **Düzenle**.

   ![Ek Kitaplık dizinleri özelliğini Düzenle](media/mathclient-additional-library-directories-property.png "ek kitaplık dizinleri özelliğini Düzenle")

1. Üst bölmede çift **ek kitaplık dizinleri** bir düzenleme denetimi etkinleştirmek için iletişim kutusu. Düzenleme denetiminde konumunun yolunu belirtin **MathLibrary.lib** dosya. Yapılar için hem hata ayıklama ve yayın çalışır bir makro kullanmak üzere bu değeri girin:

   `..\..\MathLibrary\$(IntDir)`

   ![Kitaplık dizinine ekleme](media/mathclient-additional-library-directories.png "kitaplık dizinini Ekle")

1. Kitaplık dosyasına yolu girdikten sonra **ek kitaplık dizinleri** iletişim kutusunda **Tamam** dönmek için düğme **özellik sayfaları** iletişim kutusu.

İstemci uygulamanızı, artık derlemek ve başarılı bir şekilde bağlamak, ancak bu yine de çalıştırmak için ihtiyaç duyduğu her şeyi gerekli değildir. İşletim sistemi, uygulama yüklendiğinde MathLibrary DLL için arar. DLL belirli sistem dizinleri, ortam yolu veya yerel uygulama dizini bulunamıyor, yükleme başarısız olur. Bu sorunu önlemek için bir DLL oluşturma işleminin bir parçası, istemci yürütülebilir dosyayı içeren dizine kopyalamak için yoludur. DLL kopyalamak için ekleyebileceğiniz bir **derleme sonrası olay** projeniz için bir komut eklemek için DLL, derleme çıktı dizinine kopyalar. Burada belirtilen komut yalnızca eksik olan veya değişti ve yapılandırmanızı doğru hata ayıklama veya perakende konumlarını ve kopyalamak için makroları kullanır DLL kopyalar.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>Oluşturma sonrası olayında DLL kopyalamak için

1. Açık **özellik sayfaları** iletişim kutusu için **MathClient** zaten açık değilse proje.

1. Yapılandırma açılan kutusunda **yapılandırmalarında** zaten seçili değilse.

1. Sol bölmede seçin **derleme sonrası olay** altında **yapılandırma özellikleri** > **Build Events**.

1. Özellik bölmesinde, bir düzenleme denetimini seçin **komut satırı** alan ve ardından şu komutu girin:

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![Derleme sonrası komut ekleme](media/mathclient-post-build-command-line.png "derleme sonrası komut ekleme")

1. Seçin **Tamam** proje özelliklerine yaptığınız değişiklikleri kaydetmek için düğme.

İstemci uygulamanızı derlemek ve çalıştırmak için ihtiyaç duyduğu her şeyi sunuyor. Seçerek uygulama derleme **derleme** > **Çözümü Derle** menü çubuğundaki. **Çıkış** Visual Studio'daki aşağıdakine benzer olmalıdır:

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>pch.cpp
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.pdb (Partial PDB)
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Tebrikler, İşlevler DLL'nizi çağıran bir uygulama oluşturdunuz. Şimdi ne işe yaradığını görmek için uygulamanızı çalıştırın. Menü çubuğunda, **hata ayıklama** > **hata ayıklama olmadan Başlat**. Visual Studio çalıştırılacak programı için bir komut penceresi açılır. Son kısmını çıktı gibi görünmelidir:

![İstemci uygulama, hata ayıklama olmadan Başlat](media/mathclient-run-without-debugging.png "istemci uygulama, hata ayıklama olmadan Başlat")

Komut penceresini kapatmak için herhangi bir tuşa basın.

Bir DLL ve istemci uygulaması oluşturduktan sonra denemeler yapabilirsiniz. İstemci uygulama kodunda kesme noktalarını ayarlamayı deneyin ve hata ayıklayıcıda uygulamayı çalıştırın. Kitaplık çağrısına olduğunda ne olacağına bakalım. Diğer işlevler kitaplığa eklemek veya DLL kullanan başka bir istemci uygulaması yazma.

Uygulamanızı dağıtırken de kullandığı DLL'leri dağıtmanız gerekir. Oluşturduğunuz veya size içeren dll Üçüncü taraflardan uygulamanıza kullanılabilmesi için en basit yolu bunları, uygulamanız ile aynı dizinde olarak da bilinen eklemektir *uygulaması yerel dağıtım*. Dağıtım hakkında daha fazla bilgi için bkz: [Visual C++ üzerinde dağıtım](../ide/deployment-in-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Basic Uygulamalarından DLL İşlevleri Çağırma](calling-dll-functions-from-visual-basic-applications.md)
