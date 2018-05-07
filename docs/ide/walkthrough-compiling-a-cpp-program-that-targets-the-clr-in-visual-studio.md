---
title: CLR'yi hedefleyen C++ programını derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2a7bcb0eead62730f0b70b0b1df64e5ed08f1f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>İzlenecek Yol: Visual Studio'da CLR'yi Hedefleyen C++ Programını Derleme
Visual Studio geliştirme ortamı kullanarak derlemek ve .NET sınıfları kullanan Visual C++ programları oluşturabilirsiniz.  
  
 Bu yordam için kendi Visual C++ programı yazın ya da örnek programlar birini kullanın. Bu yordamda kullanırız örnek program textfile.txt adlı bir metin dosyası oluşturur ve proje dizinine kaydeder.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu konular, C++ dili ile ilgili temel bilgileri anladığınızdan varsayalım.  
  
### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>Visual Studio'da yeni proje oluşturma ve yeni bir kaynak dosya eklemek için  
  
1.  Yeni bir proje oluşturun. Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
2.  Visual C++ proje türlerinden tıklatın **CLR**ve ardından **CLR boş proje**.  
  
3.  Bir proje adı yazın.  
  
     Varsayılan olarak, projeyi içeren çözümü yeni proje aynı ada sahip, ancak farklı bir ad girin. İsterseniz, proje için farklı bir konum girebilirsiniz.  
  
     Tıklatın **Tamam** yeni proje oluşturmak için.  
  
4.  Çözüm Gezgini görünür durumda değilse, tıklatın **Çözüm Gezgini** üzerinde **Görünüm** menüsü.  
  
5.  Yeni bir kaynak dosyası projeye ekleyin:  
  
    -   Sağ **kaynak dosyaları** klasörü Çözüm Gezgini'nde işaret **Ekle** tıklatıp **yeni öğe**.  
  
    -   Tıklatın **C++ dosyasına (.cpp)** ve bir dosya adı yazın ve ardından **Ekle**.  
  
     **.Cpp** dosya görünür **kaynak dosyaları** klasörü Çözüm Gezgini'nde ve sekmeli bir pencere görünür kod girildiği bu dosyada istiyor.  
  
6.  Visual Studio'da yeni oluşturulan sekmesini tıklatın ve geçerli bir Visual C++ program yazın veya kopyalayın ve bir örnek programlar yapıştırın.  
  
     Örneğin, kullanabileceğiniz [nasıl yapılır: bir metin dosyasına yazma (C + +/ CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md) örnek program (içinde **dosya işleme ve g/ç** programlama kılavuzu düğümünün).  
  
     Örnek program kullanırsanız, kullandığına dikkat edin `gcnew` anahtar sözcüğü yerine `new` .NET nesnesi ve oluştururken `gcnew` bir işleyici döner (`^`) bir işaretçi yerine (`*`):  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     Yeni Visual C++ sözdizimi hakkında daha fazla bilgi için bkz: [çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md).  
  
7.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     **Çıkış** pencere konumunu derleme günlüğünde ve yapı durumu bildiren bir ileti gibi derleme ilerleme durumu hakkında bilgileri görüntüler.  
  
     Değişiklikleri yapın ve bir yapı yapmadan program çalıştırırsanız, bir iletişim kutusu projenin güncel olduğunu gösteriyor olabilir. Tıklamadan önce bu iletişim kutusundaki onay kutusunu işaretleyin **Tamam** dosyaların güncel sürümleri her zaman isteyen yerine her zaman kullanmak için Visual Studio istiyorsanız uygulama oluşturur.  
  
8.  Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat hata ayıklama olmadan**.  
  
9. Programını çalıştırdığınızda, örnek programı kullandıysanız metin dosyasının oluşturulduğunu belirten bir komut penceresi görüntülenir. Komut penceresini kapatmak için herhangi bir tuşa basın.  
  
     **Textfile.txt** metin dosyası artık proje dizininde bulunur. Not Defteri'ni kullanarak bu dosyayı açabilirsiniz.  
  
    > [!NOTE]
    >  Proje şablonu otomatik olarak ayarla boş CLR seçme **/CLR** derleyici seçeneği. Bunu doğrulamak için'nde projeye sağ **Çözüm Gezgini** tıklatıp **özellikleri**ve ardından denetleyin **ortak dil çalışma zamanı Destek** seçeneği **Genel** düğümünün **yapılandırma özellikleri**.  
  
## <a name="whats-next"></a>Sırada ne var?  
 **Önceki:** [izlenecek yol: komut satırında yerel C++ programı derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **sonraki:**[izlenecek yol: komut satırında C programı derleme](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)