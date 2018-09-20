---
title: 'Nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d0067681573f3d8f1c49d5a711daf09e20b14847
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411046"
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>Nasıl yapılır: İletişim Kutusunda Kullanıcı Denetimi Ve Konak Oluşturma

Bu makaledeki adımlar iletişime dayalı oluşturduğunuzu varsayar ([CDialog sınıfı](../mfc/reference/cdialog-class.md)) Microsoft Foundation Classes (MFC) projesi, ancak aynı zamanda desteği ekleyebilirsiniz bir Windows Forms denetimi varolan bir MFC iletişim kutusu.

### <a name="to-create-the-net-user-control"></a>.NET kullanıcı denetimi oluşturmak için

1. Adlı bir Visual C# Windows Forms Denetim Kitaplığı projesi oluşturun `WindowsFormsControlLibrary1`.

     Üzerinde **dosya** menüsünde tıklatın **yeni** ve ardından **proje**. İçinde **Visual C#** klasörüne **Windows Forms Denetim Kitaplığı**.

     Kabul `WindowsFormsControlLibrary1` tıklayarak proje adı **Tamam**.

     Varsayılan olarak, .NET denetiminin adı olacaktır `UserControl1`.

1. Alt öğe denetimleri Ekle `UserControl1`.

     İçinde **araç kutusu**açın **tüm Windows Formları** listesi. Sürükleme bir **düğmesi** denetimini `UserControl1` tasarım yüzeyi.

     Ayrıca bir **TextBox** denetimi.

1. İçinde **Çözüm Gezgini**, çift **UserControl1.Designer.cs** düzenlemek üzere açın. Metin kutusu ve düğmesinden bildirimlerini değiştirme `private` için `public`.

1. Projeyi oluşturun.

     Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için

1. MFC Uygulama projesi oluşturun.

     Üzerinde **dosya** menüsünde tıklatın **yeni** ve ardından **proje**. İçinde **Visual C++** klasörüne **MFC uygulaması**.

     İçinde **adı** kutusuna `MFC01`. Çözüm ayarını değiştirme **eklemek için çözüm**. **Tamam**'ı tıklatın.

     İçinde **MFC Uygulama Sihirbazı**, uygulama türü için **iletişim kutusu tabanlı**. Geri kalan varsayılan ayarları kabul edin ve tıklayın **son**. Bu, bir MFC iletişim kutusu olan bir MFC uygulaması oluşturur.

1. MFC iletişim kutusuna bir yer tutucu denetimi ekleyin.

     Üzerinde **görünümü** menüsünü tıklatın **kaynak görünümü**. İçinde **kaynak görünümü**, genişletme **iletişim** klasörü ve çift `IDD_MFC01_DIALOG`. İletişim kaynakları görünür **Kaynak Düzenleyicisi**.

     İçinde **araç kutusu**açın **iletişim kutusu Düzenleyicisi** listesi. Sürükleme bir **statik metin** iletişim kaynak denetimi. **Statik metin** denetimi .NET Windows Forms denetimleri için yer tutucu olarak hizmet edecektir. Windows Forms denetiminin yaklaşık boyuta yeniden boyutlandırın.

     İçinde **özellikleri** penceresinde değişiklik **kimliği** , **statik metin** denetimini `IDC_CTRL1` değiştirip **sekme durağı** özelliği **True**.

1. Projeyi ortak dil çalışma zamanı (CLR) desteği için yapılandırın.

     İçinde **Çözüm Gezgini**MFC01 proje düğümüne sağ tıklayın ve ardından **özellikleri**.

     İçinde **özellik sayfaları** iletişim kutusunun **yapılandırma özellikleri**seçin **genel**. İçinde **Proje Varsayılanları** bölümünde, **ortak dil çalışma zamanı desteği** için **ortak dil çalışma zamanı desteği (/ clr)**.

     Altında **yapılandırma özellikleri**, genişletme **C/C++** seçip **genel** düğümü. Ayarlama **hata ayıklama bilgileri biçimi** için **Program veritabanı (/Zi)**.

     Seçin **kod oluşturma** düğümü. Ayarlama **en az yeniden derlemeyi etkinleştir** için **Hayır (/ Gm-)**. Ayrıca **temel çalışma zamanı denetimleri** için **varsayılan**.

     Tıklayın **Tamam** değişiklikleri uygulamak için.

1. .NET denetimine bir başvuru ekleyin.

     İçinde **Çözüm Gezgini**, MFC01 proje düğümüne sağ tıklayın ve ardından **Ekle**, **başvuruları**. Üzerinde **özellik sayfası**, tıklayın **Yeni Başvuru Ekle**seçin **WindowsFormsControlLibrary1** (altında **projeleri** sekmesinde) ve tıklayın **Tamam**. Bu biçimde bir başvuru ekler bir [/FU](../build/reference/fu-name-forced-hash-using-file.md) programın derleyeceği derleyici seçeneği. Böylece program çalışacaktır \MFC01\ proje klasörüne de Windowscontrollibrary1.dll bir kopyasını getirir.

1. Stdafx.h içinde şu satırı bulun:

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

     Üstüne şu satırları ekleyin:

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. Yönetilen denetim oluşturmak için kod ekleyin.

     İlk olarak, yönetilen denetimi bildirin. MFC01Dlg.h'de iletişim sınıfı bildirimine gidin ve korumalı kapsamda kullanıcı denetimine veri üyesi aşağıdaki şekilde ekleyin.

    ```
    class CMFC01Dlg : public CDialog
    {
       // ...
       // Data member for the .NET User Control:
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;
    ```

     Ardından, yönetilen denetim için bir uygulama sağlar. MFC01Dlg.cpp'de iletişimini geçersiz kılmada `CMFC01Dlg::DoDataExchange` MFC Uygulama Sihirbazı tarafından oluşturulan (değil `CAboutDlg::DoDataExchange`, aynı dosyada olduğu), yönetilen denetim oluşturmak ve statik yer tutucu IDC_CTRL1 ile ilişkilendirmek için aşağıdaki kodu ekleyin.

    ```
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
    {
       CDialog::DoDataExchange(pDX);
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);
    }
    ```

1. Derleme ve projeyi çalıştırın.

     İçinde **Çözüm Gezgini**, sağ **MFC01** ve ardından **başlangıç projesi olarak ayarla**.

     Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

     Üzerinde **hata ayıklama** menüsünü tıklatın **hata ayıklama olmadan Başlat**. MFC iletişim kutusu Windows Forms denetimlerini görüntülemelidir.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)