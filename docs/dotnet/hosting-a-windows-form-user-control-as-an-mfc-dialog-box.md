---
title: Form kullanıcı denetimi MFC iletişim kutusu olarak Windows barındırma | Microsoft Docs
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
ms.openlocfilehash: b356bff4974b43445524d9bc07e1e37c62a6f8d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33138684"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma
MFC sağlar Şablon sınıfı [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) böylece bir Windows Forms kullanıcı denetimi barındırabilir (<xref:System.Windows.Forms.UserControl>) kalıcı veya geçici bir MFC iletişim kutusunda. `CWinFormsDialog` MFC sınıfından türetilen [CDialog](../mfc/reference/cdialog-class.md), iletişim kutusu kalıcı veya geçici başlatılabilir.  
  
 İşlem, `CWinFormsDialog` kullanıcı denetimini barındırmak için kullandığı benzer bölümünde açıklanan [MFC iletişim kutusunda Windows Form kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md). Ancak, `CWinFormsDialog` başlatma ve böylece el ile programlanmış gerekmez kullanıcı denetimi barındırma yönetir.  
  
 MFC'de Windows Forms gösteren örnek bir uygulama için bkz: [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için  
  
1.  MFC Uygulama projesi oluşturun.  
  
     Üzerinde **dosya** menüsünde, select **yeni**ve ardından **proje**. İçinde **Visual C++** klasöründe seçin **MFC uygulaması**.  
  
     İçinde **adı** kutusuna `MFC03` çözüm ayarını değiştirip **eklemek için çözüm**. Tıklatın **Tamam**.  
  
     İçinde **MFC Uygulama Sihirbazı'nı**, tüm Varsayılanları kabul edin ve ardından **son**. Bu, birden çok belge arabirimi ile bir MFC uygulaması oluşturur.  
  
2.  Projeyi yapılandırın.  
  
     İçinde **Çözüm Gezgini**, sağ **MFC03** proje düğümünü ve seçin **özellikleri**. **Özellik sayfaları** iletişim kutusu görüntülenir.  
  
     İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** ağaç denetimi, select **genel**, ardından **Proje Varsayılanları**bölümünde, **ortak dil çalışma zamanı Destek** için **ortak dil çalışma zamanı desteği (/ clr)**. **Tamam**'ı tıklatın.  
  
3.  .NET denetlemek için bir başvuru ekleyin.  
  
     İçinde **Çözüm Gezgini**, sağ **MFC03** proje düğümünü ve seçin **Ekle**, **başvurular**. İçinde **özellik sayfası**, tıklatın **Yeni Başvuru Ekle**, WindowsControlLibrary1 seçin (altında **projeleri** sekmesinde), tıklatıp **Tamam**. Bu biçiminde bir başvuru ekler bir [/FU](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği program derlenir; ayrıca WindowsControlLibrary1.dll kopyalar `MFC03` proje dizinine program çalışır.  
  
4.  Ekleme `#include <afxwinforms.h>` var olan sonunda Stdafx.H'ye `#include` deyimleri.  
  
5.  Bu alt sınıfların yeni bir sınıf ekleyin `CDialog`.  
  
     Proje adına sağ tıklayın ve o alt sınıfların bir MFC sınıfı (CHostForWinForm) eklemek `CDialog`. İletişim kutusu kaynağı gerekmediği kaynak kimliği silebilirsiniz (kaynak görünümünü seçin, iletişim klasörünü genişletin ve IDD_HOSTFORWINFORM kaynağını silin.  Ardından, tüm başvuruları kimliği kodda kaldırın.).  
  
6.  Değiştir `CDialog` ile CHostForWinForm.h ve CHostForWinForm.cpp dosyalarındaki `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`.  
  
7.  DoModal CHostForWinForm sınıfının çağırın.  
  
     MFC03.cpp içinde eklemek `#include "HostForWinForm.h"`.  
  
     CMFC03App::InitInstance tanımını içindeki return deyimi önce ekleyin:  
  
     `CHostForWinForm m_HostForWinForm;`  
  
     `m_HostForWinForm.DoModal();`  
  
8.  Oluşturun ve projeyi çalıştırın.  
  
     Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat hata ayıklama olmadan**.  
  
     Sonraki MFC uygulamasından Windows Forms denetiminde durumunu izlemek için kod ekleyeceksiniz.  
  
9. OnInitDialog için bir işleyici ekleyin.  
  
     Görüntü **özellikleri** penceresi (F4). İçinde **sınıf görünümü**, CHostForWinForm öğesini seçin. İçinde **özellikleri** penceresinde, seçin geçersiz kılar ve OnInitDialog satırında, sol taraftaki sütunda tıklatın ve seçin \< Ekle >. Bu, aşağıdaki satırı CHostForWinForm.h öğesine ekler:  
  
    ```  
    virtual BOOL OnInitDialog();  
    ```  
  
10. OnInitDialog (in CHostForWinForm.cpp) aşağıdaki gibi tanımlayın:  
  
    ```  
    BOOL CHostForWinForm::OnInitDialog() {  
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();  
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);  
       return TRUE;  
    }  
    ```  
  
11. Daha sonra OnButton1 işleyicisini ekleyin. CHostForWinForm.h'deki CHostForWinForm sınıfının ortak bölümüne aşağıdaki satırları ekleyin:  
  
    ```  
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );  
  
    BEGIN_DELEGATE_MAP( CHostForWinForm )  
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );  
    END_DELEGATE_MAP()  
    ```  
  
     CHostForWinForm.cpp Bu tanım ekleyin:  
  
    ```  
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )   
    {  
       System::Windows::Forms::MessageBox::Show("test");  
    }  
    ```  
  
12. Oluşturun ve projeyi çalıştırın. Windows formunda olan Düğmeye tıkladığınızda MFC uygulamasındaki kod çalıştırın.  
  
     Sonra MFC kodundan Windows formunda metin kutusundaki değeri görüntülemek için kod ekleyeceksiniz.  
  
13. CHostForWinForm.h'deki CHostForWinForm sınıfının ortak bölümünde aşağıdaki bildirimi ekleyin:  
  
    ```  
    CString m_sEditBoxOnWinForm;  
    ```  
  
14. CHostForWinForm.cpp DoDataExchange tanımında aşağıdaki üç satır işlevi sonuna ekleyin:  
  
    ```  
    if (pDX->m_bSaveAndValidate)  
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);  
    else  
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);  
    ```  
  
15. İn CHostForWinForm.cpp sonra OnButton1 tanımında aşağıdaki üç satır işlevi sonuna ekleyin:  
  
    ```  
    this->UpdateData(TRUE);  
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);  
    System::Windows::Forms::MessageBox::Show(z);  
    ```  
  
16. Oluşturun ve projeyi çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [MFC içinde Windows Formu Kullanıcı Denetimi Kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)