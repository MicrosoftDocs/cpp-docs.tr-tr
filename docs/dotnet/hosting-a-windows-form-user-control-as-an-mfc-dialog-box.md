---
description: 'Hakkında daha fazla bilgi edinin: bir Windows form kullanıcı denetimini MFC Iletişim kutusu olarak barındırma'
title: MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
ms.openlocfilehash: 885b63e17140cca7983aeeed26e56eac47091a0d
ms.sourcegitcommit: 3987d9c39f5a5b4824303a48a6215984ce8949e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/02/2021
ms.locfileid: "99478064"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma

MFC, bir Windows Forms user [](../mfc/reference/cwinformsdialog-class.md) Control ( <xref:System.Windows.Forms.UserControl> ) öğesini kalıcı veya kalıcı MFC iletişim kutusunda barındırabilmeniz için CWinFormsDialog şablon sınıfını sağlar. `CWinFormsDialog` MFC sınıfı [CDialog](../mfc/reference/cdialog-class.md)sınıfından türetilir, bu nedenle iletişim kutusu kalıcı veya kalıcı olarak başlatılabilir.

`CWinFormsDialog`Kullanıcı denetimini barındırmak için kullanan işlem, [MFC Iletişim kutusunda Windows form kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)bölümünde açıklananla benzerdir. Ancak, `CWinFormsDialog` Kullanıcı denetiminin başlatılmasını ve barındırmayı yönetir, böylece el ile programlanabilir olması gerekmez.

MFC ile kullanılan Windows Forms gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirmesi](https://download.cnet.com/MFC-and-WinForms-Integration/3000-2383_4-75453644.html).

### <a name="to-create-the-mfc-host-application"></a>MFC ana bilgisayar uygulaması oluşturmak için

1. MFC Uygulama projesi oluşturun.

   **Dosya** menüsünde **Yeni**' yi seçin ve ardından **Proje**' ye tıklayın. **Visual C++** klasöründe **MFC uygulaması**' nı seçin.

   **Ad** kutusunda, çözüm `MFC03` ayarını **çözüme Ekle**' ye girin ve değiştirin. **Tamam**' a tıklayın.

   **MFC Uygulama sihirbazında** tüm varsayılanları kabul edin ve ardından **son**' a tıklayın. Bu, birden çok belge arabirimine sahip bir MFC uygulaması oluşturur.

1. Projeyi yapılandırın.

   **Çözüm Gezgini**, **MFC03** proje düğümüne sağ tıklayın ve **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusu görüntülenir.

   **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri** ağaç denetiminde **genel**' i seçin, sonra **Proje Varsayılanları** bölümünde ortak dil çalışma zamanı **desteğini** **ortak dil çalışma zamanı desteği (/CLR)** olarak ayarlayın. **Tamam**'a tıklayın.

1. .NET denetimine bir başvuru ekleyin.

   **Çözüm Gezgini**, **MFC03** proje düğümüne sağ tıklayın ve **Ekle**, **Başvurular**' ı seçin. **Özellik sayfasında**, **Yeni Başvuru Ekle**' ye tıklayın, WindowsControlLibrary1 ( **Projeler** sekmesi altında) seçeneğini belirleyin ve **Tamam**' a tıklayın. Bu, programın derleyeceği bir [/Fu](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği biçiminde bir başvuru ekler; Ayrıca `MFC03` , WindowsControlLibrary1.dll programın çalışması için proje dizinine kopyalar.

1. `#include <afxwinforms.h>`Var olan deyimlerin sonundaki *pch. h* (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ) öğesine ekleyin `#include` .

1. Alt sınıflara sahip yeni bir sınıf ekleyin `CDialog` .

   Proje adı ' na sağ tıklayın ve alt sınıflı bir MFC sınıfı (CHostForWinForm adlı) ekleyin `CDialog` . İletişim kutusu kaynağına ihtiyacınız olmadığından, kaynak KIMLIĞINI silebilir ( **kaynak görünümü** seçin, **iletişim kutusu** klasörünü genişletebilir ve `IDD_HOSTFORWINFORM` kaynağı silebilirsiniz.  Ardından, koddaki KIMLIĞE başvuruları kaldırın.).

1. `CDialog`CHostForWinForm. h ve CHostForWinForm. cpp dosyalarını ile değiştirin `CWinFormsDialog<WindowsControlLibrary1::UserControl1>` .

1. CHostForWinForm sınıfında DoModal çağrısı yapın.

   MFC03. cpp içinde ekleyin `#include "HostForWinForm.h"` .

   CMFC03App:: InitInstance tanımındaki Return ifadesinden önce şunu ekleyin:

    ```cpp
    CHostForWinForm m_HostForWinForm;
    m_HostForWinForm.DoModal();
    ```

1. Projeyi derleyin ve çalıştırın.

   **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın.

   Daha sonra, MFC uygulamasından Windows Forms bir denetimin durumunu izlemek için kod ekleyeceksiniz.

1. OnInitDialog için bir işleyici ekleyin.

   **Özellikler** penceresini (F4) görüntüleyin. **Sınıf görünümü**, CHostForWinForm ' ı seçin. **Özellikler** penceresinde, geçersiz kılmalar ' ı seçin ve OnInitDialog satırında, sol taraftaki sütuna tıklayın ve öğesini seçin \< Add > . Bu, CHostForWinForm. h öğesine aşağıdaki satırı ekler:

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

<xref:System.Windows.Forms.UserControl?displayProperty=fullName>
[MFC 'de Windows formu Kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)
