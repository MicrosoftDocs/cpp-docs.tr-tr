---
title: Bir Windows barındırma Form MFC iletişim kutusunda kullanıcı denetimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 291c0856e9d305e0b2b31c6bc233005b111592a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129443"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma
MFC ActiveX denetimi özel bir tür olarak bir Windows Forms denetimi barındırır ve denetimle ActiveX arabirimleri ve özelliklerini ve yöntemlerini kullanarak iletişim kurar <xref:System.Windows.Forms.Control> sınıfı. Denetim üzerinde çalışması için .NET Framework özellikleri ve yöntemleri kullanmanızı öneririz.  
  
 MFC'de Windows Forms gösteren örnek bir uygulama için bkz: [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
> [!NOTE]
>  Geçerli sürümde, bir `CDialogBar` nesnesi Windows Forms denetimlerini barındıramaz.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: İletişim Kutusunda Kullanıcı Denetimi Ve Konak Oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [Nasıl yapılır: Windows Forms ile DDX/DDV veri bağlaması yapma](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)  
  
## <a name="reference"></a>Başvuru  
 [Ddx_managedcontrol sınıfı](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog sınıfı](../mfc/reference/cdialog-class.md) &#124; [CWnd sınıfı](../mfc/reference/cwnd-class.md)&#124; <xref:System.Windows.Forms.Control>  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC içinde Windows formu kullanıcı denetimi kullanma](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows Forms/MFC programlama farkları](../dotnet/windows-forms-mfc-programming-differences.md)   
 [MFC görünümü olarak Windows Forms kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)