---
title: MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
ms.openlocfilehash: bf91730f98685935d50ee0076739b436e8d9da60
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73964942"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma

MFC, bir Windows Forms Kullanıcı denetimini MFC görünümünde barındırmak için CWinFormsView sınıfını kullanır. MFC Windows Forms görünümleri ActiveX denetimleridir. Kullanıcı denetimi yerel görünümün bir alt öğesi olarak barındırılır ve yerel görünümün tüm istemci alanını kaplar.

Nihai sonuç, [CFormView sınıfı](../mfc/reference/cformview-class.md)tarafından kullanılan modele benzer. Bu, zengin form tabanlı görünümler oluşturmak için Windows Forms Tasarımcısı ve çalışma zamanından yararlanmanızı sağlar.

MFC Windows Forms görünümleri ActiveX denetimleri olduğundan, MFC görünümleriyle aynı `hwnd` sahip değildir. Ayrıca, [CView](../mfc/reference/cview-class.md) görünümüne işaretçi olarak geçirilemez. Genel olarak, Windows Forms görünümleriyle çalışmak ve Win32 üzerinde daha az kullanmak için .NET Framework yöntemler kullanın.

MFC ile kullanılan Windows Forms gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirmesi](https://www.microsoft.com/download/details.aspx?id=2113).

## <a name="in-this-section"></a>Bu Bölümde

[Nasıl yapılır: Kullanıcı Denetim ve Konak MDI Görünümü Oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[Nasıl yapılır: Windows Forms Denetiminin Çağrı Özellikleri ve Yöntemleri](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC içinde Windows Formu Kullanıcı Denetimi Kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Nasıl yapılır: Bileşik Denetimler Yazma](/dotnet/framework/winforms/controls/how-to-author-composite-controls)
