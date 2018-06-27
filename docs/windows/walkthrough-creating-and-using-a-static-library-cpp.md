---
title: 'İzlenecek yol: Oluşturma ve bir statik kitaplık (C++) kullanılarak | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d136dae553f623cbd607a69ab710fa9c6fe6c91b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891587"
---
# <a name="walkthrough-creating-and-using-a-static-library-c"></a>İzlenecek yol: Statik Kitaplık Oluşturma ve Kullanma (C++)
Bu adım adım, C++ uygulamaları ile kullanmak için bir statik kitaplık (.lib dosyası) oluşturulacağını gösterir. Statik bir kitaplık kullanılarak kodunu yeniden için harika bir yoludur. Aynı yordamlar işlevselliği gerektiren her uygulama, yeniden uygulamak, yerine bunları bir kez statik kitaplığa yazar ve uygulamalardan başvuru. Statik bir kitaplıktan bağlı kodunu uygulamanızı bir parçası olur — kodu kullanmak için başka bir dosyaya yüklemeniz gerekmez.  
  
 Bu kılavuzda, bu görevleri içerir:  
  
-   [Bir statik kitaplık projesi oluşturma](#BKMK_CreateLibProject)  
  
-   [Statik kitaplığa sınıf ekleme](#BKMK_AddClassToLib)  
  
-   [Statik kitaplık başvuran bir C++ konsol uygulaması oluşturma](#BKMK_CreateAppToRefTheLib)  
  
-   [Uygulamasında statik kitaplığından işlevlerini kullanma](#BKMK_UseLibInApp)  
  
-   [Uygulamayı çalıştırma](#BKMK_RunApp)  
  
## <a name="prerequisites"></a>Önkoşullar  
 C++ dil temelleri anlayış.  
  
##  <a name="BKMK_CreateLibProject"></a> Bir statik kitaplık projesi oluşturma  
  
#### <a name="to-create-a-static-library-project"></a>Bir statik kitaplık projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  Sol bölmesinde **yeni proje** iletişim kutusunda, genişletin **yüklü**, **şablonları**, **Visual C++** ve ardından  **Win32**.  
  
3.  Orta bölmede seçin **Win32 konsol uygulaması**.  
  
4.  Proje için bir ad belirtin — örneğin, **MathFuncsLib**— içinde **adı** kutusu. Çözüm için bir ad belirtin — örneğin, **StaticLibrary**— içinde **çözüm adı** kutusu. Seçin **Tamam** düğmesi.  
  
5.  Üzerinde **genel bakış** sayfasında **Win32 Uygulama Sihirbazı'nı** iletişim kutusunda, seçin **sonraki** düğmesi.  
  
6.  Üzerinde **uygulama ayarları** sayfasında **uygulama türü**seçin **statik kitaplık.**  
  
7.  Üzerinde **uygulama ayarları** sayfasında **ek seçenekler**, Temizle **önceden derlenmiş üstbilgi** onay kutusu.  
  
8.  Seçin **son** projesi oluşturmak için düğmesi.  
  
##  <a name="BKMK_AddClassToLib"></a> Statik kitaplığa sınıf ekleme  
  
#### <a name="to-add-a-class-to-the-static-library"></a>Bir sınıf statik kitaplığa eklemek için  
  
1.  Yeni bir sınıf için bir üstbilgi dosyası oluşturmak için kısayol menüsünü açın **MathFuncsLib** proje **Çözüm Gezgini**ve ardından **Ekle**, **yeni öğe** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, sol bölmede altında **Visual C++** seçin **kod**. Orta bölmede seçin **üstbilgi dosyası (.h)**. Üstbilgi dosyası için bir ad belirtin — örneğin, **MathFuncsLib.h**— ve ardından **Ekle** düğmesi. Boş üstbilgi dosyası görüntülenir.  
  
2.  Adlı bir sınıf ekleyin **MyMathFuncs** toplama ve çıkarma, çarpma ve bölme gibi ortak matematiksel işlemleri yapmak için. Kod şuna benzemelidir:  
  
     [!code-cpp[NVC_Walkthrough_Create_Static_Lib#100](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_1.h)]  
  
3.  Yeni sınıf için bir kaynak dosyası oluşturmak için kısayol menüsünü açın **MathFuncsLib** proje **Çözüm Gezgini**ve ardından **Ekle**, **yeni öğe** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, sol bölmede altında **Visual C++** seçin **kod**. Orta bölmede seçin **C++ dosyasına (.cpp)**. Kaynak dosya için bir ad belirtin — örneğin, **MathFuncsLib.cpp**— ve ardından **Ekle** düğmesi. Boş kaynak dosyası görüntülenir.  
  
4.  İşlemin işlevselliği uygulamak için bu kaynak dosyasını kullanın **MyMathFuncs**. Kod şuna benzemelidir:  
  
     [!code-cpp[NVC_Walkthrough_Create_Static_Lib#110](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_2.cpp)]  
  
5.  Statik kitaplık seçerek derleme **yapı**, **yapı çözümü** menü çubuğunda. Bu, diğer programları tarafından kullanılan bir statik kitaplık oluşturur.  
  
    > [!NOTE]
    >  Visual Studio komut satırında yapılandırdığınızda, programın iki adımda yapılandırmanız gerekir. Öncelikle çalıştırın **cl /c /EHsc MathFuncsLib.cpp** Kodu derlemek ve adlı bir nesne dosyası oluşturmak için **MathFuncsLib.obj**. ( **Cl** komutu çalıştırır Cl.exe, derleyici ve **/c** seçeneği bağlantılandırmadan derleme belirtir. Daha fazla bilgi için bkz: [/c (derleme olmadan bağlama)](../build/reference/c-compile-without-linking.md).) İkinci olarak, çalıştırmak **MathFuncsLib.obj lib** kodu bağlayın ve statik kitaplık oluşturma için **MathFuncsLib.lib**. ( **Lib** komutu Kitaplığı Yöneticisi ' ni Lib.exe çağırır. Daha fazla bilgi için bkz: [LIB başvurusu](../build/reference/lib-reference.md).)  
  
##  <a name="BKMK_CreateAppToRefTheLib"></a> Statik kitaplık başvuran bir C++ konsol uygulaması oluşturma  
  
#### <a name="to-create-a-c-console-app-that-references-the-static-library"></a>Statik kitaplık başvuruda bulunan bir C++ konsol uygulaması oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  Sol bölmede altında **Visual C++** seçin **Win32**.  
  
3.  Orta bölmede seçin **Win32 konsol uygulaması**.  
  
4.  Proje için bir ad belirtin — örneğin, **MyExecRefsLib**— içinde **adı** kutusu. Açılan listeden sonraki **çözüm**seçin **eklemek için çözüm**. Bu statik kitaplık içeren çözüme yeni proje ekler. Seçin **Tamam** düğmesi.  
  
5.  Üzerinde **genel bakış** sayfasında **Win32 Uygulama Sihirbazı'nı** iletişim kutusunda, seçin **sonraki** düğmesi.  
  
6.  Üzerinde **uygulama ayarları** sayfasında **uygulama türü**seçin **konsol uygulaması**.  
  
7.  Üzerinde **uygulama ayarları** sayfasında **ek seçenekler**, Temizle **önceden derlenmiş üstbilgi** onay kutusu.  
  
8.  Seçin **son** projesi oluşturmak için düğmesi.  
  
##  <a name="BKMK_UseLibInApp"></a> Uygulamasında statik kitaplığından işlevlerini kullanma  
  
#### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>Uygulamanın statik kitaplığa işlevselliği kullanmak için  
  
1.  Bir konsol uygulaması oluşturduktan sonra boş bir program sizin için oluşturulur. Kaynak dosyasının adı daha önce seçtiğiniz ad ile aynıdır. Bu örnekte adlı **MyExecRefsLib.cpp**.  
  
2.  Statik kitaplıkta matematik yordamları kullanmadan önce başvurmalıdır. Bunu yapmak için kısayol menüsünü açın **MyExecRefsLib** proje **Çözüm Gezgini**ve ardından **başvurular**. İçinde **MyExecRefsLibProperty sayfaları** iletişim kutusunda, genişletin **ortak özellikleri** düğümü, select **Framework ve başvuruları**ve ardından **Ekle Yeni başvuru** düğmesi. Hakkında daha fazla bilgi için **başvuruları** iletişim kutusu, bkz: [başvuruları ekleme](../ide/adding-references-in-visual-cpp-projects.md).  
  
3.  **Başvuru Ekle** iletişim kutusu başvurusu yapabilir kitaplıkları listeler. **Projeleri** sekmesini projeleri geçerli çözümü ve içerdikleri tüm kitaplıkları listeler. Üzerinde **projeleri** sekmesine **MathFuncsLib** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
4.  Başvuru **MathFuncsLib.h** üst bilgi dosyasını dahil dizinleri yolu değiştirmeniz gerekir. İçinde **özellik sayfaları** iletişim kutusu için **MyExecRefsLib**, genişletin **yapılandırma özellikleri** düğümü genişletin **C/C++** düğümünü ve ardından **genel**. Yanına **ek içeren dizinler**, yolunu belirtin **MathFuncsLib** dizini ya da onu gözatın.  
  
     Dizin yolu için göz atmak için özellik değeri açılır listesini açın ve ardından **Düzenle**. İçinde **ek içeren dizinler** iletişim kutusunda, metin kutusunda, boş bir satırı seçin ve ardından üç nokta düğmesini (**...** ) satırın sonundaki. İçinde **Dizin Seç** iletişim kutusunda **MathFuncsLib** dizin ve ardından **klasörü seçin** düğmesine seçiminizi kaydetmek ve iletişim kutusunu kapatın. İçinde **ek içeren dizinler** iletişim kutusunda, seçin **Tamam** düğmesine ve ardından **özellik sayfaları** iletişim kutusunda, seçin **Tamam**projeye yaptığınız değişiklikleri kaydetmek için düğmesi.  
  
5.  Artık kullanabilirsiniz **MyMathFuncs** Bu uygulamadaki sınıfı. Bunu yapmak için içeriğini değiştirmek **MyExecRefsLib.cpp** Bu kod:  
  
     [!code-cpp[NVC_Walkthrough_Create_Static_Lib#120](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_3.cpp)]  
  
6.  Yürütülebilir dosya seçerek yapı **yapı**, **yapı çözümü** menü çubuğunda.  
  
##  <a name="BKMK_RunApp"></a> Uygulamayı çalıştırma  
  
#### <a name="to-run-the-app"></a>Uygulamayı çalıştırmak için  
  
1.  Olduğundan emin olun **MyExecRefsLib** için kısayol menüsünü açarak varsayılan proje seçilir **MyExecRefsLib** içinde **Çözüm Gezgini**ve ardından seçme **Başlangıç projesi olarak ayarla**.  
  
2.  Menü çubuğunda proje çalıştırmak için tercih **hata ayıklama**, **hata ayıklama olmadan Başlat**. Çıkış şuna benzemelidir:  
  
    ```Output  
    a + b = 106.4  
    a - b = -91.6  
    a * b = 732.6  
    a / b = 0.0747475  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Oluşturma ve dinamik bağlantı kitaplığı (C++) kullanma](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)   
 [Masaüstü Uygulamaları (Visual C++)](../windows/desktop-applications-visual-cpp.md)