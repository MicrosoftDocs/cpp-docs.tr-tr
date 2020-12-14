---
description: 'Hakkında daha fazla bilgi edinin: MFC Iletişim kutusunda Windows form kullanıcı denetimi barındırma'
title: MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 3ccfbb32132f5732c244473c652bb6b2df175efa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335443"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma

MFC bir Windows Forms denetimini özel bir ActiveX denetimi olarak barındırır ve ActiveX arabirimlerini kullanarak denetimle iletişim kurar ve sınıfın özellikleri ve yöntemleri <xref:System.Windows.Forms.Control> . Denetim üzerinde çalışmak için .NET Framework özellikleri ve yöntemleri kullanmanızı öneririz.

MFC ile kullanılan Windows Forms gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirmesi](https://www.microsoft.com/download/details.aspx?id=2113).

> [!NOTE]
> Geçerli sürümde, bir `CDialogBar` nesne Windows Forms denetimleri barındıramaz.

## <a name="in-this-section"></a>Bu Bölümde

[Nasıl yapılır: Iletişim kutusunda Kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[Nasıl yapılır: Windows Forms ile DDX/DDV veri bağlamayı yapma](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[Nasıl yapılır: Yerel C++ Sınıflarından Windows Forms olaylarını havuza alma](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>Başvuru

[CWnd sınıfı](../mfc/reference/cwnd-class.md) &#124; [cdialog](../mfc/reference/cdialog-class.md) sınıfı &#124; [CWinFormsControl sınıfı](../mfc/reference/cwinformscontrol-class.md) &#124;<xref:System.Windows.Forms.Control>

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Windows formu Kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Windows Forms/MFC programlama farkları](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[MFC Iletişim kutusu olarak Windows formu Kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
