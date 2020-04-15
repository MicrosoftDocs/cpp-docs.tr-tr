---
title: 'Nasıl yapılır: Kullanıcı Denetim ve Konak MDI Görünümü Oluşturma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
ms.openlocfilehash: 72501ba32d3b8b9a5c5fd8dd0c56f0628642b147
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374464"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>Nasıl yapılır: Kullanıcı Denetim ve Konak MDI Görünümü Oluşturma

Aşağıdaki adımlar, bir .NET Framework kullanıcı denetiminin nasıl oluşturulup, bir denetim sınıfı kitaplığında (özellikle bir Windows Denetim Kitaplığı projesi) kullanıcı denetimini nasıl yazarak projeyi derlemeyi gösterir. Denetim daha sonra [CView Class](../mfc/reference/cview-class.md) ve [CWinFormsView Sınıfı'ndan](../mfc/reference/cwinformsview-class.md)türetilen sınıfları kullanan bir MFC uygulamasından tüketilebilir.

Windows Forms kullanıcı denetimi oluşturma ve denetim sınıfı kitaplığı yazma hakkında bilgi için [bkz.](/dotnet/framework/winforms/controls/how-to-author-composite-controls)

> [!NOTE]
> Bazı durumlarda, üçüncü taraf Grid denetimi gibi Windows Forms denetimleri, bir MFC uygulamasında barındırıldığında güvenilir bir şekilde çalışmayabilir. Önerilen geçici çözüm, MFC uygulamasına bir Windows Forms Kullanıcı Denetimi yerleştirmek ve üçüncü taraf Izgara denetimini Kullanıcı denetiminin içine yerleştirmektir.

Bu yordam, WindowsFormsControlLibrary1 adlı bir Windows Forms Controls Library projesi oluşturduğunuzu varsayar, bu yordama göre [Nasıl Yapılır: Kullanıcı Denetimini ve Ana Bilgisayar'ı Bir İletişim Kutusu'nda oluşturma.](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

### <a name="to-create-the-mfc-host-application"></a>MFC ana bilgisayar uygulamasını oluşturmak için

1. Bir MFC Uygulama projesi oluşturun.

   **Dosya** menüsünde **Yeni'yi**seçin ve ardından **Project'i**tıklatın. Visual **C++** klasöründe **MFC Application'ı**seçin.

   **Ad** kutusuna, `MFC02` **Çözüm** ayarı girin ve **Çözüme Ekle'yi**değiştirin. **Tamam**'a tıklayın.

   **MFC Uygulama Sihirbazı'nda,** tüm varsayılanları kabul edin ve sonra **Bitir'i**tıklatın. Bu, Çoklu Belge Arabirimi olan bir MFC uygulaması oluşturur.

1. Ortak Dil Çalışma Süresi (CLR) desteği için projeyi yapılandırın.

   **Çözüm Gezgini'nde**proje `MFC01` düğümüne sağ tıklayın ve bağlam menüsünden **Özellikler'i** seçin. **Özellik Sayfaları** iletişim kutusu görüntülenir.

   **Yapılandırma Özellikleri**altında **Genel'i**seçin. Project **Defaults** bölümünde, **Ortak Dil Çalışma Zamanı desteğini** Ortak Dil Çalışma Süresi Desteği **(/clr)** olarak ayarlayın.

   **Yapılandırma Özellikleri**altında **C/C++** seçeneğini genişletin ve **Genel** düğüm'ü tıklatın. **Hata Ayıklama Bilgi Biçimini** Program **Veritabanına (/Zi)** ayarlayın.

   Kod **Oluşturma** düğüm'üne tıklayın. **Minimum Yeniden Oluşturmayı** Hayır **(/Gm-)** olarak ayarlayın. Ayrıca **Temel Çalışma Zamanı Denetimlerini** **Varsayılan**olarak ayarlayın.

   Değişikliklerinizi uygulamak için **Tamam'ı** tıklatın.

1. *Pch.h* (Visual Studio 2017 ve önceki yıllarda*stdafx.h)* olarak aşağıdaki satırı ekleyin:

    ```
    #using <System.Windows.Forms.dll>
    ```

1. .NET denetimine bir başvuru ekleyin.

   **Çözüm Gezgini'nde**proje `MFC02` düğümüne sağ tıklayın ve Add **,** **References'ı**seçin. Özellik **Sayfasında,** **Yeni Başvuru Ekle'yi**tıklatın, WindowsFormsControlLibrary1'i seçin **(Projeler** sekmesinin altında) ve **Tamam'ı**tıklatın. Bu, programın derlet edilebis olması için [/FU](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği şeklinde bir başvuru ekler; ayrıca WindowsFormsControlLibrary1.dll'yi `MFC02` proje dizinine kopyalar, böylece program çalışır.

1. Stdafx.h olarak, bu satırı bulmak:

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   Üzerine şu satırları ekleyin:

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. Görünüm sınıfını [CWinFormsView'den](../mfc/reference/cwinformsview-class.md)devralabilecek şekilde değiştirin.

   MFC02View.h'de [CView'i](../mfc/reference/cview-class.md) [CWinFormsView](../mfc/reference/cwinformsview-class.md) ile değiştirin, böylece kod aşağıdaki gibi görünür:

    ```
    class CMFC02View : public CWinFormsView
    {
    };
    ```

   MDI uygulamanıza ek görünüm ler eklemek istiyorsanız, oluşturduğunuz her görünüm için [CWinApp::AddDocTemplate'i](../mfc/reference/cwinapp-class.md#adddoctemplate) aramanız gerekir.

1. IMPLEMENT_DYNCREATE makro ve ileti haritasında CView'i CWinFormsView olarak değiştirmek için MFC02View.cpp dosyasını değiştirin ve varolan boş oluşturucuyu aşağıda gösterilen oluşturucuyla değiştirin:

    ```
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)

    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)
    {
    }
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)
    //leave existing body as is
    END_MESSAGE_MAP()
    ```

1. Projeyi oluşturun ve çalıştırın.

   **Çözüm Gezgini'nde**MFC02'ye sağ tıklayın ve **Başlangıç Projesi olarak Ayarla'yı**seçin.

   **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   Hata **Ayıklama** menüsünde hata **ayıklama olmadan Başlat'ı**tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
