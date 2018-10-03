---
title: Form kullanıcı denetimi olarak bir MFC iletişim kutusu bir Windows barındırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5867f9524d897657641ab9db392d77585117a465
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235001"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma

MFC sağlayan Şablon sınıfı [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) bir Windows Forms kullanıcı denetimi barındırabilmesi (<xref:System.Windows.Forms.UserControl>) kalıcı veya geçici bir MFC iletişim kutusunda. `CWinFormsDialog` MFC sınıfından türetilen [CDialog](../mfc/reference/cdialog-class.md), iletişim kutusu kalıcı veya kısıtlayıcı olmayan başlatılabilir.

İşlem, `CWinFormsDialog` kullanıcı denetimini barındırmak için kullandığı benzer açıklanan [MFC iletişim kutusu bir Windows formu kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md). Ancak, `CWinFormsDialog` başlatma ve böylece, el ile programlanmak zorunda değildir, kullanıcı denetimi barındırma yönetir.

MFC'de Windows formlarını gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için

1. MFC Uygulama projesi oluşturun.

     Üzerinde **dosya** menüsünde **yeni**ve ardından **proje**. İçinde **Visual C++** klasörüne **MFC uygulaması**.

     İçinde **adı** kutusuna `MFC03` ve çözüm ayarını değiştirme **eklemek için çözüm**. Tıklayın **Tamam**.

     İçinde **MFC Uygulama Sihirbazı**tüm Varsayılanları kabul edin ve ardından **son**. Bu, bir Çoklu Belge Arabirimiyle beraber bir MFC uygulaması oluşturur.

1. Projeyi yapılandırın.

     İçinde **Çözüm Gezgini**, sağ **MFC03** proje düğümünü ve seçin **özellikleri**. **Özellik sayfaları** iletişim kutusu görüntülenir.

     İçinde **özellik sayfaları** iletişim kutusundaki **yapılandırma özellikleri** ağaç denetiminden, select **genel**, ardından **Proje Varsayılanları**bölümünde, **ortak dil çalışma zamanı desteği** için **ortak dil çalışma zamanı desteği (/ clr)**. **Tamam**'ı tıklatın.

1. .NET denetimine bir başvuru ekleyin.

     İçinde **Çözüm Gezgini**, sağ **MFC03** projesini düğümünü ve ardından **Ekle**, **başvuruları**. İçinde **özellik sayfası**, tıklayın **Yeni Başvuru Ekle**, WindowsControlLibrary1'ı seçin (altında **projeleri** sekmesinde), tıklatıp **Tamam**. Bu biçimde bir başvuru ekler bir [/FU](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği, böylece programın derleyeceği; ayrıca WindowsControlLibrary1.dll öğesini kopyalar `MFC03` proje dizinine, böylece program çalışacaktır.

1. Ekleme `#include <afxwinforms.h>` varolan sonundaki stdafx.H'ye `#include` deyimleri.

1. Alt sınıflara ayıran yeni bir sınıf ekleyin `CDialog`.

     Proje adına sağ tıklayın ve alt sınıflara ayıran bir MFC sınıfı (CHostForWinForm adında) ekleyin `CDialog`. İletişim kutusu kaynağına gerekmediğinden, kaynak Kimliğini silebilirsiniz (seçin **kaynak görünümü**, genişletme **iletişim** klasörü ve delete `IDD_HOSTFORWINFORM` kaynak.  Daha sonra tüm başvuruları kimliğine kodda kaldırın.).

1. Değiştirin `CDialog` ile CHostForWinForm.h ve CHostForWinForm.cpp dosyalarındaki `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`.

1. CHostForWinForm sınıfındaki DoModal çağırın.

     MFC03.cpp öğesinde ekleme `#include "HostForWinForm.h"`.

     Mfc03app::InitInstance öğesinin tanımındaki dönüş deyiminden önce ekleyin:

    ```cpp
    CHostForWinForm m_HostForWinForm;
    m_HostForWinForm.DoModal();
    ```

1. Derleme ve projeyi çalıştırın.

     Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

     Üzerinde **hata ayıklama** menüsünü tıklatın **hata ayıklama olmadan Başlat**.

     Ardından MFC uygulamasından Windows Forms üzerindeki bir denetimin durumunu izlemek için kod ekleyeceksiniz.

9. OnInitDialog için bir işleyici ekleyin.

     Görüntü **özellikleri** penceresini (F4). İçinde **sınıf görünümü**, CHostForWinForm öğesini seçin. İçinde **özellikleri** penceresinde seçin geçersiz kılar ve OnInitDialog satırında, sol taraftaki sütunu tıklatın ve seçin \< Ekle >. Bu, CHostForWinForm.h öğesine aşağıdaki satırı ekler:

    ```cpp
    virtual BOOL OnInitDialog();
    ```

10. Aşağıdaki şekilde OnInitDialog (in CHostForWinForm.cpp) tanımlayın:

    ```
    BOOL CHostForWinForm::OnInitDialog() {
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);
       return TRUE;
    }
    ```

11. Daha sonra OnButton1 işleyicisini ekleyin. Aşağıdaki satırları CHostForWinForm.h'deki CHostForWinForm sınıfının ortak bölümüne ekleyin:

    ```
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );

    BEGIN_DELEGATE_MAP( CHostForWinForm )
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );
    END_DELEGATE_MAP()
    ```

     CHostForWinForm.cpp öğesine bu tanımı ekleyin:

    ```
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )
    {
       System::Windows::Forms::MessageBox::Show("test");
    }
    ```

12. Derleme ve projeyi çalıştırın. Windows Form üzerinde olan düğmeyi tıklattığınızda MFC uygulamasındaki kod çalışacaktır.

     Sonraki Windows Form üzerinde metin kutusunun değerini MFC kodundan görüntülemek için kod ekleyeceksiniz.

13. CHostForWinForm.h'deki CHostForWinForm sınıfının ortak bölümüne aşağıdaki bildirimi ekleyin:

    ```
    CString m_sEditBoxOnWinForm;
    ```

14. CHostForWinForm.cpp içinde DoDataExchange tanımında, aşağıdaki üç satırı işlevin sonuna ekleyin:

    ```
    if (pDX->m_bSaveAndValidate)
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);
    else
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);
    ```

15. CHostForWinForm.cpp içinde OnButton1 tanımında, aşağıdaki üç satırı işlevin sonuna ekleyin:

    ```
    this->UpdateData(TRUE);
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);
    System::Windows::Forms::MessageBox::Show(z);
    ```

16. Derleme ve projeyi çalıştırın.

## <a name="see-also"></a>Ayrıca Bkz.

<xref:System.Windows.Forms.UserControl?displayProperty=fullName>
[MFC içinde Windows formu kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)