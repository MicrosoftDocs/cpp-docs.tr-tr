---
title: 'İzlenecek yol: Kendi dinamik bağlantı kitaplığınızı oluşturma ve kullanma (C++)'
description: Visual C++ Studio 'Da bir Windows dinamik bağlantı KITAPLıĞı (dll) oluşturmak için kullanın.
ms.custom: conceptual
ms.date: 07/17/2019
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
ms.openlocfilehash: 8ca89471177ba2d1fa98bfaf51b86ed15dcd6d2f
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299821"
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>İzlenecek yol: Kendi dinamik bağlantı kitaplığınızı oluşturma ve kullanma (C++)

Bu adım adım izlenecek yol, Visual Studio IDE 'nin içinde C++yazılmış kendi dinamik bağlantı KITAPLıĞıNıZı (dll) oluşturmak için nasıl kullanılacağını ve sonra başka bir C++ uygulamadan nasıl kullanıldığını gösterir. Dll 'Ler (UNIX tabanlı işletim sistemlerinde paylaşılan kitaplıklar olarak da bilinir), en kullanışlı Windows bileşenleri türlerinden biridir. Bunları kod ve kaynakları paylaşmak, uygulamalarınızın boyutunu daraltmak ve uygulamalarınızı daha kolay hale getirmek ve genişletmek için bir yöntem olarak kullanabilirsiniz. Bu kılavuzda, bazı matematik işlevlerini uygulayan bir DLL oluşturun ve ardından DLL 'den işlevleri kullanan bir konsol uygulaması oluşturursunuz. Bu şekilde, Windows dll 'Lerinde kullanılan bazı programlama tekniklerinden ve kurallarından bir giriş alırsınız.

Bu izlenecek yol aşağıdaki görevleri içerir:

- Visual Studio 'da bir DLL projesi oluşturun.

- DLL 'ye aktarılmış işlevler ve değişkenler ekleyin.

- Visual Studio 'da bir konsol uygulaması projesi oluşturun.

- Konsol uygulamasındaki DLL 'den içeri aktarılan işlevleri ve değişkenleri kullanın.

- Tamamlanmış uygulamayı çalıştırın.

Statik olarak bağlı bir kitaplık gibi, bir DLL değişkenleri, işlevleri ve kaynakları ada göre _dışa aktarır_ ve uygulamanız bu adları bu değişkenleri, işlevleri ve kaynakları kullanacak şekilde _içeri aktarır_ . Statik olarak bağlı bir kitaplığın aksine, Windows, uygulamanızda içeri aktarımları, yükleme zamanında veya çalışma zamanında bir DLL 'de dışarı aktarmalar için bağlantı zamanında bağlamak yerine, bir DLL 'ye bağlar. Windows, bu bağlantıları yapmak için standart C++ derleme modelinin parçası olmayan ek bilgiler gerektirir. MSVC derleyicisi, bu ek bilgileri sağlamak için Microsoft 'a C++ özgü bazı uzantılar uygular. Bu uzantıları gittiğimiz için açıkladık.

Bu izlenecek yol iki Visual Studio çözümü oluşturur; DLL 'yi ve istemci uygulamasını oluşturan birini oluşturan bir tane. DLL, platform ve çağırma ve bağlama kuralları eşleştiği sürece diğer diller kullanılarak oluşturulan uygulamalardan çağrılabilmesi için C çağırma kuralını kullanır. İstemci uygulaması, Windows 'un uygulamayı yükleme zamanında DLL 'ye bağladığı _örtük bağlama_kullanır. Bu bağlama, uygulamanın, statik olarak bağlanmış bir kitaplıktaki işlevleri gibi DLL tarafından sağlanan işlevleri çağırmasını sağlar.

Bu izlenecek yol bazı yaygın durumları kapsamaz. Diğer programlama dilleri tarafından C++ dll 'lerin kullanımını göstermez. Yalnızca kaynak DLL 'nin nasıl oluşturulacağını göstermez. Ayrıca, dll 'Leri yükleme sırasında değil çalışma zamanında yüklemek için açık bağlama kullanımını göstermez. Bunun için, Visual Studio 'Yu bu işlemleri yapmak için kullanabilirsiniz. Dll 'Ler hakkında daha fazla bilgi için bkz. [Visual Studio 'DaC++ C/dll oluşturma](dlls-in-visual-cpp.md). Örtük bağlama ve açık bağlama hakkında daha fazla bilgi için, [Hangi bağlama yönteminin kullanılacağını belirleme](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)konusuna bakın. C-Language bağlantı C++ kurallarını kullanan programlama dilleri ile kullanmak üzere dll 'ler oluşturma hakkında bilgi için bkz. [c C++ Dili Çalıştırılabilirlerinde kullanmak için işlevleri dışarı aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md). .NET dilleri ile kullanmak üzere dll oluşturma hakkında daha fazla bilgi için, bkz. [Visual Basic UYGULAMALARıNDAN dll Işlevleri çağırma](calling-dll-functions-from-visual-basic-applications.md).

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Windows 7 veya sonraki sürümlerini çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10 ' un kullanılması önerilir.

- Visual Studio 'nun bir kopyası. Visual Studio 'Yu indirme ve yükleme hakkında daha fazla bilgi için bkz. [Visual Studio 'Yu yükleme](/visualstudio/install/install-visual-studio). Yükleyiciyi çalıştırdığınızda, iş yüküyle **masaüstü geliştirme C++**  ' nin işaretli olduğundan emin olun. Visual Studio 'Yu yüklerken bu iş yükünü yüklemediyseniz endişelenmeyin. Yükleyiciyi yeniden çalıştırabilir ve şimdi yükleyebilirsiniz.

   ![Ile C++ masaüstü geliştirme](media/desktop-development-with-cpp.png "Ile C++ masaüstü geliştirme")

- Visual Studio IDE kullanmanın temellerini anlama. Daha önce Windows Masaüstü uygulamaları kullandıysanız muhtemelen izleyebilirsiniz. Giriş için bkz. [Visual STUDIO IDE Özellik turu](/visualstudio/ide/visual-studio-ide).

- Üzerinde izlenecek C++ dilin temel sayısının yeterince anlaşılmasıdır. Endişelenmeyin, çok karmaşık bir şey yapmadık.

## <a name="create-the-dll-project"></a>DLL projesi oluşturma

Bu görev kümesinde, DLL 'niz için bir proje oluşturur, kod ekler ve derler. Başlamak için Visual Studio IDE 'yi başlatın ve gerekirse oturum açın. Yönergeler, kullandığınız Visual Studio sürümüne bağlı olarak biraz farklılık gösterir. Bu sayfanın sol üst kısmındaki denetimde doğru sürümün seçili olduğundan emin olun.

::: moniker range="=vs-2019"

### <a name="to-create-a-dll-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de bir DLL projesi oluşturmak için

1. **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda **Dosya** > **Yeni** > **Proje** ' yi seçin.

   ![Yeni BIR DLL projesi oluştur](media/create-new-dll-project-2019.png "MathLibrary projesi oluşturma")

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **kitaplık**olarak ayarlayın. 

1. Filtre uygulanmış proje türleri listesinden **dinamik bağlantı kitaplığı (dll)** öğesini seçin ve ardından **İleri**' yi seçin. Bir sonraki sayfada, proje için `MathLibrary` bir ad belirtmek üzere **ad** kutusuna girin ve isterseniz proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-dll-project-in-visual-studio-2017"></a>Visual Studio 2017 ' de bir DLL projesi oluşturmak için

1. **Yeni proje** iletişim kutusunu açmak için menü çubuğunda **Dosya** > **Yeni** > **Proje** ' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, gerekirse **yüklü** ve  **C++ görsel** ' i genişletin ve ardından **Windows Masaüstü**' ni seçin. Orta bölmede **Windows Masaüstü Sihirbazı**' nı seçin. Proje `MathLibrary` için bir ad belirtmek üzere **ad** kutusuna girin.

   ![MathLibrary projesini adlandırın](media/mathlibrary-new-project-name-153.png "MathLibrary projesini adlandırın")

1. **Yeni proje** iletişim kutusunu kapatmak ve **Windows Masaüstü projesi** Sihirbazı 'nı başlatmak için **Tamam** düğmesini seçin.

1. **Windows Masaüstü projesi** sihirbazında, **uygulama türü**altında, **dinamik bağlantı kitaplığı (. dll)** öğesini seçin.

   ![Windows Masaüstü projesi SIHIRBAZıNDA dll oluşturma](media/mathlibrary-desktop-project-wizard-dll.png "Windows Masaüstü projesi SIHIRBAZıNDA dll oluşturma")

1. Projeyi oluşturmak için **Tamam** düğmesini seçin.

> [!NOTE]
> Visual Studio 2017 sürüm 15,3 ' de bir sorunu çözmesi için ek adımlar gereklidir. Bu değişikliği yapmanız gerektiğini öğrenmek için bu yönergeleri izleyin.
>
>1. **Çözüm Gezgini**, zaten seçili değilse, **' MathLibrary ' çözümünün**altındaki **MathLibrary** projesini seçin.
>
>1. Menü çubuğunda, **Proje** > **özellikleri**' ni seçin.
>
>1. **Özellik sayfaları** iletişim kutusunun sol bölmesinde, **yapılandırma özellikleri** > **C++** ' nin altında **Önişlemci** ' yi seçin. **Önişlemci tanımları** özelliğinin içeriğini kontrol edin.<br/><br/>![Önişlemci tanımları özelliğini denetleyin](media/mathlibrary-153bug-preprocessor-definitions-check.png "Önişlemci tanımları özelliğini denetleyin")<br/><br/>Ön **Işlemci tanımları** listesinde **&#95;MATHLIBRARY dışarı aktarmalar** görürseniz, herhangi bir şeyi değiştirmeniz gerekmez. Bunun yerine **&#95;MathLibrary dışarı aktarmalar** görürseniz, bu adımları izlemeye devam edin.
>
>1. **Özellik sayfaları** iletişim kutusunun üst kısmında **yapılandırma** açılan listesini **Tüm yapılandırmalara**değiştirin.
>
>1. Özellik bölmesinde, **Önişlemci tanımları**için düzenleme kutusunun yanındaki aşağı açılan denetimi seçin ve ardından **Düzenle**' yi seçin.<br/><br/>![Önişlemci tanımları özelliğini Düzenle](media/mathlibrary-153bug-preprocessor-definitions-property.png "Önişlemci tanımları özelliğini Düzenle")
>
>1. Ön **Işlemci tanımları** iletişim kutusunun üst bölmesinde yeni bir sembol `MATHLIBRARY_EXPORTS`ekleyin.<br/><br/>![MATHLIBRARY_EXPORTS sembolünü ekleme](media/mathlibrary-153bug-preprocessor-definitions-dialog.png "MATHLIBRARY_EXPORTS sembolünü ekleme")
>
>1. Ön **Işlemci tanımları** iletişim kutusunu kapatmak için **Tamam** ' ı seçin ve sonra değişikliklerinizi proje özelliklerine kaydetmek için **Tamam** ' ı seçin.

::: moniker-end

::: moniker range="=vs-2015"

### <a name="to-create-a-dll-project-in-older-versions-of-visual-studio"></a>Visual Studio 'nun eski sürümlerinde bir DLL projesi oluşturmak için

1. Menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** > **Şablonlar**' ı genişletin ve **görsel C++** ' i seçin ve ardından orta bölmedeki **Win32 konsol uygulaması**' nı seçin. Proje `MathLibrary` için bir ad belirtmek üzere **ad** düzenleme kutusuna girin.

   ![MathLibrary projesini adlandırın](media/mathlibrary-project-name.png "MathLibrary projesini adlandırın")

1. **Yeni proje** iletişim kutusunu kapatmak ve **Win32 uygulama Sihirbazı**' nı başlatmak için **Tamam** düğmesini seçin.

   ![Win32 uygulama Sihirbazına Genel Bakış](media/mathlibrary-project-wizard-1.png "Win32 uygulama Sihirbazına Genel Bakış")

1. Seçin **sonraki** düğmesi. **Uygulama ayarları** sayfasında, **uygulama türü**altında, **DLL**' yi seçin.

   ![Win32 uygulama Sihirbazı 'NDA dll oluşturma](media/mathlibrary-project-wizard-2.png "Win32 uygulama Sihirbazı 'NDA dll oluşturma")

1. Projeyi oluşturmak için **son** düğmesini seçin.

Sihirbaz çözümü tamamladığında, oluşturulan proje ve kaynak dosyaları Visual Studio 'da **Çözüm Gezgini** penceresinde görebilirsiniz.

![Visual Studio 'Da oluşturulan çözüm](media/mathlibrary-solution-explorer-153.png "Visual Studio 'Da oluşturulan çözüm")

Şu anda bu DLL çok fazla yapmaz. Daha sonra, DLL dışarı aktarmaların bulunduğu işlevleri bildirmek için bir üst bilgi dosyası oluşturur ve ardından daha kullanışlı hale getirmek için işlev tanımlarını DLL 'ye eklersiniz.

::: moniker-end

### <a name="to-add-a-header-file-to-the-dll"></a>DLL 'ye bir üst bilgi dosyası eklemek için

1. İşlevleriniz için bir üst bilgi dosyası oluşturmak için, menü çubuğunda **Proje** > **Ekle yeni öğe**' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda, sol bölmede, **C++görsel**' i seçin. Orta bölmede **üst bilgi dosyası (. h)** öğesini seçin. Üst `MathLibrary.h` bilgi dosyasının adı olarak belirtin.

   ![Yeni öğe Ekle iletişim kutusunda üst bilgi Ekle](media/mathlibrary-add-new-item-header-file.png "Yeni öğe Ekle iletişim kutusuna üstbilgi dosyası Ekle")

1. Yeni bir düzenleyici penceresinde görüntülenecek boş bir üst bilgi dosyası oluşturmak için **Ekle** düğmesini seçin.

   ![Düzenleyicide boş MathLibrary. h dosyası](media/edit-empty-mathlibrary-header.png "Düzenleyicide boş MathLibrary. h dosyası")

1. Üstbilgi dosyasının içeriğini şu kodla değiştirin:

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

Bu üstbilgi dosyası, bir Genelleştirilmiş Fipriaccı sırası oluşturmak için bazı işlevleri bildirir ve bu iki başlangıç değeri verilir. İçin `fibonacci_init(1, 1)` bir çağrı tanıdık fibonaccı numara sırasını oluşturur.

Dosyanın en üstündeki Önişlemci ifadelerine dikkat edin. Varsayılan olarak, bir dll için yeni proje şablonu, DLL projesi için tanımlanan Önişlemci makrolarını  **\<dışarı&#95;aktarır > ProjectName\</em >** ekler. Bu örnekte, MathLibrary DLL projeniz oluşturulduğunda Visual Studio **&#95;MATHLIBRARY dışarı aktarmaları** tanımlar. 

::: moniker range="=vs-2017"

(Visual Studio 2017 sürüm 15,3 ' deki sihirbaz bu sembol tanımını büyük harfe zorlamaz. Projenizi "MathLibrary" olarak adlandırın, tanımlanan sembol MATHLIBRARY&#95;&#95;dışarı aktarmaları yerine MathLibrary dışarı aktarmaları olur. Bu nedenle, bu simgeyi eklemek için yukarıdaki ek adımlar vardır.)

::: moniker-end

**MATHLIBRARY&#95;dışarı aktarma** makrosu tanımlandığında, **MATHLIBRARY&#95;API** makrosu işlev bildirimlerinde `__declspec(dllexport)` değiştiricisini ayarlar. Bu değiştirici, derleyiciye ve bağlayıcıya, başka uygulamalar tarafından kullanılabilmesi için DLL 'den bir işlev veya değişken dışarı aktarmayı söyler. **&#95;MATHLIBRARY dışarı aktarmalar** tanımsız olduğunda, örneğin, üstbilgi dosyası bir istemci uygulaması tarafından dahil edildiğinde, `__declspec(dllimport)` **&#95;MATHLIBRARY API 'si** bildirime değiştiricisini uygular. Bu değiştirici, bir uygulamadaki işlevin veya değişkenin içe aktarımını iyileştirir. Daha fazla bilgi için bkz. [dllexport, dllimport](../cpp/dllexport-dllimport.md).

### <a name="to-add-an-implementation-to-the-dll"></a>DLL 'ye bir uygulama eklemek için

::: moniker range="vs-2019"

1. **Çözüm Gezgini**, **kaynak dosyalar** düğümüne sağ tıklayın ve önceki adımda yeni bir üstbilgi dosyası eklediğiniz şekilde adlı `MathLibrary.cpp` yeni bir. cpp dosyası ekleyin.

::: moniker-end

1. Düzenleyici penceresinde, zaten açıksa **MathLibrary. cpp** sekmesini seçin. Değilse, **Çözüm Gezgini**Içinde, **MathLibrary** projesinin **kaynak dosyaları** klasöründe **MathLibrary. cpp** ' yi açın.

1. Düzenleyicide, MathLibrary. cpp dosyasının içeriğini aşağıdaki kodla değiştirin:

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "stdafx.h" // use pch.h in Visual Studio 2019
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

Her şeyin şu ana kadar çalıştığını doğrulamak için dinamik bağlantı kitaplığını derleyin. Derlemek için, menü çubuğunda derleme**çözümü** **Oluştur** > ' u seçin. Çıktı şuna benzer görünmelidir. DLL yürütülebilir dosyasının ve ilgili derleyici çıkışının doğrudan çözüm klasörünün altında *hata ayıklama* adlı bir klasöre yerleştirildiğini unutmayın. Yayın derlemesi oluşturursanız, çıktı *yayın*adlı bir klasöre yerleştirilir:

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>MathLibrary.cpp
1>dllmain.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.pdb (Partial PDB)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Tebrikler, Visual Studio 'Yu kullanarak bir DLL oluşturdunuz! Ardından, DLL tarafından dışarıya aktarılmış işlevleri kullanan bir istemci uygulaması oluşturacaksınız.

## <a name="create-a-client-app-that-uses-the-dll"></a>DLL 'yi kullanan bir istemci uygulaması oluşturma

Bir DLL oluşturduğunuzda, DLL 'nizin nasıl kullanılabileceğini düşünmeniz gerekir. DLL tarafından dışarıya alınan işlevleri çağıran kodu derlemek için, bildirimlerin istemci kaynak koduna dahil olması gerekir. Bağlantı zamanında, bu DLL işlevlerine yapılan çağrılar çözümlenirse bağlayıcının bir *içeri aktarma kitaplığı*olması gerekir, bu, gerçek kod yerine işlevleri bulma hakkında bilgi içeren özel bir kitaplık dosyasıdır. Çalışma zamanında DLL, işletim sisteminin bulabileceği bir konumda istemci için kullanılabilir olmalıdır.

Kendi veya üçüncü taraf DLL 'niz olsun, bir DLL 'yi kullanmak için, istemci uygulama projeniz DLL dışarı aktarmaları, bağlayıcı için içeri aktarma kitaplıklarını ve DLL 'nin kendisini bildiren üstbilgileri bulmalıdır. Tek yönlü, bu dosyaların hepsini istemci projenize kopyalamadır. İstemciniz geliştirirken değişmemiş olan üçüncü taraf dll 'Ler için, bu yöntem bunları kullanmanın en iyi yolu olabilir. Ancak, DLL 'yi de oluşturduğunuzda çoğaltmaktan kaçınmak daha iyidir. Geliştirme aşamasında olan DLL dosyalarının bir kopyasını yaparsanız, yanlışlıkla bir kopyada bir başlık dosyasını değiştirebilir, diğerini değil veya güncel olmayan bir kitaplık kullanamazsınız. Bu sorundan kaçınmak için, dll projesinden DLL üstbilgi dosyalarını dahil etmek için istemci projenizdeki ekleme yolunu ayarlamanızı öneririz. Ayrıca, DLL projesinden DLL içeri aktarma kitaplıklarını dahil etmek için istemci projenizdeki kitaplık yolunu ayarlayın. Son olarak, derleme çıkış dizininize DLL projesinden oluşturulan DLL 'yi kopyalayın. Bu adım, istemci uygulamanızın oluşturduğunuz DLL kodunu kullanmasını sağlar.

::: moniker range="vs-2019"

### <a name="to-create-a-client-app-in-visual-studio-2019"></a>Visual Studio 2019 ' de bir istemci uygulaması oluşturmak için

1. **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda **Dosya** > **Yeni** > **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol**olarak ayarlayın. 

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri**' yi seçin. Bir sonraki sayfada, proje için `MathClient` bir ad belirtmek üzere **ad** kutusuna girin ve isterseniz proje konumunu belirtin.

   ![İstemci projesini adlandırın](media/mathclient-project-name-2019.png "İstemci projesini adlandırın")

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-client-app-in-visual-studio-2017"></a>Visual Studio 2017 ' de bir istemci uygulaması oluşturmak için

1. Oluşturduğunuz DLL 'yi C++ kullanan bir uygulama oluşturmak için, menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** > **C++görsel**altında **Windows Masaüstü** ' nü seçin. Orta bölmede **Windows Masaüstü Sihirbazı**' nı seçin. Proje `MathClient`için **ad düzenleme kutusunda** adı belirtin.

   ![İstemci projesini adlandırın](media/mathclient-new-project-name-153.png "İstemci projesini adlandırın")

1. **Windows Masaüstü projesi** sihirbazını başlatmak için **Tamam ' ı** seçin. Sihirbazda, istemci uygulama projesini oluşturmak için **Tamam** ' ı seçin.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-client-app-in-older-versions-of-visual-studio-2017"></a>Visual Studio 'nun eski sürümlerinde bir istemci uygulaması oluşturmak için 2017

1. Oluşturduğunuz DLL 'yi C++ kullanan bir uygulama oluşturmak için, menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** > **Şablonlar** > **görseli C++** altında **Win32** öğesini seçin. Orta bölmede **Win32 konsol uygulaması**' nı seçin. Proje `MathClient`için **ad düzenleme kutusunda** adı belirtin.

   ![İstemci projesini adlandırın](media/mathclient-project-name.png "İstemci projesini adlandırın")

1. **Yeni proje** iletişim kutusunu kapatmak ve **Win32 uygulama Sihirbazı**' nı başlatmak için **Tamam** düğmesini seçin. **Win32 uygulama Sihirbazı** Iletişim kutusunun **genel bakış** sayfasında **İleri** düğmesini seçin.

1. **Uygulama ayarları** sayfasında, **uygulama türü**altında, henüz seçili değilse **konsol uygulaması** ' nı seçin.

1. Projeyi oluşturmak için **son** düğmesini seçin.

::: moniker-end

Sihirbaz tamamlandığında, sizin için en az bir konsol uygulaması projesi oluşturulur. Ana kaynak dosyanın adı, daha önce girdiğiniz proje adıyla aynıdır. Bu örnekte, **MathClient. cpp**olarak adlandırılmıştır. Onu oluşturabilirsiniz, ancak henüz DLL 'nizi kullanmaz.

Sonra, kaynak kodunuzda MathLibrary işlevlerini çağırmak için projenizin MathLibrary. h dosyasını içermesi gerekir. Bu üst bilgi dosyasını istemci uygulama projenize kopyalayabilir, ardından projeye varolan bir öğe olarak ekleyebilirsiniz. Bu yöntem, üçüncü taraf kitaplıklar için iyi bir seçenek olabilir. Bununla birlikte, istemciniz ile aynı anda DLL 'niz için kod üzerinde çalışıyorsanız, diğer bir başlık dosyasındaki değişikliklere yol açabilir. Bu sorunu önlemek için, projenizdeki **ek Içerme dizinleri** yolunu, özgün üst bilgi yolunu içerecek şekilde değiştirebilirsiniz.

### <a name="to-add-the-dll-header-to-your-include-path"></a>DLL üst bilgisini ekleme yolunuza eklemek için

1. **Özellik sayfaları** iletişim kutusunu açmak için **Çözüm Gezgini** 'teki **MathClient** düğümüne sağ tıklayın.

1. **Yapılandırma** açılan kutusunda, henüz seçili değilse **tüm yapılandırmalar** ' ı seçin.

1. Sol bölmede, **yapılandırma özellikleri** > **C++** ' nin altında **genel** ' i seçin.

1. Özellik bölmesinde, **Ek ekleme dizinleri** düzenleme kutusunun yanındaki açılan denetimi seçin ve ardından **Düzenle**' yi seçin.

   ![Ek Içerme dizinleri özelliğini Düzenle](media/mathclient-additional-include-directories-property.png "Ek Içerme dizinleri özelliğini Düzenle")

1. Bir düzenleme denetimini etkinleştirmek için **Ek ekleme dizinleri** iletişim kutusunun üst bölmesine çift tıklayın.

1. Düzenleme denetiminde, **MathLibrary. h** üstbilgi dosyasının konumunun yolunu belirtin. Aşağı oka ve ardından  **\<> Düzenle**' yi seçin. Doğru klasöre gitmek için klasör simgesine ve ardından üç nokta ( **...** ) simgesine tıklayabilirsiniz.
 
   Ayrıca, bu durumda, istemci projesindeki. cpp dosyalarınızı içeren klasörden, DLL projesindeki. h dosyasını içeren klasöre göreli bir yol yazabilirsiniz. İstemci projeniz DLL çözümüyle aynı klasördeki ayrı bir çözümde ise, göreli yol şuna benzemelidir:

   `..\MathLibrary\MathLibrary`

   DLL 'niz ve istemci projeleriniz aynı çözümde ise veya çözümler farklı klasörlerde varsa, daha önce açıklanan yöntemi kullanarak ilgili yolu uygun şekilde ayarlamanız veya başka bir klasöre gözatmalısınız.

   ![Üstbilgi konumunu ek ekleme dizinleri özelliğine ekleyin](media/mathclient-additional-include-directories.png "Üstbilgi konumunu ek ekleme dizinleri özelliğine ekleyin")

1. **Ek dizinleri Ekle** iletişim kutusunda üstbilgi dosyasının yolunu girdikten sonra, **Özellik sayfaları** iletişim kutusuna geri dönmek için **Tamam** düğmesini seçin ve ardından değişikliklerinizi kaydetmek için **Tamam** düğmesini seçin.

Artık **MathLibrary. h** dosyasını dahil edebilir ve istemci uygulamanızda bildirdiği işlevleri kullanabilirsiniz. **MathClient. cpp** içeriğini şu kodu kullanarak değiştirin:

```cpp
// MathClient.cpp : Client app for MathLibrary DLL.
// #include "pch.h" Uncomment for Visual Studio 2017 and earlier
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

Bağlayıcı, uygulamayı henüz derlemek için gereken içeri aktarma kitaplığını bulamadığı için bu kod derlenebilir, ancak bağlanamaz. Bağlayıcı başarıyla bağlanacak MathLibrary. lib dosyasını bulmalıdır. **Ek bağımlılıklar** özelliğini ayarlayarak MathLibrary. lib dosyasını yapıya ekleyin. Bir kez daha, kitaplık dosyasını istemci uygulama projenize kopyalayabilirsiniz, ancak hem kitaplık hem de istemci uygulaması geliştirme aşamasındadır; bu, diğeri de görünmeyen bir kopyada değişikliklere yol açabilir. Bu sorunu önlemek için, oluşturduğunuz **Ek kitaplık dizinleri** yolunu, bağladığınızda orijinal kitaplığın yolunu içerecek şekilde değiştirebilirsiniz.

### <a name="to-add-the-dll-import-library-to-your-project"></a>DLL içeri aktarma kitaplığını projenize eklemek için

1. **Özellik sayfaları** iletişim kutusunu açmak için **Çözüm Gezgini** 'teki **MathClient** düğümüne sağ tıklayın.

1. **Yapılandırma** açılan kutusunda, henüz seçili değilse **tüm yapılandırmalar** ' ı seçin. Bu ayar, yolun hem hata ayıklama hem de yayın yapıları için ayarlanmasını sağlar.

1. Sol bölmede, **yapılandırma özellikleri** > **bağlayıcı**altında **giriş** ' i seçin. Özellik bölmesinde, **ek bağımlılıklar** düzenleme kutusunun yanındaki açılan denetimi seçin ve ardından **Düzenle**' yi seçin.

   ![Ek bağımlılıklar özelliğini Düzenle](media/mathclient-additional-dependencies-property.png "Ek bağımlılıklar özelliğini Düzenle")

1. **Ek bağımlılıklar** iletişim kutusunda, en üstteki `MathLibrary.lib` düzenleme denetimindeki listeye ekleyin.

   ![Kitaplık bağımlılığını ekleyin](media/mathclient-additional-dependencies.png "Kitaplık bağımlılığını ekleyin")

1. **Özellik sayfaları** iletişim kutusuna geri dönmek için **Tamam ' ı** seçin.

1. Sol bölmede, **yapılandırma özellikleri** > **Bağlayıcısı**' nın altında **genel** ' i seçin. Özellik bölmesinde, **Ek kitaplık dizinleri** düzenleme kutusunun yanındaki açılan denetimi seçin ve ardından **Düzenle**' yi seçin.

   ![Ek kitaplık dizinleri özelliğini Düzenle](media/mathclient-additional-library-directories-property.png "Ek kitaplık dizinleri özelliğini Düzenle")

1. Bir düzenleme denetimini etkinleştirmek için **Ek kitaplık dizinleri** iletişim kutusunun üst bölmesine çift tıklayın. Düzenleme denetiminde, **MathLibrary. lib** dosyasının konumunun yolunu belirtin. Doğrudan çözüm klasörünüzün altında adlı `Debug` bir klasördür. Yayın derlemesi oluşturursanız, çıktı adlı `Release`bir klasöre yerleştirilir. Aşağıdaki makroyu kullanarak bağlayıcı, oluşturduğunuz tür derlemeyi ne olursa olsun DLL 'nizi bulabilir:

   **Visual Studio 2019:**

   `..\MathLibrary\$(IntDir)`

   **Visual Studio 2017 ve öncesi:**

   `..\..\MathLibrary\$(IntDir)`

   ![Kitaplık dizinini ekleme](media/mathclient-additional-library-directories.png "Kitaplık dizinini ekleme")

1. Kitaplık dosyasının yolunu **Ek kitaplık dizinleri** iletişim kutusunda girdikten sonra, **Özellik sayfaları** iletişim kutusuna geri dönmek için **Tamam** düğmesini seçin.

İstemci uygulamanız artık başarıyla derleyip bağlantı oluşturabilir, ancak çalışması gereken her şeyi de yok. İşletim sistemi uygulamanızı yüklediğinde, MathLibrary DLL 'sini arar. DLL 'yi belirli sistem dizinlerinde, ortam yolunda veya yerel uygulama dizininde bulamazsa, yükleme başarısız olur. Bu sorundan kaçınmak için bir yol, DLL 'yi yapı sürecinin bir parçası olarak istemci yürütülebilir dosyanızı içeren dizine kopyalamaktır. DLL 'yi kopyalamak için, derleme çıkış dizininize DLL 'yi kopyalayan bir komut eklemek üzere projenize **oluşturma sonrası bir olay** ekleyebilirsiniz. Burada belirtilen komut, yalnızca eksik veya değişmiş olması durumunda DLL 'yi kopyalar ve yapılandırmanıza yönelik doğru hata ayıklama veya sürüm konumlarına kopyalamak için makroları kullanır.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>Derleme sonrası bir olayda DLL 'yi kopyalamak için

1. **Özellik sayfaları** iletişim kutusunu açmak için **Çözüm Gezgini** 'teki **MathClient** düğümüne sağ tıklayın.

1. Yapılandırma açılan kutusunda, henüz seçili değilse **tüm yapılandırmalar** ' ı seçin.

1. Sol bölmede, **yapılandırma özellikleri** > **derleme olayları**altında **Derleme sonrası olay** ' ı seçin.

1. Özellik bölmesinde, **komut satırı** alanındaki düzenleme denetimini seçin ve ardından şu komutu girin:

   **Visual Studio 2019:**

   `xcopy /y /d "..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

    **Visual Studio 2017 ve öncesi:**

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   ![Oluşturma sonrası komutunu ekleyin](media/mathclient-post-build-command-line.png "Oluşturma sonrası komutunu ekleyin")

1. Değişikliklerinizi proje özelliklerine kaydetmek için **Tamam** düğmesini seçin.

Artık istemci uygulamanızda derlemek ve çalıştırmak için gereken her şey vardır. Menü çubuğunda Build**Build Solution** **öğesini seçerek** > uygulamayı oluşturun. Visual Studio 'daki **Çıkış** penceresinde, Visual Studio sürümünüze bağlı olarak aşağıdaki örneğe benzer bir örnek bulunmalıdır:

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>pch.cpp
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.pdb (Partial PDB)
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Tebrikler, DLL 'inizdeki işlevleri çağıran bir uygulama oluşturdunuz. Şimdi, ne yaptığını görmek için uygulamanızı çalıştırın. Menü çubuğunda hata ayıklama**başlatma hatası olmadan Başlat**' **ı seçin.**  >  Visual Studio programın içinde çalışması için bir komut penceresi açar. Çıktının son kısmı şöyle görünmelidir:

![İstemci uygulamasını hata ayıklama olmadan Başlat](media/mathclient-run-without-debugging.png "İstemci uygulamasını hata ayıklama olmadan Başlat")

Komut penceresini kapatmak için herhangi bir tuşa basın.

Artık bir DLL ve bir istemci uygulaması oluşturduğunuza göre, denemeler yapabilirsiniz. İstemci uygulamasının kodunda kesme noktalarını ayarlamayı deneyin ve uygulamayı hata ayıklayıcıda çalıştırın. Bir kitaplık çağrısına tıkladığınızda ne olacağını görün. Kitaplığa başka işlevler ekleyin veya DLL 'nizi kullanan başka bir istemci uygulaması yazın.

Uygulamanızı dağıtırken, kullandığı dll 'Leri de dağıtmanız gerekir. Oluşturduğunuz veya üçüncü taraflardan uygulamanıza sunulan dll 'Leri yapmanın en kolay yolu, uygulamayı uygulama *yerel dağıtımı*olarak da bilinen uygulamanızla aynı dizine yerleştirmelidir. Dağıtım hakkında daha fazla bilgi için bkz. [ C++Visual 'te dağıtım ](../windows/deployment-in-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Basic Uygulamalarından DLL İşlevleri Çağırma](calling-dll-functions-from-visual-basic-applications.md)
