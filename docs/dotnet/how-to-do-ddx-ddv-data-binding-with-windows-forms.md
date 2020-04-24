---
title: 'Nasıl yapılır: Windows Formları ile DDX-DDV Veri Bağlama yapın'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: 31629a4db2559112ba49f5c069b08de7abdfc2db
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754353"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Nasıl yapılır: Windows Forms ile DDX/DDV Veri Bağlaması Yapma

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) [CWinFormsControl çağırır::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) kaynak denetim kimliği eşleşen bir denetim oluşturmak için. Denetim `DDX_ManagedControl` `CWinFormsControl` için kullanıyorsanız (sihirbaz tarafından oluşturulan kodda), `CreateManagedControl` aynı denetim için açıkça aramamalısınız.

Kaynak `DDX_ManagedControl` aramalarından denetimler oluşturmak için [CWnd::DoDataExchange'i](../mfc/reference/cwnd-class.md#dodataexchange) arayın. Veri alışverişi için Windows Forms denetimleri ile DDX/DDV işlevlerini kullanmanız gerekmez. Bunun yerine, aşağıdaki örnekte olduğu gibi, iletişim `DoDataExchange` (veya görünüm) sınıfının yönteminde yönetilen denetim özelliklerine erişmek için kod yerleştirebilirsiniz.

Aşağıdaki örnek, yerel bir C++ dizesini bir .NET kullanıcı denetimine nasıl bağlanıntığını gösterir.

## <a name="example"></a>Örnek

Aşağıda, bir MFC dizesinin `m_str` .NET kullanıcı denetiminin kullanıcı tanımlı `NameText` özelliğiyle DDX/DDV veri bağlamasının bir örneği verilmiştir.

Denetim, [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) ilk `CMyDlg::DoDataExchange` kez aradığında oluşturulur, bu `m_UserControl` nedenle başvuruyapan `DDX_ManagedControl` herhangi bir kodun çağrıdan sonra gelmesi gerekir.

Bu kodu, nasıl oluşturulur: [Kullanıcı Denetimini ve Ana Bilgisayar'ı Bir İletişim Kutusunda Oluşturma'da](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)oluşturduğunuz MFC01 uygulamasında uygulayabilirsiniz.

CMFC01Dlg bildirimine aşağıdaki kodu koyun:

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example"></a>Örnek

CMFC01Dlg uygulamasında aşağıdaki kodu koyun:

```cpp
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

Şimdi Tamam düğmesine bir tıklama için işleyici yöntemi ni ekleyeceğiz. Kaynak **Görünümü** sekmesini tıklatın. Kaynak Görünümü'nde çift `IDD_MFC01_DIALOG`tıklatın. İletişim kaynağı Kaynak Düzenleyicisi'nde görünür. Ardından Tamam düğmesine çift tıklayın...

Işleyiciyi aşağıdaki gibi tanımlayın.

```cpp
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example"></a>Örnek

Ve BOOL CMFC01Dlg uygulanmasına aşağıdaki satırı ekleyin::OnInitDialog().

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

Artık uygulamayı derleyebilir ve çalıştırabilirsiniz. Uygulama kapandığında metin kutusundaki herhangi bir metnin açılır ileti kutusunda görüntüleneceğine dikkat edin.

## <a name="see-also"></a>Ayrıca bkz.

[CWinFormsControl Sınıfı](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)
