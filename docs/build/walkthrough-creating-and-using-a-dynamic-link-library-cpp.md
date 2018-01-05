---
title: "İzlenecek yol: Oluşturma ve kendi dinamik bağlantı kitaplığı (C++) kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
caps.latest.revision: "36"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bdcc02cf7c86b85684df0e8d8b7a1f0049ff7e25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>İzlenecek yol: Oluşturun ve kendi dinamik bağlantı kitaplığı (C++) kullanın

Bu adım adım kılavuz, Visual Studio IDE C++ ile yazılmış kendi dinamik bağlantı kitaplığı (DLL) oluşturun ve başka bir C++ uygulamasının kullanmak gösterilmiştir. DLL'leri Windows bileşenleri en yararlı türlerini biridir. Bunları kod ve kaynakları paylaşmak için bir yöntem, uygulamalarınızı boyutunu küçültmek ve hizmet ve uygulamalarınızı genişletmek kolaylaştırmak için kullanabilirsiniz. Bu kılavuzda, bazı matematik işlevleri uygulayan bir dll dosyası oluşturun ve ardından DLL işlevlerini kullanan bir konsol uygulaması oluşturun. Yol boyunca programlama teknikleri ve Windows DLL'lerde kullanılan kuralları bazıları giriş alın.

Bu kılavuzda, bu görevleri içerir:

- Visual Studio'da bir DLL projesi oluşturun.

- Dışarı aktarılan işlevleri ve değişkenler DLL'e ekleyin.

- Visual Studio'da bir konsol uygulama projesi oluşturun.

- İşlevleri ve değişkenler konsol uygulaması DLL'de içe kullanın.

- Tamamlanmış uygulamayı çalıştırın.

Gibi bir DLL statik olarak bağlantılı bir kitaplık _aktarır_ değişkenler, İşlevler ve kaynak adı ve uygulamanız tarafından _alır_ Bu değişkenler, İşlevler ve kaynakları kullanmak için bu adları. Statik olarak bağlantılı bir kitaplık Windows yükleme zamanında veya bağlantı aynı anda bağlanan yerine çalışma zamanında dışarı DLL'de içeri aktarmalar, uygulamanızda bağlanır. Windows bu bağlantıları kurmak için standart C++ derleme modelin parçası olmayan ek bilgileri gerektirir. Visual C++ derleyicisi bazı ek bu bilgiler sağlamak için C++ için Microsoft özgü uzantıları uygular. Biz ilerledikçe Biz bu uzantıları açıklanmaktadır.

Bu kılavuzda iki Visual Studio çözümü oluşturur; DLL oluşturan, diğeri, istemci uygulaması oluşturur. DLL C çağırma kuralı kullandığı için platform çağırma ve kuralları bağlama eşleştiği sürece diğer diller kullanılarak oluşturulmuş uygulamalardan çağrılabilir. İstemci uygulama kullandığı _örtük bağlantılandırma_, burada Windows uygulama yükleme zamanında DLL bağlar. Bu DLL tarafından sağlanan işlevleri gibi statik olarak bağlantılı bir kitaplıkta işlevlerini uygulama sağlar.

Bu kılavuzda, bazı ortak durumlar kapsamaz. Diğer programlama dilleri tarafından C++ DLL'leri kullanımını göstermez. Yalnızca kaynak DLL oluşturma göstermez. Ayrıca, çalışma zamanında yerine yükleme zamanında DLL'leri yüklemek için açıkça bağlama kullanımını da göstermez. REST garanti, tüm bu işlemler yapmak için Visual C++ kullanabilirsiniz. DLL'leri hakkında daha fazla bilgi için bağlantılar için bkz: [DLL'leri Visual C++'ta](../build/dlls-in-visual-cpp.md). Örtük bağlantılandırma ve açıkça bağlama hakkında daha fazla bilgi için bkz: [belirleme hangi bağlama yöntemini kullanacağınızı](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use). C dili bağlantı kuralları kullanan diller programlama ile kullanmak için C++ DLL'leri oluşturma hakkında daha fazla bilgi için bkz: [C dili yürütülebilir öğelerinde kullanmak için C++ işlevlerini dışarı aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md). .NET dilleri ile kullanılmak üzere DLL'leri oluşturma hakkında daha fazla bilgi için bkz: [Visual Basic uygulamalarından DLL işlevleri çağırma](../build/calling-dll-functions-from-visual-basic-applications.md).

Bu kılavuzda Visual Studio 2017 kullanılır, ancak kod ve yönergeleri çoğunu önceki sürümleri için geçerlidir. Visual Studio 2017 sürüm 15.3 başlayarak yeni projeler oluşturma adımlarını değiştirildi. Bu kılavuzda daha yeni ve eski sürümleri projelerde oluşturmayı açıklar. Visual Studio sürümünüzle eşleşen adımları arayın.

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Windows 7 veya sonraki sürümlerini çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10 öneririz.

- Visual Studio 2017 kopyası. Visual Studio yükleyip konusunda daha fazla bilgi için bkz: [yükleme Visual Studio 2017](/visualstudio/install/install-visual-studio). Yükleyiciyi çalıştırdığınızda emin olun **C++ ile masaüstü geliştirme** iş yükü denetlenir. Visual Studio yüklendiğinde bu iş yükü yüklenmediyse, endişelenmeyin. Yükleyiciyi yeniden çalıştırın ve şimdi yükleyin.

   ![C++ ile masaüstü geliştirme](media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

- Visual Studio IDE kullanarak, temel bir anlayış. Windows Masaüstü uygulamaları önce kullandıysanız, büyük olasılıkla tutabilirsiniz. Giriş için bkz [Visual Studio IDE özelliği Turu](/visualstudio/ide/visual-studio-ide).

- Bir anlayış yeterli izlemek için C++ dili ile ilgili temel bilgileri. Endişelenmeyin, biz çok karmaşık hiçbir şey yapmayın.

## <a name="create-the-dll-project"></a>DLL projesi oluşturma

Görevlerin bu kümesindeki DLL için bir proje oluşturun, kodu ekleyin ve bu derleme. Başlamak için Visual Studio IDE başlatın ve gerekirse oturum açın. Visual Studio 2017 sürüm 15.3 yönergelerini ilk gelir. Önceki sürümler için yönergeler, daha sonra gelir, bu nedenle, gerekirse İleri atlayabilirsiniz.

### <a name="to-create-a-dll-project-in-visual-studio-2017-version-153-or-later"></a>15.3 veya sonraki Visual Studio 2017 sürüm DLL projesi oluşturmak için

1. Menü çubuğunda seçin **dosya**, **yeni**, **proje** açmak için **yeni proje** iletişim kutusu.

1. Sol bölmesinde **yeni proje** iletişim kutusunda, genişletin **yüklü** ve **Visual C++** gerekli ve ardından seçerseniz **Windows Masaüstü**. Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**. Girin `MathLibrary` içinde **adı** kutusunda proje için bir ad belirtin.

   ![MathLibrary proje adı](media/mathlibrary-new-project-name-153.png "MathLibrary proje adı")

1. Seçin **Tamam** kapatmak için düğmesini **yeni proje** iletişim ve başlangıç **Windows Masaüstü projesi** Sihirbazı.

1. İçinde **Windows Masaüstü projesi** altında **uygulama türü**seçin **dinamik bağlantı kitaplığı (.dll)**.

   ![Windows Masaüstü projesi Sihirbazı'nda DLL oluşturma](media/mathlibrary-desktop-project-wizard-dll.png "Windows Masaüstü projesi Sihirbazı'nda DLL oluşturma")

1. Seçin **Tamam** projesi oluşturmak için düğmesi.

> [!NOTE]
> Visual Studio 2017 sürüm 15.3 bir sorunu düzeltmek için ek adımlar gereklidir. Bu değişikliği yapmak gerekip gerekmediğini görmek için bu yönergeleri izleyin.
>
>1. İçinde **Çözüm Gezgini**, zaten değilse seçildiğinde, select **MathLibrary** altında proje **çözüm 'MathLibrary'**.
>
>1. Menü çubuğunda seçin **proje**, **özellikleri**.
>
>1. Sol bölmesinde **özellik sayfaları** iletişim kutusunda **önişlemci** altında **yapılandırma özellikleri**, **C/C++**. İçeriğini denetlemek **önişlemci tanımları** özelliği.<br/><br/>![Önişlemci tanımları özelliğini denetleyin](media/mathlibrary-153bug-preprocessor-definitions-check.png "önişlemci tanımları özelliğini denetleyin")<br/><br/>Görürseniz **MATHLIBRARY &#95; Dışarı aktarma** içinde **önişlemci tanımları** değişikliği gerekmez sonra listeleyin. Görürseniz **MathLibrary &#95; Dışarı aktarma** bunun yerine, bu adımları izlemek sonra devam edin.
>
>1. Üstündeki **özellik sayfaları** iletişim kutusunda, değişiklik **yapılandırma** aşağı açılan **tüm yapılandırmaları**.
>
>1. Düzenleme kutusu yanında aşağı açılan denetimi özelliği bölmesinde seçin **önişlemci tanımları**ve ardından **Düzenle**.<br/><br/>![Önişlemci tanımları özelliğini Düzenle](media/mathlibrary-153bug-preprocessor-definitions-property.png "önişlemci tanımları özelliğini Düzenle")
>
>1. Üst bölmesinde **önişlemci tanımları** iletişim kutusunda, yeni bir sembol eklemek `MATHLIBRARY_EXPORTS`.<br/><br/>![MATHLIBRARY_EXPORTS simgesi eklemek](media/mathlibrary-153bug-preprocessor-definitions-dialog.png "MATHLIBRARY_EXPORTS Simge Ekle")
>
>1. Seçin **Tamam** kapatmak için **önişlemci tanımları** iletişim kutusunda ve ardından **Tamam** proje özellikleri yaptığınız değişiklikleri kaydetmek için.

### <a name="to-create-a-dll-project-in-older-versions-of-visual-studio"></a>Visual Studio'nun daha eski sürümleri DLL projesi oluşturmak için

1. Menü çubuğunda seçin **dosya**, **yeni**, **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda, genişletin **yüklü**, **şablonları**seçip **Visual C++**ve ardından Merkezi bölmesinde, **Win32 konsol uygulaması**. Girin `MathLibrary` içinde **adı** düzenleme kutusu proje için bir ad belirtin.

   ![MathLibrary proje adı](media/mathlibrary-project-name.png "MathLibrary proje adı")

1. Seçin **Tamam** kapatmak için düğmesini **yeni proje** iletişim ve başlangıç **Win32 Uygulama Sihirbazı'nı**.

   ![Win32 Uygulama Sihirbazı genel bakış](media/mathlibrary-project-wizard-1.png "Win32 Uygulama Sihirbazı genel bakış")

1. Seçin **sonraki** düğmesi. Üzerinde **uygulama ayarları** sayfasında **uygulama türü**seçin **DLL**.

   ![Win32 Uygulama Sihirbazı'nda DLL oluşturma](media/mathlibrary-project-wizard-2.png "Win32 Uygulama Sihirbazı'nda DLL oluşturma")

1. Seçin **son** projesi oluşturmak için düğmesi.

Sihirbaz çözümü tamamlandığında, oluşturulan proje ve kaynak dosyalarında görebilirsiniz **Çözüm Gezgini** Visual Studio'daki.

![Visual Studio'da çözüm oluşturulan](media/mathlibrary-solution-explorer-153.png "Visual Studio'da çözüm oluşturulan")

Sağ şimdi bu DLL oldukça yapmaz. Ardından, DLL işlevleri bildirmek için bir başlık dosyası oluştur dışa aktarır ve ardından daha kullanışlı hale getirmek için DLL işlev tanımları ekleyin.

### <a name="to-add-a-header-file-to-the-dll"></a>DLL üstbilgi dosyası eklemek için

1. Menü çubuğunda, işlevleri için bir üstbilgi dosyası oluşturmak için seçtiğiniz **proje**, **Yeni Öğe Ekle**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda, sol bölmede, select **Visual C++**. Orta bölmede seçin **üstbilgi dosyası (.h)**. Belirtin `MathLibrary.h` üstbilgi dosyası adı olarak.

   ![Yeni Öğe Ekle iletişim kutusunda Ekle'yi üstbilgi](media/mathlibrary-add-new-item-header-file.png "Yeni Öğe Ekle iletişim kutusunda Ekle'yi üstbilgi dosyası")

1. Seçin **Ekle** yeni Düzenleyicisi penceresinde görüntülenen boş üstbilgi dosyası oluşturmak için düğmesi.

   ![Boş MathLibrary.h dosyayı Düzenleyicide](media/edit-empty-mathlibrary-header.png "boş MathLibrary.h dosyayı düzenleyicide")

1. Üstbilgi dosyasının içeriğini bu kod ile değiştirin:

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

Bu üst bilgi dosyası genelleştirilmiş bir Fibonacci dizisi olan iki verilen ilk değer üretmek için bazı işlevler bildirir. Çağrı `fibonacci_init(1, 1)` tanıdık Fibonacci numara sırası oluşturur.

Önişlemci deyimlerini dosyanın en üstüne dikkat edin. Varsayılan olarak, bir DLL için yeni bir proje şablonu ekler  ***PROJECTNAME*&#95; Dışarı aktarma** DLL projesi için tanımlanan Önişlemci makroları için. Bu örnekte, Visual Studio tanımlar **MATHLIBRARY &#95; Dışarı aktarma** MathLibrary DLL projenizi ne zaman oluşturulur. (Visual Studio 2017 sürüm 15.3 sihirbazda bu büyük harflerle sembol tanımına zorlamaz. Projeniz "MathLibrary" adı tanımlanmış simgenin MathLibrary &#95;olup; Dışarı aktarma MATHLIBRARY &#95;yerine; DIŞA AKTARIR. That's vardır neden ek adımlar bu simgeyi eklemek için yukarıdaki.)

Zaman **MATHLIBRARY &#95; Dışarı aktarma** makrosu tanımlanır, **MATHLIBRARY &#95; API** makrosu kümeleri `__declspec(dllexport)` işlev bildirimleri değiştiricisi. Bu değiştirici derleyici ve böylece diğer uygulamalar tarafından kullanılan bir işlev veya değişken DLL'den dışarı aktarmak için bağlayıcı söyler. Zaman **MATHLIBRARY &#95; Dışarı aktarma** bir istemci uygulaması tarafından üst bilgi dosyasını dahil edildiğinde Örneğin, tanımsızdır **MATHLIBRARY &#95; API** geçerlidir `__declspec(dllimport)` bildirimlerine değiştiricisi. Bu değiştirici işlevi veya bir uygulamadaki değişken alınmasıyla en iyi duruma getirir. Daha fazla bilgi için bkz: [dllexport, dllimport](../cpp/dllexport-dllimport.md).

### <a name="to-add-an-implementation-to-the-dll"></a>DLL için bir uygulama eklemek için

1. Düzenleyicisi penceresinde sekmesini seçin **MathLibrary.cpp** zaten açıksa. Aksi durumda, buna **Çözüm Gezgini**açın **MathLibrary.cpp** içinde **kaynak dosyaları** klasöründe **MathLibrary** proje.

1. Düzenleyicisi'nde MathLibrary.cpp dosyasının içeriğini aşağıdaki kodla değiştirin:

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

Her şeyi kadarki çalıştığını doğrulamak için dinamik bağlantı kitaplığı derleyin. Derleme tercih **yapı**, **yapı çözümü** menü çubuğunda. Çıktı aşağıdakine benzer görünmelidir:

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

Tebrikler, Visual C++ kullanarak DLL'den oluşturduğunuzu düşünün. Ardından, DLL tarafından dışarı aktarılan işlevlerini kullanan bir istemci uygulaması oluşturacaksınız.

## <a name="create-a-client-app-that-uses-the-dll"></a>DLL kullanan bir istemci uygulaması oluşturma

DLL oluşturduğunuzda nasıl DLL kullanılabileceği konusunda düşünmeniz gerekir. Tarafından DLL dışarı aktarılan işlevlerin çağıran kodu derlemek için bildirimler istemci kaynak kodunda eklenmesi gerekir. DLL işlevleri çağrıları olduğunda çözülmüş, bağlantı zaman, bağlayıcı olmalıdır bir *kitaplığına*, gerçek bir kod yerine işlevlerin bulunacağı hakkında bilgi için Windows içeren kitaplık dosyası özel bir tür. Ve çalışma zamanında DLL istemciye işletim sistemi bulabilirsiniz konumda bulunmalıdır.

DLL'den kullanmak için olup olmadığını, sahip olduğunuz veya bir üçüncü taraf DLL istemci uygulaması projenize DLL bildirme üstbilgileri aktarır, bağlayıcı ve DLL için içeri aktarma kitaplıkları bulamıyor olmalıdır. Bunu yapmanın bir yolu, tüm bu dosyaların istemci projenize kopyalamaktır. İstemci geliştirme olsa da değiştirmek olası üçüncü taraf DLL'ler için bu bunları kullanmak için en iyi yolu olabilir. Ancak, DLL de derlerken yinelemesinden kaçınmak en iyisidir. Geliştirilme aşamasındadır DLL dosyalarının bir kopyasını yaparsanız, yanlışlıkla bir kopya, ancak diğer üstbilgi dosyasında değiştirme veya eski bir kitaplığını kullanın. Bu sorunu önlemek için istemci projenizdeki DLL projesi DLL üstbilgi dosyalarını içerecek şekilde INCLUDE yolu ayarlamanızı öneririz. Ayrıca, kitaplık yolu DLL projeden DLL içeri aktarma kitaplıkları dahil etmek için istemci projeniz olarak ayarlayın. Ve son olarak, yerleşik DLL DLL projesinde, yapı çıktı dizinine kopyalayın. Bu, istemci uygulamanızı oluşturma aynı DLL kodu kullanmasını sağlar.

### <a name="to-create-a-client-app-in-visual-studio-2017-version-153-or-later"></a>Bir istemci uygulaması 15.3 veya sonraki Visual Studio 2017 sürüm oluşturmak için

1. Yeni menü çubuğunda, oluşturduğunuz DLL kullanan bir C++ uygulaması oluşturmak için seçtiğiniz **dosya**, **yeni**, **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **Windows Masaüstü** altında **yüklü**, **Visual C++**. Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**. Proje adını belirtin `MathClient`, **adı** düzenleme kutusu.

   ![İstemci proje adı](media/mathclient-new-project-name-153.png "istemci proje adı")

1. Seçin **Tamam** başlatmak için **Windows Masaüstü projesi** Sihirbazı. Sihirbazda seçtiğiniz **Tamam** istemci uygulaması projesi oluşturmak için.

### <a name="to-create-a-client-app-in-older-versions-of-visual-studio-2017"></a>Visual Studio 2017 eski sürümleri bir istemci uygulaması oluşturmak için

1. Yeni menü çubuğunda, oluşturduğunuz DLL kullanan bir C++ uygulaması oluşturmak için seçtiğiniz **dosya**, **yeni**, **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **Win32** altında **yüklü**, **şablonları**, **Visual C++**. Orta bölmede seçin **Win32 konsol uygulaması**. Proje adını belirtin `MathClient`, **adı** düzenleme kutusu.

   ![İstemci proje adı](media/mathclient-project-name.png "istemci proje adı")

1. Seçin **Tamam** kapatmak için düğmesini **yeni proje** iletişim ve başlangıç **Win32 Uygulama Sihirbazı'nı**. Üzerinde **genel bakış** sayfasında **Win32 Uygulama Sihirbazı'nı** iletişim kutusunda, seçin **sonraki** düğmesi.

1. Üzerinde **uygulama ayarları** sayfasında **uygulama türü**seçin **konsol uygulaması** henüz seçili değilse.

1. Seçin **son** projesi oluşturmak için düğmesi.

Sihirbaz sona erdiğinde, en az konsol uygulama projesi sizin için oluşturulur. Ana kaynak dosyasının adı daha önce girdiğiniz proje adı ile aynıdır. Bu örnekte adlı **MathClient.cpp**. Oluşturabilir, ancak henüz DLL kullanmaz.

Ardından, kaynak kodunuzda MathLibrary işlevleri çağırmak için projenizi MathLibrary.h dosyası içermelidir. Bu üst bilgi dosyasını istemci uygulaması projenize kopyalayın ve var olan bir öğe olarak projeye eklemek. Bu, üçüncü taraf kitaplıklar için iyi bir seçimdir olabilir. Kod DLL için aynı anda istemci olarak çalışıyorsanız, ancak, bir üst bilgi dosyası diğer yansıtılmaz değişikliklere neden olabilir. Bu sorunu önlemek için değiştirebileceğiniz **ek içeren dizinler** özgün üstbilgisi yolunu eklemek için projenizin yolunda.

### <a name="to-add-the-dll-header-to-your-include-path"></a>DLL üstbilgi eklemek için yolu ekleyin

1. Açık **özellik sayfaları** iletişim kutusu için **MathClient** projesi.

1. İçinde **yapılandırma** açılan kutusunda **tüm yapılandırmaları** henüz seçili değilse.

1. Sol bölmede seçin **genel** altında **yapılandırma özellikleri**, **C/C++**.

1. Özellik bölmesinde yanındaki açılan denetimi seçin **ek içeren dizinler** düzenleme kutusuna ve ardından **Düzenle**.

   ![Ek içeren dizinler özelliğini Düzenle](media/mathclient-additional-include-directories-property.png "ek içeren dizinler özelliğini Düzenle")

1. Üst bölmede çift **ek içeren dizinler** düzenleme denetimi etkinleştirmek için iletişim kutusu.

1. Düzenleme denetimine konumunun yolunu belirtin **MathLibrary.h** üstbilgi dosyası. Bu durumda, göreli bir yol kullanabilirsiniz:

   `..\..\MathLibrary\MathLibrary`

   ![Ek içeren dizinler özelliğine Üstbilgi Konumu Ekle](media/mathclient-additional-include-directories.png "ek içeren dizinler özelliğine Üstbilgi Konumu Ekle")

1. Üstbilgi dosyası için yol girdikten sonra **ek içeren dizinler** iletişim kutusunda, seçin **Tamam** geri düğmesini **özellik sayfaları** iletişim kutusu, ve ardından **Tamam** yaptığınız değişiklikleri kaydetmek için düğmesi.

Şimdi içerebilir **MathLibrary.h** dosya ve istemci uygulamanızı bildirir işlevlerini kullanın. Değiştir **MathClient.cpp** bu kodu kullanarak:

```cpp
// MathClient.cpp : Client app for MathLibrary DLL.
#include "stdafx.h"
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

Bu kod derlenmiş ancak henüz uygulamanızı oluşturmak için gerekli içeri aktarma kitaplığı bağlayıcı bulamadığından, bağlı değil. Bağlayıcı başarıyla bağlamak için MathLibrary.lib doya kurabilmesi gerekir. Ayarlayarak yapı MathLibrary.lib dosya eklemelisiniz **ek bağımlılıklar** özelliği. Bir kez daha, istemci uygulaması projenize kitaplık dosyasını kopyalamak, ancak Kitaplığı hem istemci uygulaması geliştirme altında olması durumunda, bir kopya diğer yansıtılmaz değişikliklere neden olabilir. Bu sorunu önlemek için değiştirebileceğiniz **ek kitaplık dizinleri** bağlantı oluşturduğunuzda özgün kitaplık yoluna dahil etmek için projenize yolu.

### <a name="to-add-the-dll-import-library-to-your-project"></a>DLL içeri aktarma kitaplığını projenize eklemek için

1. Açık **özellik sayfaları** iletişim kutusu için **MathClient** projesi.

1. İçinde **yapılandırma** açılan kutusunda **tüm yapılandırmaları** henüz seçili değilse.

1. Sol bölmede seçin **giriş** altında **yapılandırma özellikleri**, **bağlayıcı**. Özellik bölmesinde yanındaki açılan denetimi seçin **ek bağımlılıklar** düzenleme kutusuna ve ardından **Düzenle**.

   ![Ek Bağımlılıklar özelliğini Düzenle](media/mathclient-additional-dependencies-property.png "ek bağımlılıklar özelliğini Düzenle")

1. İçinde **ek bağımlılıklar** iletişim kutusunda, eklemek `MathLibrary.lib` üst listesine Denetim Düzenle.

   ![Kitaplık bağımlılık ekleme](media/mathclient-additional-dependencies.png "kitaplığı bağımlılık Ekle")

1. Seçin **Tamam** dönmek için **özellik sayfaları** iletişim kutusu.

1. Sol bölmede seçin **genel** altında **yapılandırma özellikleri**, **bağlayıcı**. Özellik bölmesinde yanındaki açılan denetimi seçin **ek kitaplık dizinleri** düzenleme kutusuna ve ardından **Düzenle**.

   ![Ek Kitaplık dizinleri özelliğini Düzenle](media/mathclient-additional-library-directories-property.png "ek kitaplık dizinleri özelliğini Düzenle")

1. Üst bölmede çift **ek kitaplık dizinleri** düzenleme denetimi etkinleştirmek için iletişim kutusu. Düzenleme denetimine konumunun yolunu belirtin **MathLibrary.lib** dosya. Hata ayıklama ve yayın için çalışır derlemeler makrosu kullanmak için bu değeri girin:

   `..\..\MathLibrary\$(IntDir)`

   ![Kitaplık dizinine ekleme](media/mathclient-additional-library-directories.png "kitaplığı Dizin Ekle")

1. Kitaplık dosyası için yol girdikten sonra **ek kitaplık dizinleri** iletişim kutusunda, seçin **Tamam** geri düğmesini **özellik sayfaları** iletişim kutusu.

İstemci uygulamanızı, şimdi derlemek ve başarıyla bağlamak, ancak hala çalıştırmak için gereken her şeyi yok. İşletim sistemi uygulamanızı yüklediğinde MathLibrary DLL için arar. DLL belirli sistem dizinleri, ortam yolu veya yerel uygulama dizinindeki bulamıyorsanız, yükleme başarısız olur. Bu sorunu önlemek için bir DLL oluşturma işleminin bir parçası olarak, istemci yürütülebilir içeren dizine kopyalamak için yoludur. DLL kopyalamak için ekleyebileceğiniz bir **oluşturma sonrası olay** projeniz için bir komut eklemek için DLL derleme çıktı dizinine kopyalar. Yalnızca, eksik veya değişti ve makrolar ve yapılandırmanız için doğru hata ayıklama veya perakende konumlardan kopyalamak için kullanıyorsa burada belirtilen komut DLL kopyalar.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>Bir oluşturma sonrası olay DLL kopyalamak için

1. Açık **özellik sayfaları** iletişim kutusu için **MathClient** zaten açık değilse proje.

1. Yapılandırma açılan kutusunda **tüm yapılandırmaları** henüz seçili değilse.

1. Sol bölmede seçin **oluşturma sonrası olay** altında **yapılandırma özellikleri**, **yapı olayları**.

1. Düzenleme denetimine özelliği bölmesinde seçin **komut satırı** alanında ve şu komutu girin:

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![Yapı sonrası komut eklemek](media/mathclient-post-build-command-line.png "oluşturma sonrası komut ekleme")

1. Seçin **Tamam** proje özellikleri yaptığınız değişiklikleri kaydetmek için düğmesi.

Şimdi istemci uygulamanızı oluşturmak ve çalıştırmak için gereken her şeyi içerir. Uygulama seçerek yapı **yapı**, **yapı çözümü** menü çubuğunda. **Çıkış** Visual Studio'daki şöyle bir şey içermelidir:

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>stdafx.cpp
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.pdb (Partial PDB)
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Tebrikler, DLL dosyanızda işlevleri çağıran bir uygulama oluşturduğunuza. Şimdi ne yaptığını görmek için uygulamanızı çalıştırın. Menü çubuğunda seçin **hata ayıklama**, **hata ayıklama olmadan Başlat**. Visual Studio programı çalıştırmak bir komut penceresi açar. Çıktı son parçası, aşağıdaki gibi görünmelidir:

![Hata ayıklama olmadan istemci uygulamasını Başlat](media/mathclient-run-without-debugging.png "hata ayıklama olmadan istemci uygulamasını Başlat")

Komut penceresini kapatmak için herhangi bir tuşa basın.

DLL ve bir istemci uygulaması oluşturduğunuza göre deneyebilirsiniz. İstemci uygulama kodunda kesme noktalarını ayarlama deneyin ve hata ayıklayıcısı'ndaki uygulamayı çalıştırın. Bkz. kitaplığı çağrısını adım ne olur. DLL kullanan başka bir istemci uygulama yazmak veya diğer işlevleri kitaplığa ekleyin.

Uygulamanızı dağıttığınızda, kullandığı DLL'leri dağıtmanız gerekir. Bunları, uygulamanız ile aynı dizinde olarak da bilinen koymak için oluşturduğunuz veya dahil DLL'leri üçüncü tarafların uygulamanıza kullanılabilmesi için en basit yolu olan *uygulama yerel dağıtım*. Dağıtımı hakkında daha fazla bilgi için bkz: [Visual C++ üzerinde dağıtım](..\ide\deployment-in-visual-cpp.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)  
[Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)  
[İzlenecek Yol: Programınızı Dağıtma (C++)](../ide/walkthrough-deploying-your-program-cpp.md)  
[Visual Basic Uygulamalarından DLL İşlevleri Çağırma](../build/calling-dll-functions-from-visual-basic-applications.md)