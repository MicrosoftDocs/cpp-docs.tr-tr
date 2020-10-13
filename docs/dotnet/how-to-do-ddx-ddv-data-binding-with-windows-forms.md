---
title: 'Nasıl yapılır: Windows Forms ile DDX-DDV veri bağlaması yapma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: a0759eba1c55e72f2c0a99964b0b2d254df82a25
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008314"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Nasıl yapılır: Windows Forms ile DDX/DDV Veri Bağlaması Yapma

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) , kaynak denetimi kimliğiyle eşleşen bir denetim oluşturmak için [CWinFormsControl:: CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) çağırır. `DDX_ManagedControl`Bir denetim için kullanıyorsanız `CWinFormsControl` (sihirbaz tarafından oluşturulan kodda), `CreateManagedControl` aynı denetim için açıkça çağırmamalıdır.

`DDX_ManagedControl`Kaynak kimliklerinden denetim oluşturmak Için [CWnd::D oDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) içinde çağrı. Veri değişimi için, Windows Forms denetimleriyle DDX/DDV işlevlerini kullanmanız gerekmez. Bunun yerine, `DoDataExchange` Aşağıdaki örnekte olduğu gibi iletişim kutusu (veya Görünüm) sınıfınızın yönteminde yönetilen denetimin özelliklerine erişmek için kod yerleştirebilirsiniz.

Aşağıdaki örnekte, yerel C++ dizesinin bir .NET Kullanıcı denetimine nasıl bağlanacağı gösterilmektedir.

## <a name="example-ddxddv-data-binding"></a>Örnek: DDX/DDV veri bağlama

Aşağıda `m_str` .NET Kullanıcı denetiminin Kullanıcı tanımlı özelliği ile BIR MFC DIZESININ DDX/DDV veri bağlamasının bir örneği verilmiştir `NameText` .

Denetim, [CDialog:: OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) ilk kez aradığında oluşturulur `CMyDlg::DoDataExchange` . bu nedenle, başvuruda bulunan tüm kodlar `m_UserControl` çağrıdan sonra gelmelidir `DDX_ManagedControl` .

Bu kodu, [nasıl yapılır: bir Iletişim kutusunda Kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)bölümünde oluşturduğunuz MFC01 uygulamasında uygulayabilirsiniz.

Aşağıdaki kodu CMFC01Dlg bildirimine koyun:

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example-implement-dodataexchange"></a>Örnek: DoDataExchange () uygulayın

Aşağıdaki kodu CMFC01Dlg uygulamasına koyun:

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

## <a name="example-add-handler-method"></a>Örnek: Add Handler yöntemi

Şimdi Tamam düğmesine tıklama için işleyici yöntemi ekleyeceğiz. **Kaynak görünümü** sekmesine tıklayın. Kaynak Görünümü ' de, üzerine çift tıklayın `IDD_MFC01_DIALOG` . İletişim kaynağı kaynak Düzenleyicisi ' nde görünür. Ardından Tamam düğmesine çift tıklayın.

İşleyiciyi aşağıdaki gibi tanımlayın.

```cpp
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example-set-the-textbox-text"></a>Örnek: metin kutusu metnini ayarlama

Ve BOOL CMFC01Dlg:: OnInitDialog () uygulamasına aşağıdaki satırı ekleyin.

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

Artık uygulamayı derleyebilir ve çalıştırabilirsiniz. Metin kutusundaki tüm metinlerin, uygulama kapandığında açılan bir ileti kutusunda görüntülendiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[CWinFormsControl sınıfı](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::D oDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)
