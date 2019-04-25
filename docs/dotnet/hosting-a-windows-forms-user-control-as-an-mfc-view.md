---
title: MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
ms.openlocfilehash: 9c59f28739ab94210c16bd800a48997f3f2282df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222877"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma

MFC CWinFormsView sınıfı MFC görünümü olarak bir Windows Forms kullanıcı denetimini barındırmak için kullanır. MFC Windows Forms ActiveX denetimlerini görünümleridir. Kullanıcı denetimi yerel görünümün alt sitesi olarak barındırılan ve yerel görünümün tüm istemci alanını kaplar.

Sonuç modeli tarafından kullanılan benzer [CFormView sınıfı](../mfc/reference/cformview-class.md). Bu Windows Form Tasarımcısı ve çalışma zamanı form tabanlı zengin görünümler oluşturmak için avantajlarından yararlanmanıza imkan sağlar.

MFC Windows formlar görünümlerini ActiveX denetimlerini olduğundan, aynı olmadığı `hwnd` MFC görünüm olarak. Ayrıca bunlar için bir işaretçi olarak geçirilemez bir [CView](../mfc/reference/cview-class.md) görünümü. Genel olarak, daha az Win32 kullanır ve Windows Forms görünümlerle çalışma için .NET Framework yöntemlerini kullanın.

MFC'de Windows formlarını gösteren örnek bir uygulama için bkz. [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

## <a name="in-this-section"></a>Bu Bölümde

[Nasıl yapılır: Kullanıcı Denetimi ve Konak MDI Görünümü Oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[Nasıl yapılır: Windows Forms Denetimine Yönlendiren Komut Ekleme](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[Nasıl yapılır: Windows Forms Denetiminin Çağrı Özellikleri ve Yöntemleri](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC içinde Windows Formu Kullanıcı Denetimi Kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Nasıl yapılır: Bileşik denetimler yazma](/dotnet/framework/winforms/controls/how-to-author-composite-controls)
