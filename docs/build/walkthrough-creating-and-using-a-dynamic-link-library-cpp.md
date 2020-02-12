---
title: 'İzlenecek yol: kendi dinamik bağlantı kitaplığınızı oluşturma ve kullanma (C++)'
description: Visual C++ Studio 'Da bir Windows dinamik bağlantı KITAPLıĞı (dll) oluşturmak için kullanın.
ms.custom: conceptual
ms.date: 08/22/2019
helpviewer_keywords:
- libraries [C++], DLLs
- DLLs [C++], walkthroughs
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
ms.openlocfilehash: 37dc59dfb77af9fff240c0d44b21de84b17d073b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127848"
---
# <a name="walkthrough-create-and-use-your-own-dynamic-link-library-c"></a>İzlenecek yol: kendi dinamik bağlantı kitaplığınızı oluşturma ve kullanma (C++)

Bu adım adım izlenecek yol, Microsoft C++ 'ta (MSVC) yazılmış kendi dinamik bağlantı KITAPLıĞıNıZı (dll) oluşturmak Için VISUAL Studio IDE 'nin nasıl kullanılacağını gösterir. Daha sonra, başka bir C++ uygulamadan dll 'nin nasıl kullanılacağını gösterir. Dll 'Ler (UNIX tabanlı işletim sistemlerinde *paylaşılan kitaplıklar* olarak da bilinir), en kullanışlı Windows bileşenleri türlerinden biridir. Bunları kod ve kaynakları paylaşmak ve uygulamalarınızın boyutunu küçültmek için bir yöntem olarak kullanabilirsiniz. Dll 'Ler hatta uygulamalarınızı daha kolay hale getirmek ve genişletmek de kolaylaşır.

Bu izlenecek yolda, bazı matematik işlevlerini uygulayan bir DLL oluşturacaksınız. Ardından, DLL 'den işlevleri kullanan bir konsol uygulaması oluşturacaksınız. Ayrıca Windows dll 'Lerinde kullanılan bazı programlama tekniklerine ve kurallara bir giriş alırsınız.

Bu izlenecek yol aşağıdaki görevleri içerir:

- Visual Studio 'da bir DLL projesi oluşturun.

- DLL 'ye aktarılmış işlevler ve değişkenler ekleyin.

- Visual Studio 'da bir konsol uygulaması projesi oluşturun.

- Konsol uygulamasındaki DLL 'den içeri aktarılan işlevleri ve değişkenleri kullanın.

- Tamamlanmış uygulamayı çalıştırın.

Statik olarak bağlı bir kitaplık gibi, bir DLL değişkenleri, işlevleri ve kaynakları ada göre _dışa aktarır_ . İstemci uygulaması, bu değişkenleri, işlevleri ve kaynakları kullanmak için adları _içeri aktarır_ . Statik olarak bağlı bir kitaplığın aksine, Windows, uygulamanızda içeri aktarımları, yükleme zamanında veya çalışma zamanında bir DLL 'de dışarı aktarmalar için bağlantı zamanında bağlamak yerine, bir DLL 'ye bağlar. Windows, bu bağlantıları yapmak için standart C++ derleme modelinin parçası olmayan ek bilgiler gerektirir. MSVC derleyicisi, bu ek bilgileri sağlamak için Microsoft 'a C++ özgü bazı uzantılar uygular. Bu uzantıları gittiğimiz için açıkladık.

Bu izlenecek yol iki Visual Studio çözümü oluşturur; DLL 'yi ve istemci uygulamasını oluşturan birini oluşturan bir tane. DLL, C çağırma kuralını kullanır. Platform, çağırma kuralları ve bağlama kuralları eşleştiği sürece, diğer programlama dillerinde yazılmış uygulamalardan çağrılabilir. İstemci uygulaması, Windows 'un uygulamayı yükleme zamanında DLL 'ye bağladığı _örtük bağlama_kullanır. Bu bağlama, uygulamanın, statik olarak bağlanmış bir kitaplıktaki işlevleri gibi DLL tarafından sağlanan işlevleri çağırmasını sağlar.

Bu izlenecek yol bazı yaygın durumları kapsamaz. Kod, diğer programlama dilleri tarafından C++ dll 'lerin kullanımını göstermez. [Yalnızca kaynak dll](creating-a-resource-only-dll.md)'nin nasıl oluşturulacağını ya da çalışma zamanında DLL 'leri yükleme zamanında yüklemek için [Açık bağlamayı](linking-an-executable-to-a-dll.md#linking-explicitly) nasıl kullanacağınızı göstermez. Artık, MSVC ve Visual Studio 'Yu kullanarak tüm bunları yapabilirsiniz.

Dll 'Ler hakkında daha fazla bilgi için bkz. [Visual Studio 'DaC++ C/dll oluşturma](dlls-in-visual-cpp.md). Örtük bağlama ve açık bağlama hakkında daha fazla bilgi için, [Hangi bağlama yönteminin kullanılacağını belirleme](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)konusuna bakın. C-Language bağlantı C++ kurallarını kullanan programlama dilleri ile kullanmak üzere dll 'ler oluşturma hakkında bilgi için bkz. [c C++ Dili Çalıştırılabilirlerinde kullanmak için işlevleri dışarı aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md). .NET dilleri ile kullanmak üzere dll oluşturma hakkında daha fazla bilgi için, bkz. [Visual Basic UYGULAMALARıNDAN dll Işlevleri çağırma](calling-dll-functions-from-visual-basic-applications.md).

## <a name="prerequisites"></a>Prerequisites

- Microsoft Windows 7 veya sonraki sürümlerini çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10 ' un kullanılması önerilir.

::: moniker range=">=vs-2017"

- Visual Studio 'nun bir kopyası. Visual Studio 'Yu indirme ve yükleme hakkında daha fazla bilgi için bkz. [Visual Studio 'Yu yükleme](/visualstudio/install/install-visual-studio). Yükleyiciyi çalıştırdığınızda, iş yüküyle **masaüstü geliştirme C++**  ' nin işaretli olduğundan emin olun. Visual Studio 'Yu yüklerken bu iş yükünü yüklemediyseniz endişelenmeyin. Yükleyiciyi yeniden çalıştırabilir ve şimdi yükleyebilirsiniz.

   ![İle masaüstü geliştirmeC++](media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

::: moniker-end

::: moniker range="vs-2015"

- Visual Studio 'nun bir kopyası. Visual Studio 2015 ' i indirme ve yükleme hakkında daha fazla bilgi için bkz. [Visual studio 2015](/visualstudio/install/install-visual-studio-2015?view=vs-2015)' yi yükleme. Varsayılan olarak yüklenmediği için, C++ derleyici ve araçları yüklemek üzere özel bir yükleme kullanın.

::: moniker-end

- Visual Studio IDE kullanmanın temellerini anlama. Daha önce Windows Masaüstü uygulamaları kullandıysanız muhtemelen izleyebilirsiniz. Giriş için bkz. [Visual STUDIO IDE Özellik turu](/visualstudio/ide/visual-studio-ide).

- Üzerinde izlenecek C++ dilin temel sayısının yeterince anlaşılmasıdır. Endişelenmeyin, çok karmaşık bir şey yapmadık.

::: moniker range="vs-2017"

> [!NOTE]
> Bu izlenecek yol, Visual Studio 2017 sürüm 15,9 veya üstünü kullandığınızı varsayar. Visual Studio 2017 ' nin bazı önceki sürümlerinde kod şablonlarında hatalar vardı veya farklı kullanıcı arabirimi iletişimleri kullanılmaktadır. Sorunları önlemek için Visual Studio Yükleyicisi kullanarak Visual Studio 2017 sürümünü 15,9 veya üzeri bir sürüme güncelleştirin.

::: moniker-end

## <a name="create-the-dll-project"></a>DLL projesi oluşturma

Bu görev kümesinde, DLL 'niz için bir proje oluşturur, kod ekler ve derler. Başlamak için Visual Studio IDE 'yi başlatın ve gerekirse oturum açın. Yönergeler, kullandığınız Visual Studio sürümüne bağlı olarak biraz farklılık gösterir. Bu sayfanın sol üst kısmındaki denetimde doğru sürümün seçili olduğundan emin olun.

::: moniker range=">=vs-2019"

### <a name="to-create-a-dll-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de bir DLL projesi oluşturmak için

1. **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda **dosya** > **Yeni** > **Proje** ' yi seçin.

   ![Yeni bir DLL projesi oluştur](media/create-new-dll-project-2019.png "MathLibrary projesi oluşturma")

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **kitaplık**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **dinamik bağlantı kitaplığı (dll)** öğesini seçin ve ardından **İleri**' yi seçin.

1. **Yeni projenizi yapılandırın** sayfasında, proje için bir ad belirtmek üzere **Proje adı** kutusuna *MathLibrary* girin. Varsayılan **konum** ve **çözüm adı** değerlerini bırakın. **Yeni çözüm oluşturmak**için **çözüm** ayarlayın. Eğer işaretliyse **, çözümü ve projeyi aynı dizine yerleştir** seçeneğinin işaretini kaldırın.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

Çözüm oluşturulduğunda, Visual Studio 'da **Çözüm Gezgini** penceresinde oluşturulan proje ve kaynak dosyalarını görebilirsiniz.

![Visual Studio 'da oluşturulan çözüm](media/mathlibrary-solution-explorer-162.png "Visual Studio 'da oluşturulan çözüm")

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-dll-project-in-visual-studio-2017"></a>Visual Studio 2017 ' de bir DLL projesi oluşturmak için

1. **Yeni proje** iletişim kutusunu açmak için menü çubuğunda **dosya** > **Yeni** > **Proje** ' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** >  **C++ Visual** > **Windows Desktop**' ı seçin. Orta bölmede, **dinamik bağlantı kitaplığı (dll)** öğesini seçin. Proje için bir ad belirtmek üzere **ad** kutusuna *MathLibrary* girin. Varsayılan **konum** ve **çözüm adı** değerlerini bırakın. **Yeni çözüm oluşturmak**için **çözüm** ayarlayın. İşaretlenmezse **çözüm için dizin oluştur** ' a bakın.

   ![MathLibrary projesini adlandırın](media/mathlibrary-new-project-name-159.png "MathLibrary projesini adlandırın")

1. Projeyi oluşturmak için **Tamam** düğmesini seçin.

Çözüm oluşturulduğunda, Visual Studio 'da **Çözüm Gezgini** penceresinde oluşturulan proje ve kaynak dosyalarını görebilirsiniz.

![Visual Studio 'da oluşturulan çözüm](media/mathlibrary-solution-explorer-159.png "Visual Studio 'da oluşturulan çözüm")

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-dll-project-in-visual-studio-2015-and-older-versions"></a>Visual Studio 2015 ve eski sürümlerde bir DLL projesi oluşturmak için

1. Menü çubuğunda **dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** > **Şablonlar**' ı genişletin ve **görsel C++** ' i seçin ve ardından orta bölmedeki **Win32 konsol uygulaması**' nı seçin. Proje için bir ad belirtmek için **ad** düzenleme kutusuna *MathLibrary* girin. Varsayılan **konum** ve **çözüm adı** değerlerini bırakın. **Yeni çözüm oluşturmak**için **çözüm** ayarlayın. İşaretlenmezse **çözüm için dizin oluştur** ' a bakın.

   ![MathLibrary projesini adlandırın](media/mathlibrary-project-name.png "MathLibrary projesini adlandırın")

1. **Yeni proje** iletişim kutusunu kapatmak ve **Win32 uygulama Sihirbazı**' nı başlatmak için **Tamam** düğmesini seçin.

   ![Win32 uygulama Sihirbazına Genel Bakış](media/mathlibrary-project-wizard-1.png "Win32 uygulama Sihirbazına Genel Bakış")

1. **İleri** düğmesini seçin. **Uygulama ayarları** sayfasında, **uygulama türü**altında, **DLL**' yi seçin.

   ![Win32 uygulama Sihirbazı 'nda DLL oluşturma](media/mathlibrary-project-wizard-2.png "Win32 uygulama Sihirbazı 'nda DLL oluşturma")

1. Projeyi oluşturmak için **son** düğmesini seçin.

Sihirbaz çözümü tamamladığında, oluşturulan proje ve kaynak dosyaları Visual Studio 'da **Çözüm Gezgini** penceresinde görebilirsiniz.

![Visual Studio 'da oluşturulan çözüm](media/mathlibrary-solution-explorer-153.png "Visual Studio 'da oluşturulan çözüm")

::: moniker-end

Şu anda bu DLL çok fazla yapmaz. Daha sonra, DLL dışarı aktarmaların olduğu işlevleri bildirmek için bir üst bilgi dosyası oluşturacak ve ardından daha kullanışlı hale getirmek için işlev tanımlarını DLL 'ye eklersiniz.

### <a name="to-add-a-header-file-to-the-dll"></a>DLL 'ye bir üst bilgi dosyası eklemek için

1. İşlevleriniz için bir üst bilgi dosyası oluşturmak için, menü çubuğunda **proje** > **Yeni öğe Ekle**' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda, sol bölmede, **C++görsel**' i seçin. Orta bölmede **üst bilgi dosyası (. h)** öğesini seçin. Üst bilgi dosyasının adı olarak *MathLibrary. h* öğesini belirtin.

   ![Yeni öğe Ekle iletişim kutusunda üst bilgi ekle](media/mathlibrary-add-new-item-header-file.png "Yeni öğe Ekle iletişim kutusuna üstbilgi dosyası Ekle")

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

Bu üstbilgi dosyası, bir Genelleştirilmiş Fipriaccı sırası oluşturmak için bazı işlevleri bildirir ve bu iki başlangıç değeri verilir. `fibonacci_init(1, 1)` çağrısı tanıdık Fibonaccı numara sırasını oluşturur.

Dosyanın en üstündeki Önişlemci ifadelerine dikkat edin. Bir DLL projesi için yeni proje şablonu, tanımlanan Önişlemci makrolarına  **_ProjectName_&#95;dışarı aktarmalar** ekler. Bu örnekte, MathLibrary DLL projeniz oluşturulduğunda Visual Studio **&#95;MATHLIBRARY dışarı aktarmaları** tanımlar.

**MATHLIBRARY&#95;dışarı aktarma** makrosu tanımlandığında, **MATHLIBRARY&#95;API** makrosu işlev bildirimlerinde `__declspec(dllexport)` değiştiricisini ayarlar. Bu değiştirici, derleyiciye ve bağlayıcıya, DLL 'den diğer uygulamalar tarafından kullanılmak üzere bir işlev veya değişken dışarı aktarmayı söyler. **&#95;MATHLIBRARY dışarı aktarmalar** tanımsız olduğunda, örneğin, üstbilgi dosyası bir istemci uygulaması tarafından eklendiğinde, **&#95;MATHLIBRARY API 'si** bildirime `__declspec(dllimport)` değiştiricisini uygular. Bu değiştirici, bir uygulamadaki işlevin veya değişkenin içe aktarımını iyileştirir. Daha fazla bilgi için bkz. [dllexport, dllimport](../cpp/dllexport-dllimport.md).

### <a name="to-add-an-implementation-to-the-dll"></a>DLL 'ye bir uygulama eklemek için

::: moniker range=">=vs-2019"

1. **Çözüm Gezgini**, **kaynak dosyalar** düğümüne sağ tıklayın ve > **Yeni öğe** **Ekle** ' yi seçin. Önceki adımda yeni bir üst bilgi dosyası eklediğiniz şekilde *MathLibrary. cpp*adlı yeni bir. cpp dosyası oluşturun.

1. Düzenleyici penceresinde, zaten açıksa **MathLibrary. cpp** sekmesini seçin. Aksi takdirde, **Çözüm Gezgini**, açmak için **MathLibrary** projesinin **kaynak dosyaları** klasöründe **MathLibrary. cpp** öğesine çift tıklayın.

1. Düzenleyicide, MathLibrary. cpp dosyasının içeriğini aşağıdaki kodla değiştirin:

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "pch.h" // use stdafx.h in Visual Studio 2017 and earlier
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

::: moniker-end

::: moniker range="<=vs-2017"

1. Düzenleyici penceresinde, zaten açıksa **MathLibrary. cpp** sekmesini seçin. Aksi takdirde, **Çözüm Gezgini**, açmak için **MathLibrary** projesinin **kaynak dosyaları** klasöründe **MathLibrary. cpp** öğesine çift tıklayın.

1. Düzenleyicide, MathLibrary. cpp dosyasının içeriğini aşağıdaki kodla değiştirin:

   ```cpp
   // MathLibrary.cpp : Defines the exported functions for the DLL.
   #include "stdafx.h" // use pch.h in Visual Studio 2019 and later
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

::: moniker-end

Her şeyin şu ana kadar çalıştığını doğrulamak için dinamik bağlantı kitaplığını derleyin. Derlemek için, menü çubuğunda **build** > **Build Solution** öğesini seçin. DLL ve ilgili derleyici çıkışı, doğrudan çözüm klasörünün altında *hata ayıklama* adlı bir klasöre yerleştirilir. Yayın derlemesi oluşturursanız, çıktı *yayın*adlı bir klasöre yerleştirilir. Çıktı aşağıdakine benzer görünmelidir:

::: moniker range=">=vs-2019"

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>pch.cpp
1>dllmain.cpp
1>MathLibrary.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

::: moniker-end

::: moniker range="vs-2017"

```Output
1>------ Build started: Project: MathLibrary, Configuration: Debug Win32 ------
1>stdafx.cpp
1>dllmain.cpp
1>MathLibrary.cpp
1>Generating Code...
1>   Creating library C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.lib and object C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.exp
1>MathLibrary.vcxproj -> C:\Users\username\Source\Repos\MathLibrary\Debug\MathLibrary.dll
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

::: moniker-end

::: moniker range="vs-2015"

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

::: moniker-end

Tebrikler, Visual Studio 'Yu kullanarak bir DLL oluşturdunuz! Ardından, DLL tarafından dışarıya aktarılmış işlevleri kullanan bir istemci uygulaması oluşturacaksınız.

## <a name="create-a-client-app-that-uses-the-dll"></a>DLL 'yi kullanan bir istemci uygulaması oluşturma

Bir DLL oluştururken, istemci uygulamalarının bunu nasıl kullanabileceği hakkında düşünün. İşlevleri çağırmak veya DLL tarafından dışarıya alınan verilere erişmek için, istemci kaynak kodunun derleme zamanında kullanılabilir bildirimlere sahip olması gerekir. Bağlantı zamanında bağlayıcı, işlev çağrılarını veya veri erişimlerini çözümlemek için bilgi gerektirir. DLL, bu bilgileri bir *içeri aktarma kitaplığında*sağlar ve gerçek kod yerine işlevleri ve verileri bulma hakkında bilgi içeren bir dosyadır. Çalışma zamanında DLL, işletim sisteminin bulabileceği bir konumda istemci için kullanılabilir olmalıdır.

Kendi kendinize veya üçüncü tarafınızdan bağımsız olarak, istemci uygulama projenizin bir DLL kullanmak için çeşitli bilgi parçaları olması gerekir. DLL dışarı aktarmaları, bağlayıcının içeri aktarma kitaplıklarını ve DLL 'nin kendisini belirten üst bilgileri bulması gerekir. Bir çözüm, tüm bu dosyaları istemci projenize kopyalamadır. İstemciniz geliştirirken değişmemiş olan üçüncü taraf dll 'Ler için, bu yöntem bunları kullanmanın en iyi yolu olabilir. Ancak, DLL 'yi de oluşturduğunuzda çoğaltmaktan kaçınmak daha iyidir. Geliştirme kapsamında olan DLL dosyalarının yerel bir kopyasını yaparsanız, yanlışlıkla bir kopyada bir başlık dosyasını değiştirebilir veya bir güncel olmayan kitaplık kullanamazsınız.

Eşitleme dışı koddan kaçınmak için, istemci projenizdeki ekleme yolunu dll başlık dosyalarını doğrudan DLL projenizden içerecek şekilde ayarlamanızı öneririz. Ayrıca, DLL projesinden DLL içeri aktarma kitaplıklarını dahil etmek için istemci projenizdeki kitaplık yolunu ayarlayın. Son olarak, DLL projesinden oluşturulan DLL 'yi istemci derleme çıkış dizinine kopyalayın. Bu adım, istemci uygulamanızın oluşturduğunuz DLL kodunu kullanmasını sağlar.

::: moniker range=">=vs-2019"

### <a name="to-create-a-client-app-in-visual-studio"></a>Visual Studio 'da bir istemci uygulaması oluşturmak için

1. **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda **dosya** > **Yeni** > **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri**' yi seçin.

1. **Yeni projenizi yapılandırın** sayfasında, proje için bir ad belirtmek üzere **Proje adı** kutusuna *MathClient* girin. Varsayılan **konum** ve **çözüm adı** değerlerini bırakın. **Yeni çözüm oluşturmak**için **çözüm** ayarlayın. Eğer işaretliyse **, çözümü ve projeyi aynı dizine yerleştir** seçeneğinin işaretini kaldırın.

   ![İstemci projesini adlandırın](media/mathclient-project-name-2019.png "İstemci projesini adlandırın")

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin.

Sizin için en az bir konsol uygulama projesi oluşturulur. Ana kaynak dosyanın adı, daha önce girdiğiniz proje adıyla aynıdır. Bu örnekte, **MathClient. cpp**olarak adlandırılmıştır. Onu oluşturabilirsiniz, ancak henüz DLL 'nizi kullanmaz.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-client-app-in-visual-studio-2017"></a>Visual Studio 2017 ' de bir istemci uygulaması oluşturmak için

1. Oluşturduğunuz DLL 'yi C++ kullanan bir uygulama oluşturmak için, menü çubuğunda **dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** > **C++Visual**altında **Windows Masaüstü** ' nü seçin. Orta bölmede **Windows konsol uygulaması**' nı seçin. *MathClient*adlı projenin adını **ad** düzenleme kutusunda belirtin.  Varsayılan **konum** ve **çözüm adı** değerlerini bırakın. **Yeni çözüm oluşturmak**için **çözüm** ayarlayın. İşaretlenmezse **çözüm için dizin oluştur** ' a bakın.

   ![İstemci projesini adlandırın](media/mathclient-new-project-name-159.png "İstemci projesini adlandırın")

1. İstemci uygulama projesini oluşturmak için **Tamam ' ı** seçin.

Sizin için en az bir konsol uygulama projesi oluşturulur. Ana kaynak dosyanın adı, daha önce girdiğiniz proje adıyla aynıdır. Bu örnekte, **MathClient. cpp**olarak adlandırılmıştır. Onu oluşturabilirsiniz, ancak henüz DLL 'nizi kullanmaz.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-client-app-in-visual-studio-2015"></a>Visual Studio 2015 ' de bir istemci uygulaması oluşturmak için

1. Oluşturduğunuz DLL 'yi C++ kullanan bir uygulama oluşturmak için, menü çubuğunda **dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** > **Şablonlar** ' ın altında, **Visual C++**  > **Win32** ' i seçin. Orta bölmede **Win32 konsol uygulaması**' nı seçin. *MathClient*adlı projenin adını **ad** düzenleme kutusunda belirtin. Varsayılan **konum** ve **çözüm adı** değerlerini bırakın. **Yeni çözüm oluşturmak**için **çözüm** ayarlayın. İşaretlenmezse **çözüm için dizin oluştur** ' a bakın.

   ![İstemci projesini adlandırın](media/mathclient-project-name.png "İstemci projesini adlandırın")

1. **Yeni proje** iletişim kutusunu kapatmak ve **Win32 uygulama Sihirbazı**' nı başlatmak için **Tamam** düğmesini seçin. **Win32 uygulama Sihirbazı** Iletişim kutusunun **genel bakış** sayfasında **İleri** düğmesini seçin.

1. **Uygulama ayarları** sayfasında, **uygulama türü**altında, henüz seçili değilse **konsol uygulaması** ' nı seçin.

1. Projeyi oluşturmak için **son** düğmesini seçin.

Sihirbaz tamamlandığında, sizin için en az bir konsol uygulaması projesi oluşturulur. Ana kaynak dosyanın adı, daha önce girdiğiniz proje adıyla aynıdır. Bu örnekte, **MathClient. cpp**olarak adlandırılmıştır. Onu oluşturabilirsiniz, ancak henüz DLL 'nizi kullanmaz.

::: moniker-end

Sonra, kaynak kodunuzda MathLibrary işlevlerini çağırmak için projenizin *MathLibrary. h* dosyasını içermesi gerekir. Bu üst bilgi dosyasını istemci uygulama projenize kopyalayabilir, ardından projeye varolan bir öğe olarak ekleyebilirsiniz. Bu yöntem, üçüncü taraf kitaplıklar için iyi bir seçenek olabilir. Ancak, DLL 'niz ve istemciniz için aynı anda kod üzerinde çalışıyorsanız, üst bilgi dosyaları eşitlenmemiş olabilir. Bu sorundan kaçınmak için, projenizdeki **ek Içerme dizinleri** yolunu, özgün üst bilginin yolunu içerecek şekilde ayarlayın.

### <a name="to-add-the-dll-header-to-your-include-path"></a>DLL üst bilgisini ekleme yolunuza eklemek için

1. **Özellik sayfaları** iletişim kutusunu açmak için **Çözüm Gezgini** 'teki **MathClient** düğümüne sağ tıklayın.

1. **Yapılandırma** açılan kutusunda, henüz seçili değilse **tüm yapılandırmalar** ' ı seçin.

1. Sol bölmede, **yapılandırma özellikleri** > **C/C++**  > **genel**' i seçin.

1. Özellik bölmesinde, **Ek ekleme dizinleri** düzenleme kutusunun yanındaki açılan denetimi seçin ve ardından **Düzenle**' yi seçin.

   ![Ek Içerme dizinleri özelliğini Düzenle](media/mathclient-additional-include-directories-property.png "Ek Içerme dizinleri özelliğini Düzenle")

1. Bir düzenleme denetimini etkinleştirmek için **Ek ekleme dizinleri** iletişim kutusunun üst bölmesine çift tıklayın. Ya da yeni bir giriş oluşturmak için klasör simgesini seçin.

1. Düzenleme denetiminde, **MathLibrary. h** üstbilgi dosyasının konumunun yolunu belirtin. Doğru klasöre gözatabileceğiniz üç nokta ( **...** ) denetimini seçebilirsiniz.

   Ayrıca, istemci kaynak dosyalarından DLL üstbilgi dosyalarını içeren klasöre göreli bir yol girebilirsiniz. İstemci projenizi DLL 'den ayrı bir çözüme yerleştirme yönergelerini izlediyseniz, göreli yol şuna benzemelidir:

   `..\..\MathLibrary\MathLibrary`

   DLL 'niz ve istemci projeleriniz aynı çözümde ise, göreli yol şöyle görünebilir:

   `..\MathLibrary`

   DLL ve istemci projeleri başka klasörlerde olduğunda göreli yolu eşleşecek şekilde ayarlayın. İsterseniz, klasöre gitmek için üç nokta denetimini de kullanabilirsiniz.

   ![Üstbilgi konumunu ek ekleme dizinleri özelliğine ekleyin](media/mathclient-additional-include-directories.png "Üstbilgi konumunu ek ekleme dizinleri özelliğine ekleyin")

1. **Ek dizinleri Ekle** iletişim kutusunda üstbilgi dosyasının yolunu girdikten sonra **Tamam** düğmesini seçin. **Özellik sayfaları** iletişim kutusunda, değişikliklerinizi kaydetmek için **Tamam** düğmesini seçin.

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

Bu kod derlenebilir, ancak bağlanamaz. İstemci uygulamasını şimdi oluşturursanız, hata listesi bazı LNK2019 hataları gösterir. Bunun nedeni, projenizde bazı bilgilerin eksik olması gerekir: projenizin *MathLibrary. lib* kitaplığı 'nda henüz bir bağımlılığı olduğunu belirtmediniz. Ve bağlayıcı, *MathLibrary. lib* dosyasının nasıl bulunacağını söylamadınız.

Bu sorunu onarmak için kitaplık dosyasını doğrudan istemci uygulama projenize kopyalayabilirsiniz. Bağlayıcı, otomatik olarak bulup kullanacaktır. Ancak, hem kitaplık hem de istemci uygulaması geliştirme aşamasındadır ve bu, diğeri de görünmeyen bir kopyada değişikliklere yol açabilir. Bu sorundan kaçınmak için, derleme sistemine projenizin *MathLibrary. lib*öğesine bağlı olduğunu bildirmek üzere **ek bağımlılıklar** özelliğini ayarlayabilirsiniz. Ve, bağlandığınızda orijinal kitaplığın yolunu dahil etmek için projenizde **ek bir kitaplık dizinleri** yolu ayarlayabilirsiniz.

### <a name="to-add-the-dll-import-library-to-your-project"></a>DLL içeri aktarma kitaplığını projenize eklemek için

1. **Çözüm Gezgini** ' deki **MathClient** düğümüne sağ tıklayın ve **Özellikler** ' i seçerek **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma** açılan kutusunda, henüz seçili değilse **tüm yapılandırmalar** ' ı seçin. Tüm özellik değişikliklerinin hem hata ayıklama hem de yayın yapılarına uygulanmasını sağlar.

1. Sol bölmede, > **bağlayıcı** > **yapılandırma özellikleri** ' ni seçin. Özellik bölmesinde, **ek bağımlılıklar** düzenleme kutusunun yanındaki açılan denetimi seçin ve ardından **Düzenle**' yi seçin.

   ![Ek Bağımlılıklar özelliğini Düzenle](media/mathclient-additional-dependencies-property.png "Ek Bağımlılıklar özelliğini Düzenle")

1. **Ek bağımlılıklar** iletişim kutusunda, *MathLibrary. lib* ' i en üstteki düzenleme denetimindeki listeye ekleyin.

   ![Kitaplık bağımlılığını ekleyin](media/mathclient-additional-dependencies.png "Kitaplık bağımlılığını ekleyin")

1. **Özellik sayfaları** iletişim kutusuna geri dönmek için **Tamam ' ı** seçin.

1. Sol bölmede, **genel** > **bağlayıcı** > **yapılandırma özellikleri** ' ni seçin. Özellik bölmesinde, **Ek kitaplık dizinleri** düzenleme kutusunun yanındaki açılan denetimi seçin ve ardından **Düzenle**' yi seçin.

   ![Ek kitaplık dizinleri özelliğini Düzenle](media/mathclient-additional-library-directories-property.png "Ek kitaplık dizinleri özelliğini Düzenle")

1. Bir düzenleme denetimini etkinleştirmek için **Ek kitaplık dizinleri** iletişim kutusunun üst bölmesine çift tıklayın. Düzenleme denetiminde, **MathLibrary. lib** dosyasının konumunun yolunu belirtin. Varsayılan olarak, doğrudan DLL çözüm klasörünün altında *Hata Ayıkla* adlı bir klasörde yer alabilir. Yayın derlemesi oluşturursanız, dosya *yayın*adlı bir klasöre yerleştirilir. `$(IntDir)` makrosunu, hangi tür bir derleme oluşturduğunuz bağımsız olarak bağlayıcının DLL 'nizi bulabilmesi için kullanabilirsiniz. İstemci projenizi DLL projesinden ayrı bir çözüme koymak için yönergeleri izlediyseniz, göreli yol şuna benzemelidir:

   `..\..\MathLibrary\$(IntDir)`

   DLL 'niz ve istemci projeleriniz diğer konumlardayken, göreli yolu eşleşecek şekilde ayarlayın.

   ![Kitaplık dizinini ekleme](media/mathclient-additional-library-directories.png "Kitaplık dizinini ekleme")

1. Kitaplık dosyasının yolunu **Ek kitaplık dizinleri** iletişim kutusunda girdikten sonra, **Özellik sayfaları** iletişim kutusuna geri dönmek için **Tamam** düğmesini seçin. Özellik değişikliklerini kaydetmek için **Tamam ' ı** seçin.

İstemci uygulamanız artık başarıyla derleyip bağlantı oluşturabilir, ancak çalışması gereken her şeyi de yok. İşletim sistemi uygulamanızı yüklediğinde, MathLibrary DLL 'sini arar. DLL 'yi belirli sistem dizinlerinde, ortam yolunda veya yerel uygulama dizininde bulamazsa, yükleme başarısız olur. İşletim sistemine bağlı olarak şöyle bir hata iletisi görürsünüz:

![MathLibrary DLL bulunamadı hatası](media/mathclient-system-error-mathlibrary-dll-not-found.png "MathLibrary DLL bulunamadı hatası")

Bu sorundan kaçınmak için bir yol, DLL 'yi yapı sürecinin bir parçası olarak istemci yürütülebilir dosyanızı içeren dizine kopyalamaktır. Derleme çıkış dizininize DLL 'yi kopyalayan bir komut eklemek için projenize **oluşturma sonrası bir olay** ekleyebilirsiniz. Burada belirtilen komut, yalnızca eksikse veya değiştiyse DLL 'yi kopyalar. Derleme yapılandırmanıza bağlı olarak hata ayıklama veya sürüm konumlarına kopyalamak için makroları kullanır.

### <a name="to-copy-the-dll-in-a-post-build-event"></a>Derleme sonrası bir olayda DLL 'yi kopyalamak için

1. **Çözüm Gezgini** ' deki **MathClient** düğümüne sağ tıklayın ve **Özellikler** ' i seçerek **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma** açılan kutusunda, henüz seçili değilse **tüm yapılandırmalar** ' ı seçin.

1. Sol bölmede, **Derleme sonrası olay** > **derleme olaylarını** > **yapılandırma özellikleri** ' ni seçin.

1. Özellik bölmesinde, **komut satırı** alanındaki düzenleme denetimini seçin. İstemci projenizi DLL projesinden ayrı bir çözüme koymak için yönergeleri izlediyseniz, şu komutu girin:

   `xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"`

   DLL 'niz ve istemci projeleriniz diğer dizinlerde ise, eşleşecek şekilde DLL 'ye göreli yolu değiştirin.

   ![Oluşturma sonrası komutunu ekleyin](media/mathclient-post-build-command-line.png "Oluşturma sonrası komutunu ekleyin")

1. Değişikliklerinizi proje özelliklerine kaydetmek için **Tamam** düğmesini seçin.

Artık istemci uygulamanızda derlemek ve çalıştırmak için gereken her şey vardır. Menü çubuğunda **build** > **Build Solution** öğesini seçerek uygulamayı oluşturun. Visual Studio 'daki **Çıkış** penceresinde, Visual Studio sürümünüze bağlı olarak aşağıdaki örneğe benzer bir örnek bulunmalıdır:

```Output
1>------ Build started: Project: MathClient, Configuration: Debug Win32 ------
1>MathClient.cpp
1>MathClient.vcxproj -> C:\Users\username\Source\Repos\MathClient\Debug\MathClient.exe
1>1 File(s) copied
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Tebrikler, DLL 'inizdeki işlevleri çağıran bir uygulama oluşturdunuz. Şimdi, ne yaptığını görmek için uygulamanızı çalıştırın. Menü çubuğunda Hata **ayıkla** > hata **ayıklama olmadan Başlat**' ı seçin. Visual Studio programın içinde çalışması için bir komut penceresi açar. Çıktının son kısmı şöyle görünmelidir:

![İstemci uygulamasını hata ayıklama olmadan Başlat](media/mathclient-run-without-debugging.png "İstemci uygulamasını hata ayıklama olmadan Başlat")

Komut penceresini kapatmak için herhangi bir tuşa basın.

Artık bir DLL ve bir istemci uygulaması oluşturduğunuza göre, denemeler yapabilirsiniz. İstemci uygulamasının kodunda kesme noktalarını ayarlamayı deneyin ve uygulamayı hata ayıklayıcıda çalıştırın. Bir kitaplık çağrısına tıkladığınızda ne olacağını görün. Kitaplığa başka işlevler ekleyin veya DLL 'nizi kullanan başka bir istemci uygulaması yazın.

Uygulamanızı dağıtırken, kullandığı dll 'Leri de dağıtmanız gerekir. Oluşturduğunuz veya üçüncü taraflardan dahil ettiğiniz dll 'Leri yapmanın en kolay yolu, bunları uygulamanızla aynı dizine yerleştirmelidir. *Uygulama yerel dağıtımı*olarak bilinir. Dağıtım hakkında daha fazla bilgi için bkz. [ C++Visual 'te dağıtım ](../windows/deployment-in-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Basic Uygulamalarından DLL İşlevleri Çağırma](calling-dll-functions-from-visual-basic-applications.md)
