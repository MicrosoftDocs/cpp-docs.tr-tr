---
title: MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 921e6fac32d37f8976d53d49adab72fb27ab5e99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632225"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma

MFC ActiveX denetimi özel bir tür bir Windows Forms denetimi barındıran ve ActiveX arabirimleri ve özellikleri ve yöntemleri kullanarak denetimi ile iletişim kuran <xref:System.Windows.Forms.Control> sınıfı. Denetim üzerinde çalışmaları için .NET Framework özellikleri ve yöntemleri kullanmanızı öneririz.

MFC'de Windows formlarını gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

> [!NOTE]
>  Geçerli sürümde, bir `CDialogBar` nesne, Windows Forms denetimleri barındıramaz.

## <a name="in-this-section"></a>Bu Bölümde

[Nasıl yapılır: İletişim Kutusunda Kullanıcı Denetimi Ve Konak Oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[Nasıl yapılır: Windows Forms ile DDX/DDV veri bağlaması yapma](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>Başvuru

[CWinFormsControl sınıfı](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog sınıfı](../mfc/reference/cdialog-class.md) &#124; [CWnd sınıfı](../mfc/reference/cwnd-class.md)&#124; <xref:System.Windows.Forms.Control>

## <a name="see-also"></a>Ayrıca Bkz.

[MFC içinde Windows Formu Kullanıcı Denetimi Kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Windows Forms/MFC programlama farkları](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)