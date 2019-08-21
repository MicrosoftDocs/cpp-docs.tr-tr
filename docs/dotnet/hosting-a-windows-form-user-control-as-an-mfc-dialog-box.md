---
title: MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
ms.openlocfilehash: 96730cb3902674373e3e2429b7bc51cbbe257ff3
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630839"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma

MFC, bir Windows Forms user [](../mfc/reference/cwinformsdialog-class.md) Control (<xref:System.Windows.Forms.UserControl>) öğesini kalıcı veya kalıcı MFC iletişim kutusunda barındırabilmeniz için CWinFormsDialog şablon sınıfını sağlar. `CWinFormsDialog`MFC sınıfı [CDialog](../mfc/reference/cdialog-class.md)sınıfından türetilir, bu nedenle iletişim kutusu kalıcı veya kalıcı olarak başlatılabilir.

Kullanıcı denetimini barındırmak `CWinFormsDialog` için kullanan işlem, [MFC iletişim kutusunda Windows form kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)bölümünde açıklananla benzerdir. Ancak, `CWinFormsDialog` Kullanıcı denetiminin başlatılmasını ve barındırmayı yönetir, böylece el ile programlanabilir olması gerekmez.

MFC ile kullanılan Windows Forms gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirmesi](https://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

### <a name="to-create-the-mfc-host-application"></a>MFC ana bilgisayar uygulaması oluşturmak için

1. MFC Uygulama projesi oluşturun.

   **Dosya** menüsünde **Yeni**' yi seçin ve ardından **Proje**' ye tıklayın. **C++ Görsel** klasöründe **MFC uygulaması**' nı seçin.

   **Ad** kutusunda, çözüm ayarını `MFC03` **çözüme Ekle**' ye girin ve değiştirin. **Tamam**' a tıklayın.

   **MFC Uygulama sihirbazında**tüm varsayılanları kabul edin ve ardından **son**' a tıklayın. Bu, birden çok belge arabirimine sahip bir MFC uygulaması oluşturur.

1. Projeyi yapılandırın.

   **Çözüm Gezgini**, **MFC03** proje düğümüne sağ tıklayın ve **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusu görüntülenir.

   **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri** ağaç denetiminde **genel**' i seçin, sonra **Proje Varsayılanları** bölümünde ortak dil çalışma zamanı **desteğini** **ortak dil çalışma zamanı desteğine ayarlayın ( /clr)** . **Tamam**'ı tıklatın.

1. .NET denetimine bir başvuru ekleyin.

   **Çözüm Gezgini**, **MFC03** proje düğümüne sağ tıklayın ve **Ekle**, **Başvurular**' ı seçin. **Özellik sayfasında**, **Yeni Başvuru Ekle**' ye tıklayın, WindowsControlLibrary1 ( **Projeler** sekmesi altında) seçeneğini belirleyin ve **Tamam**' a tıklayın. Bu, programın derleyeceği bir [/Fu](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği biçiminde bir başvuru ekler; Ayrıca, WindowsControlLibrary1. dll `MFC03` ' i proje dizinine kopyalar, böylece programın çalışması gerekir.

1. Var `#include <afxwinforms.h>` olan`#include` deyimlerin sonundaki *pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) öğesine ekleyin.

1. Alt sınıflara `CDialog`sahip yeni bir sınıf ekleyin.

   Proje adı ' na sağ tıklayın ve alt sınıflı bir MFC sınıfı (CHostForWinForm adlı `CDialog`) ekleyin. İletişim kutusu kaynağına ihtiyacınız olmadığından, kaynak kimliğini silebilir ( **kaynak görünümü**seçin, **iletişim kutusu** klasörünü genişletebilir ve kaynağı silebilirsiniz `IDD_HOSTFORWINFORM` .  Ardından, koddaki KIMLIĞE başvuruları kaldırın.).

1. CHostForWinForm. h ve CHostForWinForm. cpp dosyalarını ile `CDialog` `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`değiştirin.

1. CHostForWinForm sınıfında DoModal çağrısı yapın.

   MFC03. cpp içinde ekleyin `#include "HostForWinForm.h"`.

   CMFC03App:: InitInstance tanımındaki Return ifadesinden önce şunu ekleyin:

    ```cpp
    CHostForWinForm m_HostForWinForm;
    m_HostForWinForm.DoModal();
    ```

1. Derleme ve projeyi çalıştırın.

   Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

   **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın.

   Daha sonra, MFC uygulamasından Windows Forms bir denetimin durumunu izlemek için kod ekleyeceksiniz.

1. OnInitDialog için bir işleyici ekleyin.

   **Özellikler** penceresini (F4) görüntüleyin. **Sınıf görünümü**, CHostForWinForm ' ı seçin. **Özellikler** penceresinde, geçersiz kılmalar ' ı seçin ve OnInitDialog satırında, sol taraftaki sütuna tıklayın ve > Ekle ' yi seçin \< . Bu, CHostForWinForm. h öğesine aşağıdaki satırı ekler:

    ```cpp
    virtual BOOL OnInitDialog();
    ```

1. OnInitDialog (CHostForWinForm. cpp) aşağıdaki gibi tanımlayın:

    ```cpp
    BOOL CHostForWinForm::OnInitDialog() {
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);
       return TRUE;
    }
    ```

1. Daha sonra OnButton1 işleyicisini ekleyin. Aşağıdaki satırları CHostForWinForm. h içindeki CHostForWinForm sınıfının ortak bölümüne ekleyin:

    ```cpp
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );

    BEGIN_DELEGATE_MAP( CHostForWinForm )
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );
    END_DELEGATE_MAP()
    ```

   CHostForWinForm. cpp içinde şu tanımı ekleyin:

    ```cpp
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )
    {
       System::Windows::Forms::MessageBox::Show("test");
    }
    ```

1. Derleme ve projeyi çalıştırın. Windows formundaki düğmesine tıkladığınızda, MFC uygulamasındaki kod çalışır.

    Ardından, MFC kodundan görüntülenecek kodu Windows formundaki metin kutusunda bulunan değer ekleyeceksiniz.

1. CHostForWinForm. h içindeki CHostForWinForm sınıfının Genel bölümünde aşağıdaki bildirimi ekleyin:

    ```cpp
    CString m_sEditBoxOnWinForm;
    ```

1. CHostForWinForm. cpp içindeki DoDataExchange tanımında, aşağıdaki üç satırı işlevin sonuna ekleyin:

    ```cpp
    if (pDX->m_bSaveAndValidate)
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);
    else
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);
    ```

1. CHostForWinForm. cpp içindeki OnButton1 tanımında, aşağıdaki üç satırı işlevin sonuna ekleyin:

    ```cpp
    this->UpdateData(TRUE);
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);
    System::Windows::Forms::MessageBox::Show(z);
    ```

1. Derleme ve projeyi çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

<xref:System.Windows.Forms.UserControl?displayProperty=fullName>
[MFC 'de Windows formu Kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)
