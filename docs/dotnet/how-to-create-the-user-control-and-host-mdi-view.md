---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: Kullanıcı denetimi ve Konak MDI görünümü oluşturma'
title: 'Nasıl yapılır: Kullanıcı Denetim ve Konak MDI Görünümü Oluşturma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
ms.openlocfilehash: d05d2132c4382365b1de16490481049cb43ffe22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328773"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>Nasıl yapılır: Kullanıcı Denetim ve Konak MDI Görünümü Oluşturma

Aşağıdaki adımlarda, bir .NET Framework Kullanıcı denetimi oluşturma, Kullanıcı denetimini bir denetim sınıfı kitaplığında (özellikle bir Windows Denetim Kitaplığı Projesi) yazma ve ardından projeyi bir derlemede derleme işlemleri gösterilmektedir. Daha sonra Denetim, [CView sınıfı](../mfc/reference/cview-class.md) ve [CWinFormsView sınıfından](../mfc/reference/cwinformsview-class.md)TÜRETILMIŞ sınıfları kullanan bir MFC uygulamasından tüketilebilir.

Bir Windows Forms Kullanıcı denetimi oluşturma ve bir denetim sınıfı kitaplığı yazma hakkında daha fazla bilgi için bkz. [nasıl yapılır: Yazar Kullanıcı denetimleri](/dotnet/framework/winforms/controls/how-to-author-composite-controls).

> [!NOTE]
> Bazı durumlarda, üçüncü taraf kılavuz denetimi gibi Windows Forms denetimleri, bir MFC uygulamasında barındırılırken güvenilir bir şekilde davranmayabilir. Önerilen bir geçici çözüm, MFC uygulamasına bir Windows Forms Kullanıcı denetimi yerleştirmekte ve üçüncü taraf kılavuz denetimini Kullanıcı denetimi içine yerleştirmemedir.

Bu yordamda, [bir Iletişim kutusunda Kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)bölümündeki yordama göre WindowsFormsControlLibrary1 adlı bir Windows Forms denetimleri kitaplık projesi oluşturduğunuzu varsaymış olursunuz.

### <a name="to-create-the-mfc-host-application"></a>MFC ana bilgisayar uygulaması oluşturmak için

1. MFC Uygulama projesi oluşturun.

   **Dosya** menüsünde **Yeni**' yi seçin ve ardından **Proje**' ye tıklayın. **Visual C++** klasöründe **MFC uygulaması**' nı seçin.

   **Ad** kutusunda, çözüm `MFC02` ayarını **çözüme Ekle**' ye  girin ve değiştirin. **Tamam** düğmesine tıklayın.

   **MFC Uygulama sihirbazında** tüm varsayılanları kabul edin ve ardından **son**' a tıklayın. Bu, birden çok belge arabirimine sahip bir MFC uygulaması oluşturur.

1. Projeyi ortak dil çalışma zamanı (CLR) desteği için yapılandırın.

   **Çözüm Gezgini**, `MFC01` proje düğümüne sağ tıklayın ve bağlam menüsünden **Özellikler** ' i seçin. **Özellik sayfaları** iletişim kutusu görüntülenir.

   **Yapılandırma özellikleri** altında **genel**' i seçin. **Proje Varsayılanları** bölümünde ortak **dil çalışma zamanı** desteğini **ortak dil çalışma zamanı desteği (/CLR)** olarak ayarlayın.

   **Yapılandırma özellikleri** altında **C/C++** öğesini genişletin ve **genel** düğümüne tıklayın. **Hata ayıklama bilgileri biçimini** **Program veritabanı (/Zi)** olarak ayarlayın.

   **Kod oluşturma** düğümüne tıklayın. **En az yeniden derlemeyi etkinleştir** **(/GM-)** olarak ayarlayın. **Temel çalışma zamanı denetimlerini** de **varsayılan** olarak ayarlayın.

   Değişikliklerinizi uygulamak için **Tamam** ' ı tıklatın.

1. *Pch. h* Içinde (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ), aşağıdaki satırı ekleyin:

    ```
    #using <System.Windows.Forms.dll>
    ```

1. .NET denetimine bir başvuru ekleyin.

   **Çözüm Gezgini**, `MFC02` proje düğümüne sağ tıklayın ve **Ekle**, **Başvurular**' ı seçin. **Özellik sayfasında**, **Yeni Başvuru Ekle**' ye tıklayın, WindowsFormsControlLibrary1 ( **Projeler** sekmesi altında) seçeneğini belirleyin ve **Tamam**' a tıklayın. Bu, programın derleyeceği bir [/Fu](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği biçiminde bir başvuru ekler; Ayrıca `MFC02` , WindowsFormsControlLibrary1.dll programın çalışması için proje dizinine kopyalar.

1. Stbafx. h içinde şu satırı bulun:

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   Bu satırları üzerine ekleyin:

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. Görünüm sınıfını [CWinFormsView](../mfc/reference/cwinformsview-class.md)öğesinden devrabir şekilde değiştirin.

   MFC02View. h içinde, kodun aşağıdaki gibi görünmesi için [CView](../mfc/reference/cview-class.md) ile [CWinFormsView](../mfc/reference/cwinformsview-class.md) değiştirin:

    ```
    class CMFC02View : public CWinFormsView
    {
    };
    ```

   MDI uygulamanıza ek görünümler eklemek istiyorsanız, oluşturduğunuz her görünüm için [CWinApp:: AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) ' i çağırmanız gerekecektir.

1. MFC02View. cpp dosyasını IMPLEMENT_DYNCREATE makroda ve ileti eşlemesinde CView CWinFormsView olarak değiştirin ve var olan boş oluşturucuyu aşağıda gösterilen oluşturucuyla değiştirin:

    ```
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)

    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)
    {
    }
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)
    //leave existing body as is
    END_MESSAGE_MAP()
    ```

1. Projeyi derleyin ve çalıştırın.

   **Çözüm Gezgini**' de, MFC02 ' a sağ tıklayın ve **Başlangıç projesi olarak ayarla**' yı seçin.

   **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
