---
title: "Nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 81a618c46f08366b9de2a02cbf84f73d42e7b108
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>Nasıl yapılır: İletişim Kutusunda Kullanıcı Denetimi Ve Konak Oluşturma
Bu makaledeki adımları iletişim tabanlı oluşturduğunuzu varsayar ([CDialog sınıfı](../mfc/reference/cdialog-class.md)) Microsoft Foundation sınıfları (MFC) projesi, ancak aynı zamanda desteği ekleyebilirsiniz bir Windows Forms denetimi için varolan bir MFC iletişim kutusu.  
  
### <a name="to-create-the-net-user-control"></a>.NET kullanıcı denetimi oluşturmak için  
  
1.  Adlı bir Visual C# Windows Forms Denetim Kütüphanesi projesi oluşturun `WindowsFormsControlLibrary1`.  
  
     Üzerinde **dosya** menüsünde tıklatın **yeni** ve ardından **proje**. İçinde **Visual C#** klasöründe seçin **Windows Forms Denetim Kitaplığı**.  
  
     Kabul `WindowsFormsControlLibrary1` tıklatarak proje adı **Tamam**.  
  
     Varsayılan olarak, .NET denetiminin adı olacaktır `UserControl1`.  
  
2.  Alt denetimler ekleme `UserControl1`.  
  
     İçinde **araç**, açık **tüm Windows Formları** listesi. Sürükleme bir **düğmesini** denetimini `UserControl1` tasarım yüzeyi.  
  
     Ayrıca bir **TextBox** denetim.  
  
3.  İçinde **Çözüm Gezgini**, çift **UserControl1.Designer.cs** düzenlemek için açın. Metin kutusu ve düğmesinden bildirimlerini değiştirme `private` için `public`.  
  
4.  Projeyi oluşturun.  
  
     Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için  
  
1.  MFC Uygulama projesi oluşturun.  
  
     Üzerinde **dosya** menüsünde tıklatın **yeni** ve ardından **proje**. İçinde **Visual C++** klasöründe seçin **MFC uygulaması**.  
  
     İçinde **adı** kutusuna `MFC01`. Çözüm ayarını değiştirme **eklemek için çözüm**. **Tamam**'ı tıklatın.  
  
     İçinde **MFC Uygulama Sihirbazı'nı**, uygulama türü için **tabanlı iletişim**. Geri kalan varsayılan ayarları kabul edin ve tıklatın **son**. MFC iletişim kutusu olan MFC uygulaması oluşturur.  
  
2.  MFC iletişim kutusu için bir yer tutucu denetimi ekleyin.  
  
     Üzerinde **Görünüm** menüsünde tıklatın **kaynak görünümü**. İçinde **kaynak görünümü**, genişletin **iletişim** klasörü ve çift `IDD_MFC01_DIALOG`. İletişim kaynağını görünür **Kaynak Düzenleyici**.  
  
     İçinde **araç**, açık **iletişim kutusu Düzenleyicisi** listesi. Sürükleme bir **statik metin** iletişim kaynak denetimine. **Statik metin** denetimi .NET Windows Forms denetimi için bir yer tutucu olarak hizmet. Windows Forms denetimi boyutuna yaklaşık yeniden boyutlandırın.  
  
     İçinde **özellikleri** penceresinde, değişiklik **kimliği** , **statik metin** denetimini `IDC_CTRL1` değiştirip **TabStop** özelliği **Doğru**.  
  
3.  Proje ortak dil çalışma zamanı (CLR) desteği için yapılandırın.  
  
     İçinde **Çözüm Gezgini**MFC01 proje düğümüne sağ tıklayın ve ardından **özellikleri**.  
  
     İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri**seçin **genel**. İçinde **Proje Varsayılanları** bölümünde, **ortak dil çalışma zamanı Destek** için **ortak dil çalışma zamanı desteği (/ clr)**.  
  
     Altında **yapılandırma özellikleri**, genişletin **C/C++** seçip **genel** düğümü. Ayarlama **hata ayıklama bilgileri biçimi** için **Program veritabanı (/Zi)**.  
  
     Seçin **kod oluşturma** düğümü. Ayarlama **en az yeniden derlemeyi etkinleştir** için **yok (/ Gm-)**. Ayrıca **temel çalışma zamanı denetler** için **varsayılan**.  
  
     Tıklatın **Tamam** değişiklikleri uygulamak için.  
  
4.  .NET denetlemek için bir başvuru ekleyin.  
  
     İçinde **Çözüm Gezgini**, MFC01 proje düğümüne sağ tıklayın ve ardından **Ekle**, **başvurular**. Üzerinde **özellik sayfası**, tıklatın **Yeni Başvuru Ekle**seçin **WindowsFormsControlLibrary1** (altında **projeleri** sekmesinde) ve'ı tıklatın **Tamam**. Bu biçiminde bir başvuru ekler bir [/FU](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği program derlenir. Program çalıştıracağı \MFC01\ proje klasöründe de WindowsFormsControlLibrary1.dll kopyasını koyar.  
  
5.  Stdafx.h'de bu satırı bulun:  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     Üstüne aşağıdaki satırları ekleyin:  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  Yönetilen denetim oluşturmak için kodu ekleyin.  
  
     Öncelikle, yönetilen denetimi bildirin. MFC01Dlg.h'ta iletişim sınıfı bildirimine gidin ve veri üyesi kullanıcı denetimi için korumalı kapsamda aşağıdaki şekilde ekleyin.  
  
    ```  
    class CMFC01Dlg : public CDialog  
    {  
       // ...  
       // Data member for the .NET User Control:  
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;  
    ```  
  
     Ardından, bir yönetilen denetim için belirtin. İletişim kutusunda MFC01Dlg.cpp'de geçersiz kılmak `CMFC01Dlg::DoDataExchange` MFC Uygulama Sihirbazı tarafından üretilen (değil `CAboutDlg::DoDataExchange`, aynı dosyada olduğu), yönetilen denetim oluşturmak ve statik yer tutucu IDC_CTRL1 ile ilişkilendirmek için aşağıdaki kodu ekleyin.  
  
    ```  
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
    {  
       CDialog::DoDataExchange(pDX);  
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);  
    }  
    ```  
  
7.  Oluşturun ve projeyi çalıştırın.  
  
     İçinde **Çözüm Gezgini**, sağ **MFC01** ve ardından **başlangıç projesi olarak ayarla**.  
  
     Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat hata ayıklama olmadan**. MFC iletişim kutusunda Windows Forms denetimi görüntülenmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)