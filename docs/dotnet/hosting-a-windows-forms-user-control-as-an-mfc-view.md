---
title: Barındırma bir Windows Forms kullanıcı denetimi MFC görünümü olarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf9e54b3e2808a232bc13052c885a341cb51297f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma
MFC MFC görünümü olarak Windows Forms kullanıcı denetimi barındırma CWinFormsView sınıfını kullanır. MFC Windows Forms ActiveX denetimlerini görünümlerdir. Kullanıcı denetimi doğal görünümün alt sitesi olarak barındırılan ve yerel görünümün tüm istemci alanı kaplar.  
  
 Tarafından kullanılan model sonuç benzer [Cformview'yu sınıfı](../mfc/reference/cformview-class.md). Bu, Windows Form Tasarımcısı ve çalışma zamanı zengin form tabanlı görünümler oluşturmak için yararlanmanızı sağlar.  
  
 MFC Windows Forms görünümleri ActiveX denetimleri olduğundan, aynı olmadığı `hwnd` MFC görünümleri olarak. Ayrıca, bir işaretçi olarak geçirilemez bir [CView](../mfc/reference/cview-class.md) görünümü. Genel olarak, daha az Win32 kullanır ve Windows Forms görünümlerle çalışma için .NET Framework yöntemlerini kullanın.  
  
 MFC'de Windows Forms gösteren örnek bir uygulama için bkz: [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: Kullanıcı Denetim ve Konak MDI Görünümü Oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [Nasıl yapılır: Windows Forms Denetiminin Çağrı Özellikleri ve Yöntemleri](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC içinde Windows formu kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Nasıl yapılır: Bileşik Denetimler Yazma](/dotnet/framework/winforms/controls/how-to-author-composite-controls)