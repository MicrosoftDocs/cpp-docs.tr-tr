---
title: 'Nasıl yapılır: Windows Forms ile DDX DDV veri bağlaması yapma | Microsoft Docs'
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
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2f6992aa0c7238d2dc89a8084c7b870dae23067a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Nasıl yapılır: Windows Forms ile DDX/DDV Veri Bağlaması Yapma
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) çağrıları [CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) kaynak denetimi kimlikle eşleşen bir denetim oluşturmak için Kullanırsanız `DDX_ManagedControl` için bir `CWinFormsControl` denetim değil çağırmalıdır (Sihirbaz tarafından oluşturulan kodda) `CreateManagedControl` açıkça aynı denetimi için.  
  
 Çağrı `DDX_ManagedControl` içinde [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) kaynak kimlikleri denetimleri oluşturmak için. Veri değişimi için Windows Forms denetimleri ile DDX/DDV işlevlerini kullanmak gerekmez. Bunun yerine yönetilen denetimin özelliklerine erişmek için kod yerleştirebilirsiniz `DoDataExchange` aşağıdaki örnekteki gibi iletişim (ya da Görünüm) sınıfının yöntemi.  
  
 Aşağıdaki örnek, yerel C++ dizesinin bir .NET kullanıcı denetimi bağlamak gösterilmektedir.  
  
## <a name="example"></a>Örnek  
 DDX/DDV veri bağlaması bir MFC dizesi örneği verilmiştir `m_str` kullanıcı tanımlı ile `NameText` bir .NET kullanıcı denetimi özelliği.  
  
 Denetimi ne zaman oluşturulur [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) çağrıları `CMyDlg::DoDataExchange` şekilde kodu ilk kez başvuran `m_UserControl` sonra gelmelidir `DDX_ManagedControl` çağırın.  
  
 Bu kod, oluşturduğunuz MFC01 uygulamasında uygulayabileceğiniz [nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
 Aşağıdaki kodu CMFC01Dlg bildiriminde koyun:  
  
```  
class CMFC01Dlg : public CDialog  
{  
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;  
   CString m_str;  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu CMFC01Dlg uygulamasında koyun:  
  
```  
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
{  
   CDialog::DoDataExchange(pDX);  
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);  
  
   if (pDX->m_bSaveAndValidate) {  
      m_str = m_MyControl->textBox1->Text;  
   } else  
   {  
      m_MyControl->textBox1->Text = gcnew System::String(m_str);  
   }  
}  
```  
  
## <a name="example"></a>Örnek  
 Tamam düğmesine tıklama için işleyici yöntemi şimdi ekleyeceğiz. Tıklatın **kaynak görünümü** sekmesi. Kaynak Görünümü'nde çift `IDD_MFC01_DIALOG`. İletişim kaynağını Kaynak Düzenleyicisi'nde görüntülenir. Ardından çift Tamam düğmesini tıklatın...  
  
 İşleyici aşağıdaki gibi tanımlayın.  
  
```  
void CMFC01Dlg::OnBnClickedOk()  
{  
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));  
   OnOK();  
}  
```  
  
## <a name="example"></a>Örnek  
 Ve BOOL CMFC01Dlg::OnInitDialog() uygulaması için aşağıdaki satırı ekleyin.  
  
```  
m_MyControl.GetControl()->textBox1->Text = "hello";  
```  
  
 Şimdi oluşturun ve uygulamayı çalıştırın. Uygulama kapandığında herhangi bir metin metin kutusuna bir açılır ileti kutusu içinde görüntülenir dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ddx_managedcontrol sınıfı](../mfc/reference/cwinformscontrol-class.md)   
 [DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)   
 [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)