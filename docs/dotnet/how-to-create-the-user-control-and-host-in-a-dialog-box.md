---
description: 'Nasıl yapılır: bir Iletişim kutusunda Kullanıcı denetimi ve konak oluşturma hakkında daha fazla bilgi edinin'
title: 'Nasıl yapılır: İletişim Kutusunda Kullanıcı Denetimi Ve Konak Oluşturma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
ms.openlocfilehash: 400906344f47f7100e52319adb37c39d1fb370e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283972"
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>Nasıl yapılır: İletişim Kutusunda Kullanıcı Denetimi Ve Konak Oluşturma

Bu makaledeki adımlarda, iletişim kutusu tabanlı ([CDialog sınıfı](../mfc/reference/cdialog-class.md)) MICROSOFT FOUNDATION SıNıFLARı (MFC) projesi oluşturduğunuzu, ancak var olan MFC iletişim kutusuna bir Windows Forms denetimi için de destek ekleyebildiğiniz varsayılır.

### <a name="to-create-the-net-user-control"></a>.NET Kullanıcı denetimi oluşturmak için

1. Adlı bir Visual C# Windows Forms denetim kitaplığı projesi oluşturun `WindowsFormsControlLibrary1` .

   **Dosya** menüsünde **Yeni** ' ye ve ardından **Proje**' ye tıklayın. **Visual C#** klasöründe **Windows Forms denetim kitaplığı**' nı seçin.

   Tamam ' a `WindowsFormsControlLibrary1` tıklayarak proje adını kabul edin.

   Varsayılan olarak, .NET denetiminin adı olacaktır `UserControl1` .

1. Öğesine alt denetimler ekleyin `UserControl1` .

   **Araç kutusunda** **tüm Windows Forms** listesini açın. Bir **düğme** denetimini `UserControl1` tasarım yüzeyine sürükleyin.

   Ayrıca bir **TextBox** denetimi de ekleyin.

1. **Çözüm Gezgini**, düzenlenmek üzere açmak için **UserControl1.Designer.cs** öğesine çift tıklayın. TextBox ve düğme bildirimlerini ' den ' `private` e değiştirin `public` .

1. Projeyi derleyin.

   **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

### <a name="to-create-the-mfc-host-application"></a>MFC ana bilgisayar uygulaması oluşturmak için

1. MFC Uygulama projesi oluşturun.

   **Dosya** menüsünde **Yeni** ' ye ve ardından **Proje**' ye tıklayın. **Visual C++** klasöründe **MFC uygulaması**' nı seçin.

   **Ad** kutusuna `MFC01` yazın. Çözüm ayarını **çözüme Ekle** olarak değiştirin. **Tamam** düğmesine tıklayın.

   **MFC Uygulama Sihirbazı**' nda, uygulama türü Için **iletişim kutusu temelli**' yi seçin. Kalan varsayılan ayarları kabul edin ve **son**' a tıklayın. Bu, MFC iletişim kutusu olan bir MFC uygulaması oluşturur.

1. MFC iletişim kutusuna bir yer tutucu denetimi ekleyin.

   **Görünüm** menüsünde **kaynak görünümü**' a tıklayın. **Kaynak görünümü**' de, **iletişim** klasörünü genişletin ve ' ı çift tıklatın `IDD_MFC01_DIALOG` . İletişim kaynağı **kaynak Düzenleyicisi**' nde görünür.

   **Araç kutusunda** **iletişim kutusu düzenleyici** listesini açın. İletişim kaynağına bir **statik metin** denetimi sürükleyin. **Statik metin** denetimi, .NET Windows Forms denetimi için bir yer tutucu olarak görev yapar. Windows Forms denetiminin boyutunu yaklaşık olarak yeniden boyutlandırın.

   **Özellikler** penceresinde, **statik metin** denetiminin **kimliğini** olarak değiştirin `IDC_CTRL1` ve **TabStop** özelliğini **true** olarak değiştirin.

1. Projeyi ortak dil çalışma zamanı (CLR) desteği için yapılandırın.

   **Çözüm Gezgini**, MFC01 proje düğümüne sağ tıklayın ve ardından **Özellikler**' e tıklayın.

   **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri** altında **genel**' i seçin. **Proje Varsayılanları** bölümünde ortak dil çalışma **zamanı** desteğini **ortak dil çalışma zamanı desteği (/CLR)** olarak ayarlayın.

   **Yapılandırma özellikleri** altında **C/C++** öğesini genişletin ve **genel** düğümünü seçin. **Hata ayıklama bilgileri biçimini** **Program veritabanı (/Zi)** olarak ayarlayın.

   **Kod oluşturma** düğümünü seçin. **En az yeniden derlemeyi etkinleştir** **(/GM-)** olarak ayarlayın. **Temel çalışma zamanı denetimlerini** de **varsayılan** olarak ayarlayın.

   Değişiklikleri uygulamak için **Tamam**'a tıklayın.

1. .NET denetimine bir başvuru ekleyin.

   **Çözüm Gezgini**, MFC01 proje düğümüne sağ tıklayın ve ardından **Ekle**, **Başvurular**' a tıklayın. **Özellik sayfasında**, **Yeni Başvuru Ekle**' ye tıklayın, **WindowsFormsControlLibrary1** ( **Projeler** sekmesi altında) seçeneğini belirleyin ve **Tamam**' a tıklayın. Bu, programın derleyeceği bir [/Fu](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği biçiminde bir başvuru ekler. Ayrıca, programın çalışması için \MFC01\ proje klasörüne bir WindowsFormsControlLibrary1.dll kopyası koyar.

1. Stbafx. h içinde şu satırı bulun:

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   Bunun üzerinde şu satırları ekleyin:

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. Yönetilen denetimi oluşturmak için kod ekleyin.

   İlk olarak, yönetilen denetimi bildirin. MFC01Dlg. h içinde, iletişim kutusu sınıfının bildirimine gidin ve korumalı kapsamdaki Kullanıcı denetimi için aşağıdaki gibi bir veri üyesi ekleyin.

    ```
    class CMFC01Dlg : public CDialog
    {
       // ...
       // Data member for the .NET User Control:
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;
    ```

   Ardından, yönetilen denetim için bir uygulama sağlayın. MFC01Dlg. cpp ' de, `CMFC01Dlg::DoDataExchange` MFC Uygulama Sihirbazı (aynı dosyada olan değil) tarafından oluşturulan iletişim kutusu geçersiz kılmada, `CAboutDlg::DoDataExchange` yönetilen denetimi oluşturmak ve statik yer tutucusu IDC_CTRL1 ilişkilendirmek için aşağıdaki kodu ekleyin.

    ```
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
    {
       CDialog::DoDataExchange(pDX);
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);
    }
    ```

1. Projeyi derleyin ve çalıştırın.

   **Çözüm Gezgini**' de, **MFC01** ' a sağ tıklayın ve ardından **Başlangıç projesi olarak ayarla**' ya tıklayın.

   **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın. MFC iletişim kutusunda Windows Forms denetimi görüntülenmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Iletişim kutusunda Windows form kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)
