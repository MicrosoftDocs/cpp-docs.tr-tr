---
title: 'Nasıl yapılır: Kullanıcı Denetim ve Konak MDI Görünümü Oluşturma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
ms.openlocfilehash: c2705ef1938684d8521316436fccaae367629584
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509128"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>Nasıl yapılır: Kullanıcı Denetim ve Konak MDI Görünümü Oluşturma

Aşağıdaki adımlarda, .NET Framework kullanıcı denetimi oluşturma, denetim sınıf kitaplığında (özellikle, bir Windows Denetim Kitaplığı projesi) kullanıcı denetiminde yazar ve ardından projenin bir derlemeye derlemek gösterilmektedir. Denetimin ardından öğelerinden türetilen sınıfları kullanan MFC uygulamasından tüketilebilir [CView sınıfı](../mfc/reference/cview-class.md) ve [CWinFormsView sınıfı](../mfc/reference/cwinformsview-class.md).

Bir Windows Forms kullanıcı denetimi oluşturun ve denetim sınıf kitaplığı yazma hakkında daha fazla bilgi için bkz: [nasıl yapılır: kullanıcı denetimleri yazma](/dotnet/framework/winforms/controls/how-to-author-composite-controls).

> [!NOTE]
>  Bazı durumlarda, Windows Forms denetimleri, bir üçüncü taraf kılavuz denetimi gibi güvenilir bir şekilde bir MFC uygulamasında barındırıldığında çalışmayabilir. MFC uygulamasında bir Windows Forms kullanıcı denetimi yerleştirin ve üçüncü taraf kılavuz denetimi yerleştirmektir yerleştirmek için önerilen bir çözüm var.

Bu yordamı, öğesindeki yordama göre WindowsFormsControlLibrary1 adında bir Windows Forms Denetim Kitaplığı projesi yarattığınızı varsayar [nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için

1. MFC Uygulama projesi oluşturun.

   Üzerinde **dosya** menüsünde **yeni**ve ardından **proje**. İçinde **Visual C++** klasörüne **MFC uygulaması**.

   İçinde **adı** kutusuna `MFC02` değiştirip **çözüm** ayarını **eklemek için çözüm**. **Tamam**'ı tıklatın.

   İçinde **MFC Uygulama Sihirbazı**tüm Varsayılanları kabul edin ve ardından **son**. Bu, bir Çoklu Belge Arabirimiyle beraber bir MFC uygulaması oluşturur.

1. Projeyi ortak dil çalışma zamanı (CLR) desteği için yapılandırın.

   İçinde **Çözüm Gezgini**, sağ `MFC01` proje düğümünü ve seçin **özellikleri** bağlam menüsünden. **Özellik sayfaları** iletişim kutusu görüntülenir.

   Altında **yapılandırma özellikleri**seçin **genel**. Altında **Proje Varsayılanları** bölümünde, **ortak dil çalışma zamanı desteği** için **ortak dil çalışma zamanı desteği (/ clr)**.

   Altında **yapılandırma özellikleri**, genişletme **C/C++** tıklatıp **genel** düğümü. Ayarlama **hata ayıklama bilgileri biçimi** için **Program veritabanı (/Zi)**.

   Tıklayın **kod oluşturma** düğümü. Ayarlama **en az yeniden derlemeyi etkinleştir** için **Hayır (/ Gm-)**. Ayrıca **temel çalışma zamanı denetimleri** için **varsayılan**.

   Tıklayın **Tamam** yaptığınız değişiklikleri uygulamak için.

1. Stdafx.h içinde şu satırı ekleyin:

    ```
    #using <System.Windows.Forms.dll>
    ```

1. .NET denetimine bir başvuru ekleyin.

   İçinde **Çözüm Gezgini**, sağ `MFC02` proje düğümünü seçip alt **Ekle**, **başvuruları**. İçinde **özellik sayfası**, tıklayın **Yeni Başvuru Ekle**, WindowsFormsControlLibrary1'ı seçin (altında **projeleri** sekmesinde), tıklatıp **Tamam** . Bu biçimde bir başvuru ekler bir [/FU](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği, böylece programın derleyeceği; ayrıca Windowscontrollibrary1.dll öğesini kopyalar `MFC02` proje dizinine, böylece program çalışacaktır.

1. Stdafx.h içinde şu satırı bulun:

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   Üstüne şu satırları ekleyin:

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. Görünüm sınıfını öğesinden devralacak şekilde değiştirin [CWinFormsView](../mfc/reference/cwinformsview-class.md).

   MFC02View.h içinde değiştirin [CView](../mfc/reference/cview-class.md) ile [CWinFormsView](../mfc/reference/cwinformsview-class.md) böylece kod aşağıdaki gibi görünür:

    ```
    class CMFC02View : public CWinFormsView
    {
    };
    ```

   MDI uygulamanıza ek görünümler eklemek istiyorsanız, çağırması gerekir [CWinApp::AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) için oluşturduğunuz her görünüm.

1. MFC02View.cpp dosyasında CView IMPLEMENT_DYNCREATE makrosu ve ileti Haritası içerisindeki CWinFormsView olarak değiştirin ve var olan boş oluşturucuyu aşağıda gösterilen oluşturucuyla değiştirin değiştirin:

    ```
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)

    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)
    {
    }
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)
    //leave existing body as is
    END_MESSAGE_MAP()
    ```

1. Derleme ve projeyi çalıştırın.

   İçinde **Çözüm Gezgini**, MFC02 sağ tıklayıp **başlangıç projesi olarak ayarla**.

   Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

   Üzerinde **hata ayıklama** menüsünü tıklatın **hata ayıklama olmadan Başlat**.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)