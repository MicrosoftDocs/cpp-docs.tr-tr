---
title: MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 8925b86a5920df6a53a2625b782cf41e1a7fe32c
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73964962"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma

MFC bir Windows Forms denetimini özel bir ActiveX denetimi olarak barındırır ve ActiveX arabirimlerini ve <xref:System.Windows.Forms.Control> sınıfının özelliklerini ve yöntemlerini kullanarak denetimle iletişim kurar. Denetim üzerinde çalışmak için .NET Framework özellikleri ve yöntemleri kullanmanızı öneririz.

MFC ile kullanılan Windows Forms gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirmesi](https://www.microsoft.com/download/details.aspx?id=2113).

> [!NOTE]
>  Geçerli sürümde, bir `CDialogBar` nesnesi Windows Forms denetimleri barındıraamaz.

## <a name="in-this-section"></a>Bu Bölümde

[Nasıl yapılır: İletişim Kutusunda Kullanıcı Denetimi Ve Konak Oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[Nasıl yapılır: Windows Forms ile DDX/DDV veri bağlamayı yapma](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>Başvuru

[CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog](../mfc/reference/cdialog-class.md) &#124; sınıfı [CWnd](../mfc/reference/cwnd-class.md) &#124; sınıfı <xref:System.Windows.Forms.Control>

## <a name="see-also"></a>Ayrıca bkz.

[MFC içinde Windows Formu Kullanıcı Denetimi Kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Windows Forms/MFC programlama farkları](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
