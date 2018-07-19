---
title: 'İzlenecek yol: Oluşturma ve bir statik kitaplık (C++) kullanılarak | Microsoft Docs'
ms.custom: get-started-article
ms.date: 07/12/2018
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
ms.openlocfilehash: 1bcbf5747b667615c96ced3488e16f2a8fc0ef2d
ms.sourcegitcommit: 9ad287c88bdccee2747832659fe50c2e5d682a0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39034809"
---
# <a name="walkthrough-creating-and-using-a-static-library-c"></a>İzlenecek yol: Statik Kitaplık Oluşturma ve Kullanma (C++)
Bu adım adım kılavuzda, C++ uygulamaları ile kullanmak için bir statik kitaplık (.lib dosyası) oluşturma işlemini göstermektedir. Statik kitaplık kullanma, kodu yeniden kullanmak için harika bir yoludur. İşlevselliği gerektiren her uygulamada aynı yordamları tekrar uygulamak yerine bunları bir statik kitaplıkta bir kez yazın ve sonra bu uygulamalardan başvurun. Statik bir kitaplıktan bağlanan kod, uygulamanızın bir parçası olur — kodu kullanmak için başka bir dosya yüklemeniz gerekmez.  
  
 Bu izlenecek yol bu görevleri kapsar:  
  
-   [Statik kitaplık projesi oluşturma](#CreateLibProject)  
  
-   [Statik kitaplığa bir sınıf ekleme](#AddClassToLib)  
  
-   [Statik kitaplık başvurusu bir C++ konsol uygulaması oluşturma](#CreateAppToRefTheLib)  
  
-   [Uygulama içindeki statik kitaplıkta işlevselliği kullanarak](#UseLibInApp)  
  
-   [Uygulamayı çalıştırma](#RunApp)  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bir C++ dilinin temellerini anlama.  
  
##  <a name="CreateLibProject"></a> Statik kitaplık projesi oluşturma  
  
#### <a name="to-create-a-static-library-project"></a>Statik kitaplık projesi oluşturmak için  
  
1.  Menü çubuğunda, **dosya**, **yeni**, **proje**.  
  
2. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü, Visual C++** ve ardından **Windows Masaüstü**.
  
3. Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**.  
  
4.  Proje için bir ad belirleyin — Örneğin, **MathFuncsLib**— içinde **adı** kutusu. Çözüm için bir ad belirleyin — Örneğin, **StaticLibrary**— içinde **çözüm adı** kutusu. Seçin **Tamam** düğmesi.  
  
5. Altında **uygulama türü**, statik kitaplık (.lib) seçin.  
  
6. Altında **ek seçenekler**, işaretini kaldırın **önceden derlenmiş üst bilgi** onay kutusu.
  
7. Seçin **Tamam** projeyi oluşturmak için.  
 
##  <a name="AddClassToLib"></a> Statik kitaplığa bir sınıf ekleme  
  
#### <a name="to-add-a-class-to-the-static-library"></a>Statik kitaplığa bir sınıf eklemek için  
  
1.  Yeni bir sınıf için bir üstbilgi dosyası oluşturmak için kısayol menüsünü açın **MathFuncsLib** projesi **Çözüm Gezgini**ve ardından **Ekle**, **yeni öğe** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, sol bölmede altında **Visual C++** seçin **kod**. Orta bölmede seçin **üst bilgi dosyası (.h)**. Üstbilgi dosyası için bir ad belirtin — örneğin, **MathFuncsLib.h**— ve ardından **Ekle** düğmesi. Boş üstbilgi dosyası görüntülenir.  
  
2.  Adlı bir sınıf ekleyin **MyMathFuncs** toplama, çıkarma, çarpma ve bölme gibi genel matematik işlemlerini yapmak için. Kod buna benzemelidir:  
  
     [!code-cpp[NVC_Walkthrough_Create_Static_Lib#100](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_1.h)]  
  
3.  Yeni bir sınıf için bir kaynak dosyası oluşturmak için kısayol menüsünü açın **MathFuncsLib** projesi **Çözüm Gezgini**ve ardından **Ekle**, **yeni öğe** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, sol bölmede altında **Visual C++** seçin **kod**. Orta bölmede seçin **C++ dosyası (.cpp)**. Kaynak dosyası için bir ad belirleyin — Örneğin, **MathFuncsLib.cpp**— ve ardından **Ekle** düğmesi. Boş bir kaynak dosyası görüntülenir.  
  
4.  Bu kaynak dosyası için işlevselliği uygulamak için kullanmak **MyMathFuncs**. Kod buna benzemelidir:  
  
     [!code-cpp[NVC_Walkthrough_Create_Static_Lib#110](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_2.cpp)]  
  
5.  Seçerek statik kitaplığı derleyin **derleme**, **Çözümü Derle** menü çubuğundaki. Bu, diğer programlar tarafından kullanılabilen statik kitaplık oluşturur.  
  
    > [!NOTE]
    >  Visual Studio komut satırında oluşturduğunuzda, programı iki adımda oluşturmanız gerekir. İlk olarak, çalıştırma **cl /c/ehsc MathFuncsLib.cpp** Kodu derlemek ve adlı bir nesne dosyası oluşturmak için **MathFuncsLib.obj**. ( **Cl** komutu derleyiciyi, cl.exe'yi çalıştırır ve **/c** seçeneği derlemeyi bağlama olmadan belirtir. Daha fazla bilgi için [/c (derleme olmadan bağlamayı)](../build/reference/c-compile-without-linking.md).) İkinci olarak, çalıştırma **MathFuncsLib.obj lib** kodunu bağlamak ve statik kitaplık oluşturmak için **MathFuncsLib.lib**. ( **LIB** komutu Kitaplık Yöneticisi Lib.exe çağırır. Daha fazla bilgi için [LIB başvurusu](../build/reference/lib-reference.md).)  
  
##  <a name="CreateAppToRefTheLib"></a> Statik kitaplık başvurusu bir C++ konsol uygulaması oluşturma  
  
#### <a name="to-create-a-c-console-app-that-references-the-static-library"></a>Statik kitaplık başvurusu bir C++ konsol uygulaması oluşturmak için  
  
1.  Menü çubuğunda, **dosya**, **yeni**, **proje**.  
  
2. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü, Visual C++** ve ardından **Windows Masaüstü**.  

3. Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**.  
  
4.  Proje için bir ad belirleyin — Örneğin, **MyExecRefsLib**— içinde **adı** kutusu. Açılan liste yanındaki **çözüm**seçin **eklemek için çözüm**. Bu, statik kitaplık içeren çözüme yeni proje ekler. Seçin **Tamam** düğmesi.  
5. Altında **uygulama türü**seçin **konsol uygulaması (.exe)**.

6. Altında **Additioal seçenekleri**, işaretini kaldırın **önceden derlenmiş üst bilgi** onay kutusu.

7. Seçin **Tamam** projeyi oluşturmak için.  
  
##  <a name="UseLibInApp"></a> Uygulama içindeki statik kitaplıkta işlevselliği kullanarak  
  
#### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>Uygulama içindeki statik kitaplıkta işlevselliği kullanmak için  
  
1.  Bir konsol uygulaması oluşturduktan sonra boş bir program sizin için oluşturulur. Kaynak dosyasının adı daha önce seçtiğiniz adı ile aynıdır. Bu örnekte, adlı **myexecrefslib.cpp içeriği**.  
  
2.  Statik kitaplıkta matematik yordamlarını kullanmadan önce başvurmanız gerekir. Bunu yapmak için MyExecRefsLib projesi için kısayol menüsünü açın **Çözüm Gezgini**ve ardından **ekleyin, başvuru**.  
  
3.  **Başvuru Ekle** iletişim kutusu başvurabileceğiniz kitaplıkları listeler. **Projeleri** sekmesi projeleri çözüme ve içerdikleri tüm kitaplıkları listeler. Üzerinde **projeleri** sekmesinde **MathFuncsLib** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
4.  Başvuru **MathFuncsLib.h** üstbilgi dosyasına eklenen dizinlerin yolunu değiştirmeniz gerekir. İçinde **özellik sayfaları** iletişim kutusu için **MyExecRefsLib**, genişletin **yapılandırma özellikleri** düğümünü genişletin **C/C++** düğümünü ve ardından **genel**. Yanındaki **ek içerik dizinleri**, yolunu belirtin **MathFuncsLib** dizin veya onu gözatın.  
  
     Dizin yoluna göz atmak için özellik değeri açılan listesini açın ve ardından **Düzenle**. İçinde **ek içerik dizinleri** iletişim kutusunda, metin kutusuna, boş bir satır seçin ve ardından üç nokta düğmesini (**...** ) satırın sonunda. İçinde **dizini Seç** iletişim kutusunda seçin **MathFuncsLib** dizin seçip **klasörü seçin** seçiminizi kaydetmek ve iletişim kutusunu kapatmak için düğme. İçinde **ek içerik dizinleri** iletişim kutusunda **Tamam** düğmesini ve ardından **özellik sayfaları** iletişim kutusunda **Tamam**projeye yaptığınız değişiklikleri kaydetmek için düğme.  
  
5.  Artık **MyMathFuncs** bu uygulamada sınıfı. Bunu yapmak için içeriğini değiştirin **myexecrefslib.cpp içeriği** Bu kod ile:  
  
     [!code-cpp[NVC_Walkthrough_Create_Static_Lib#120](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_3.cpp)]  
  
6.  Yürütülebilir dosya seçerek yapı **derleme**, **Çözümü Derle** menü çubuğunda.  
  
##  <a name="RunApp"></a> Uygulamayı çalıştırma  
  
#### <a name="to-run-the-app"></a>Uygulamayı çalıştırmak için  
  
1.  Emin olun **MyExecRefsLib** için kısayol menüsünü açıp varsayılan proje olarak seçildiğinden **MyExecRefsLib** içinde **Çözüm Gezgini**ve ardından seçme **Başlangıç projesi olarak ayarla**.  
  
2.  Menü çubuğunda projeyi çalıştırmak için seçin **hata ayıklama**, **hata ayıklama olmadan Başlat**. Çıkış şuna benzemelidir:  
  
    ```Output  
    a + b = 106.4  
    a - b = -91.6  
    a * b = 732.6  
    a / b = 0.0747475  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Oluşturma ve kullanarak bir dinamik bağlantı kitaplığı (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)   
 [Masaüstü Uygulamaları (Visual C++)](../windows/desktop-applications-visual-cpp.md)
