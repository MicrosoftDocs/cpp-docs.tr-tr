---
title: 'Nasıl yapılır: Windows Forms ile DDX / DDV veri bağlaması yapma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: 793d6728c7726028c02b885784f122792d84dd2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456448"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Nasıl yapılır: Windows Forms ile DDX/DDV Veri Bağlaması Yapma

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) çağrıları [CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) kaynak denetimi kimlikle eşleşen bir denetim oluşturmak için Kullanırsanız `DDX_ManagedControl` için bir `CWinFormsControl` denetimi (Sihirbaz tarafından oluşturulan kodda) değil, çağırmalıdır `CreateManagedControl` açıkça için aynı denetimi.

Çağrı `DDX_ManagedControl` içinde [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) kaynak kimliklerinden denetimler oluşturabilirsiniz. Veri değişimi için Windows Forms denetimleri ile DDX/DDV işlevler kullanın gerekmez. Bunun yerine, yönetilen denetimi özelliklerine erişmek için kodu koyabilirsiniz `DoDataExchange` aşağıdaki örnekte olduğu gibi iletişim kutusu (veya Görünüm) sınıfının yöntemi.

Aşağıdaki örnek, bir .NET kullanıcı denetimi için bir yerel C++ dize bağlama gösterilmektedir.

## <a name="example"></a>Örnek

DDX/DDV veri bağlaması MFC dizesi örneği verilmiştir `m_str` ile kullanıcı tanımlı `NameText` bir .NET kullanıcı denetimi özelliği.

Denetim oluşturulur [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) çağrıları `CMyDlg::DoDataExchange` ilk kez, bu nedenle herhangi bir kod öğesine başvuran `m_UserControl` sonra gelmelidir `DDX_ManagedControl` çağırın.

Bu kod, oluşturduğunuz MFC01 uygulamada uygulayabileceğiniz [nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

Aşağıdaki kod CMFC01Dlg bildiriminde yerleştirin:

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example"></a>Örnek

Aşağıdaki kod CMFC01Dlg uygulamasında yerleştirin:

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

Tamam düğmesi için tıklama işleyicisi yöntemi artık ekleyeceğiz. Tıklayın **kaynak görünümü** sekmesi. Kaynak Görünümü'nde çift tıklayarak `IDD_MFC01_DIALOG`. Kaynak Düzenleyicisi'nde iletişim kaynakları görünür. Ardından Tamam düğmesine çift tıklayın...

İşleyicisi aşağıdaki gibi tanımlayın.

```
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example"></a>Örnek

Ve BOOL CMFC01Dlg::OnInitDialog() uygulanması için aşağıdaki satırı ekleyin.

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

Artık, derleme ve uygulamayı çalıştırın. Uygulama kapandığında herhangi bir metin metin kutusundaki bir açılır ileti kutusunda görüntülenir dikkat edin.

## <a name="see-also"></a>Ayrıca Bkz.

[CWinFormsControl Sınıfı](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)