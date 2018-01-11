---
title: "Nasıl yapılır: kullanıcı Denetim ve konak MDI görünümü oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8b9b3c8ff385aed22785386c035ed537d8d97e97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>Nasıl yapılır: Kullanıcı Denetim ve Konak MDI Görünümü Oluşturma
Aşağıdaki adımlar bir .NET Framework kullanıcı denetimi oluşturma, denetim sınıf kitaplığı (özellikle, Windows Denetim Kitaplığı Proje), kullanıcı denetimi yazar ve ardından bir derlemeye Projeyi derlemek gösterir. Denetimin ardından türetilmiş sınıfları kullanan bir MFC uygulamasından tüketilebilir [CView sınıfı](../mfc/reference/cview-class.md) ve [CWinFormsView sınıfı](../mfc/reference/cwinformsview-class.md).  
  
 Bir Windows Forms kullanıcı denetimi oluşturmak ve bir denetim sınıf kitaplığı yazma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Yazar kullanıcı denetimleri](/dotnet/framework/winforms/controls/how-to-author-composite-controls).  
  
> [!NOTE]
>  Bazı durumlarda, bir üçüncü taraf kılavuz denetimi gibi Windows Forms denetimleri güvenilir bir MFC uygulamasında barındırıldığında çalışmayabilir. MFC uygulamasında bir Windows Forms kullanıcı denetimi yerleştirin ve üçüncü taraf kılavuz denetim içinde kullanıcı denetimini yerleştirmek için önerilen geçici bir çözüm değildir.  
  
 Bu yordam yordamda göredir WindowsFormsControlLibrary1 adlı bir Windows Forms denetimleri kitaplığı projesi oluşturduğunuzu varsayar [nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için  
  
1.  MFC Uygulama projesi oluşturun.  
  
     Üzerinde **dosya** menüsünde, select **yeni**ve ardından **proje**. İçinde **Visual C++** klasöründe seçin **MFC uygulaması**.  
  
     İçinde **adı** kutusuna `MFC02` değiştirip **çözüm** ayarını **eklemek için çözüm**. **Tamam**'ı tıklatın.  
  
     İçinde **MFC Uygulama Sihirbazı'nı**, tüm Varsayılanları kabul edin ve ardından **son**. Bu, birden çok belge arabirimi ile bir MFC uygulaması oluşturur.  
  
2.  Proje ortak dil çalışma zamanı (CLR) desteği için yapılandırın.  
  
     İçinde **Çözüm Gezgini**, sağ `MFC01` proje düğümünü ve seçin **özellikleri** ve bağlam menüsünden. **Özellik sayfaları** iletişim kutusu görüntülenir.  
  
     Altında **yapılandırma özellikleri**seçin **genel**. Altında **Proje Varsayılanları** bölümünde, **ortak dil çalışma zamanı Destek** için **ortak dil çalışma zamanı desteği (/ clr)**.  
  
     Altında **yapılandırma özellikleri**, genişletin **C/C++** tıklatıp **genel** düğümü. Ayarlama **hata ayıklama bilgileri biçimi** için **Program veritabanı (/Zi)**.  
  
     Tıklatın **kod oluşturma** düğümü. Ayarlama **en az yeniden derlemeyi etkinleştir** için **yok (/ Gm-)**. Ayrıca **temel çalışma zamanı denetler** için **varsayılan**.  
  
     Tıklatın **Tamam** değişikliklerinizi uygulamak için.  
  
3.  Stdafx.h'de aşağıdaki satırı ekleyin:  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
4.  .NET denetlemek için bir başvuru ekleyin.  
  
     İçinde **Çözüm Gezgini**, sağ `MFC02` proje düğümüne ve select **Ekle**, **başvurular**. İçinde **özellik sayfası**, tıklatın **Yeni Başvuru Ekle**, WindowsFormsControlLibrary1'i seçin (altında **projeleri** sekmesinde), tıklatıp **Tamam** . Bu biçiminde bir başvuru ekler bir [/FU](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği program derlenir; ayrıca Windowscontrollibrary1.dll kopyalar `MFC02` proje dizinine program çalışır.  
  
5.  Stdafx.h'de bu satırı bulun:  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     Yukarıdaki şu satırları ekleyin:  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  View sınıfı öğesinden devralınan şekilde değiştirmenize [CWinFormsView](../mfc/reference/cwinformsview-class.md).  
  
     MFC02View.h içinde Değiştir [CView](../mfc/reference/cview-class.md) ile [CWinFormsView](../mfc/reference/cwinformsview-class.md) böylece kodu aşağıdaki gibi görünür:  
  
    ```  
    class CMFC02View : public CWinFormsView  
    {  
    };  
    ```  
  
     Ek görünümler MDI uygulamanıza eklemek istiyorsanız, çağrı gerekir [CWinApp::AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) oluşturduğunuz her görünüm için.  
  
7.  CView CWinFormsView IMPLEMENT_DYNCREATE makrosu ve ileti eşlemesinde değiştirin ve var olan boş oluşturucuyu aşağıda gösterilen Oluşturucusu ile değiştirmek için MFC02View.cpp dosyasını değiştirin:  
  
    ```  
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)  
  
    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)   
    {  
    }  
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)  
    //leave existing body as is  
    END_MESSAGE_MAP()  
    ```  
  
8.  Oluşturun ve projeyi çalıştırın.  
  
     İçinde **Çözüm Gezgini**MFC02 sağ tıklatın ve seçin **başlangıç projesi olarak ayarla**.  
  
     Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat hata ayıklama olmadan**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)