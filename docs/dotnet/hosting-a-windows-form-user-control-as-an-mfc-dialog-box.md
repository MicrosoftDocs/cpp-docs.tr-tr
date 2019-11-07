---
title: MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
ms.openlocfilehash: 1351f0b2aa4ebc288469231a27c691237b52b1c1
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73704127"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma

MFC, bir Windows Forms Kullanıcı denetimini (<xref:System.Windows.Forms.UserControl>) kalıcı veya kalıcı MFC iletişim kutusunda barındırabilmeniz için şablon sınıfı [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) sağlar. `CWinFormsDialog` MFC sınıfı [CDialog](../mfc/reference/cdialog-class.md)sınıfından türetilir, bu nedenle iletişim kutusu kalıcı veya kalıcı olarak başlatılabilir.

`CWinFormsDialog` Kullanıcı denetimini barındırmak için kullandığı işlem, [MFC Iletişim kutusunda Windows form kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)bölümünde açıklananla benzerdir. Ancak, `CWinFormsDialog` el ile programlanabilmesi için Kullanıcı denetiminin başlatılmasını ve barındırmayı yönetir.

MFC ile kullanılan Windows Forms gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirmesi](https://www.microsoft.com/en-us/download/details.aspx?id=2113).

### <a name="to-create-the-mfc-host-application"></a>MFC ana bilgisayar uygulaması oluşturmak için

1. MFC Uygulama projesi oluşturun.

   **Dosya** menüsünde **Yeni**' yi seçin ve ardından **Proje**' ye tıklayın. **C++ Görsel** klasöründe **MFC uygulaması**' nı seçin.

   **Ad** kutusuna `MFC03` girin ve çözüm ayarını **çözüme Ekle**olarak değiştirin. **Tamam**' a tıklayın.

   **MFC Uygulama sihirbazında**tüm varsayılanları kabul edin ve ardından **son**' a tıklayın. Bu, birden çok belge arabirimine sahip bir MFC uygulaması oluşturur.

1. Projeyi yapılandırın.

   **Çözüm Gezgini**, **MFC03** proje düğümüne sağ tıklayın ve **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusu görüntülenir.

   **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri** ağaç denetiminde **genel**' i seçin, sonra **Proje Varsayılanları** bölümünde ortak dil çalışma zamanı **desteğini** **ortak dil çalışma zamanı desteğine ayarlayın ( /clr)** . **Tamam**'a tıklayın.

1. .NET denetimine bir başvuru ekleyin.

   **Çözüm Gezgini**, **MFC03** proje düğümüne sağ tıklayın ve **Ekle**, **Başvurular**' ı seçin. **Özellik sayfasında**, **Yeni Başvuru Ekle**' ye tıklayın, WindowsControlLibrary1 ( **Projeler** sekmesi altında) seçeneğini belirleyin ve **Tamam**' a tıklayın. Bu, programın derleyeceği bir [/Fu](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği biçiminde bir başvuru ekler; Ayrıca, WindowsControlLibrary1. dll dosyasını `MFC03` projesi dizinine kopyalar, böylece programın çalışması gerekir.

1. Mevcut `#include` deyimlerinin sonundaki *pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) öğesine `#include <afxwinforms.h>` ekleyin.

1. `CDialog`alt sınıflara yeni bir sınıf ekleyin.

   Proje adı ' na sağ tıklayın ve alt `CDialog`bir MFC sınıfı (CHostForWinForm adı verilir) ekleyin. İletişim kutusu kaynağına ihtiyacınız olmadığından, kaynak KIMLIĞINI silebilir ( **kaynak görünümü**seçin, **iletişim kutusu** klasörünü genişletebilir ve `IDD_HOSTFORWINFORM` kaynağını silebilirsiniz.  Ardından, koddaki KIMLIĞE başvuruları kaldırın.).

1. CHostForWinForm. h ve CHostForWinForm. cpp dosyalarındaki `CDialog` `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`ile değiştirin.

1. CHostForWinForm sınıfında DoModal çağrısı yapın.

   MFC03. cpp içinde `#include "HostForWinForm.h"`ekleyin.

   CMFC03App:: InitInstance tanımındaki Return ifadesinden önce şunu ekleyin:

    ```cpp
    CHostForWinForm m_HostForWinForm;
    m_HostForWinForm.DoModal();
    ```

1. Projeyi derleyin ve çalıştırın.

   **Yapı** menüsünde **çözüm oluştur**' a tıklayın.

   **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın.

   Daha sonra, MFC uygulamasından Windows Forms bir denetimin durumunu izlemek için kod ekleyeceksiniz.

1. OnInitDialog için bir işleyici ekleyin.

   **Özellikler** penceresini (F4) görüntüleyin. **Sınıf görünümü**, CHostForWinForm ' ı seçin. **Özellikler** penceresinde, geçersiz kılmalar ' ı seçin ve OnInitDialog satırında, sol taraftaki sütuna tıklayın ve \< Ekle > ' yi seçin. Bu, CHostForWinForm. h öğesine aşağıdaki satırı ekler:

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

1. Projeyi derleyin ve çalıştırın. Windows formundaki düğmesine tıkladığınızda, MFC uygulamasındaki kod çalışır.

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

1. Projeyi derleyin ve çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Windows form kullanıcı denetimi kullanarak](../dotnet/using-a-windows-form-user-control-in-mfc.md) 
<xref:System.Windows.Forms.UserControl?displayProperty=fullName>
