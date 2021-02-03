---
description: 'Hakkında daha fazla bilgi edinin: Windows Forms Kullanıcı denetimini MFC görünümü olarak barındırma'
title: MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
ms.openlocfilehash: 2db44bd4d85150b0a2b8fc1f2206af765770e9ed
ms.sourcegitcommit: 3987d9c39f5a5b4824303a48a6215984ce8949e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/02/2021
ms.locfileid: "99478154"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma

MFC, bir Windows Forms Kullanıcı denetimini MFC görünümünde barındırmak için CWinFormsView sınıfını kullanır. MFC Windows Forms görünümleri ActiveX denetimleridir. Kullanıcı denetimi yerel görünümün bir alt öğesi olarak barındırılır ve yerel görünümün tüm istemci alanını kaplar.

Nihai sonuç, [CFormView sınıfı](../mfc/reference/cformview-class.md)tarafından kullanılan modele benzer. Bu, zengin form tabanlı görünümler oluşturmak için Windows Forms Tasarımcısı ve çalışma zamanından yararlanmanızı sağlar.

MFC Windows Forms görünümleri ActiveX denetimleri olduğundan, `hwnd` MFC görünümleriyle aynı değildir. Ayrıca, [CView](../mfc/reference/cview-class.md) görünümüne işaretçi olarak geçirilemez. Genel olarak, Windows Forms görünümleriyle çalışmak ve Win32 üzerinde daha az kullanmak için .NET Framework yöntemler kullanın.

MFC ile kullanılan Windows Forms gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirmesi](https://download.cnet.com/MFC-and-WinForms-Integration/3000-2383_4-75453644.html).

## <a name="in-this-section"></a>Bu Bölümde

[Nasıl yapılır: Kullanıcı denetimi ve Konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[Nasıl yapılır: Windows Forms denetimine komut yönlendirmesi ekleme](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[Nasıl yapılır: Windows Forms denetiminin özelliklerini ve yöntemlerini çağırma](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Windows formu Kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Nasıl yapılır: Bileşik Denetimler Yazma](/dotnet/framework/winforms/controls/how-to-author-composite-controls)
