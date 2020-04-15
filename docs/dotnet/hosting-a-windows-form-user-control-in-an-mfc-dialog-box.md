---
title: MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 2704e04df3792edfee6c39f597fcbe71b6ce51b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374492"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma

MFC, özel bir ActiveX denetimi olarak bir Windows Forms denetimini barındırır ve ActiveX arabirimlerini, sınıfın özelliklerini ve yöntemlerini <xref:System.Windows.Forms.Control> kullanarak denetimle iletişim kurar. Denetimi çalıştırmak için .NET Framework özelliklerini ve yöntemlerini kullanmanızı öneririz.

MFC ile kullanılan Windows Formlarını gösteren örnek bir uygulama için [MFC ve Windows Forms Tümleştirme'ye](https://www.microsoft.com/download/details.aspx?id=2113)bakın.

> [!NOTE]
> Geçerli sürümde, `CDialogBar` bir nesne Windows Forms denetimlerini barındıramaz.

## <a name="in-this-section"></a>Bu Bölümde

[Nasıl yapılır: İletişim Kutusunda Kullanıcı Denetimi Ve Konak Oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[Nasıl yapılır: Windows Forms ile DDX/DDV Veri Bağlaması Yapma](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>Başvuru

[CWinFormsControl Sınıf](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog Sınıf](../mfc/reference/cdialog-class.md) &#124; [CWnd Sınıf](../mfc/reference/cwnd-class.md) &#124;<xref:System.Windows.Forms.Control>

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Form Kullanıcı Denetimi Kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Windows Forms/MFC Programlama Farkları](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Windows Form Kullanıcı Denetimini MFC İletişim Kutusu Olarak Barındırma](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
