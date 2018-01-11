---
title: "MFC'de Form kullanıcı denetimi Windows kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 59b4d974a6b25b896067bce0042d9a5ff9221cc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>MFC içinde Windows Formu Kullanıcı Denetimi Kullanma
MFC Windows Forms destek sınıflarını kullanarak, MFC iletişim kutuları veya görünümler içinde bir ActiveX denetimi olarak Windows Forms denetimlerini MFC uygulamalarınız içinde barındırabilir. Ayrıca, Windows Forms forms MFC iletişim kutuları olarak barındırılabilir.  
  
 Aşağıdaki bölümlerde nasıl yapılır:  
  
-   MFC iletişim kutusunda Windows Forms denetimi barındırma.  
  
-   MFC görünümü olarak Windows Forms kullanıcı denetimi barındırma.  
  
-   MFC iletişim kutusu olarak Windows Forms form barındırır.  
  
> [!NOTE]
>  MFC Windows Forms tümleştirme çalışır, ile MFC'ye dinamik olarak projelerde (Proje AFXDLL tanımlanır).  
  
> [!NOTE]
>  MFC Windows Forms arabirimi DLL (mfcmifc80.dll)'in) özel (değiştirilmiş) bir kopyasını kullanarak uygulamanızı oluşturma sırasında Microsoft anahtarı kendi satıcı anahtarınızla değiştirin sürece GAC'de yükleme başarısız olur. Derleme imzalama hakkında daha fazla bilgi için bkz: [Derlemelerle programlama](/dotnet/framework/app-domains/programming-with-assemblies) ve [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Windows Forms kullanarak örnek uygulamaları için bkz: [BirthdayPicker örnek: Windows Forms ile .NET Framework kaynakları gösteren](http://msdn.microsoft.com/en-us/ac932aed-5502-4667-be29-709bca435317), [hesaplayıcı örnek: Windows Forms Pocket hesaplayıcı](http://msdn.microsoft.com/en-us/2283b516-3b7e-45f2-80c4-fdcfb366ce25)ve [ Karalama örnek: MDI çizim uygulama](http://msdn.microsoft.com/en-us/f025da3e-659b-4222-b991-554a1b8b2358).  
  
 MFC'de Windows Forms gösteren örnek bir uygulama için bkz: [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
 MFC uygulamanız Windows Forms kullanıyorsa, uygulamanız ile mfcmifc90.dll yeniden dağıtmanız gerekir. Daha fazla bilgi için bkz: [MFC kitaplığını yeniden dağıtma](../ide/redistributing-the-mfc-library.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [MFC İletişim Kutusunda Windows Form Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)  
  
 [MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)  
  
 [MFC İletişim Kutusu Olarak Windows Formu Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)  
  
## <a name="reference"></a>Başvuru  
 [CWinFormsControl Sınıfı](../mfc/reference/cwinformscontrol-class.md)  
  
 [CWinFormsDialog Sınıfı](../mfc/reference/cwinformsdialog-class.md)  
  
 [CWinFormsView Sınıfı](../mfc/reference/cwinformsview-class.md)  
  
 [ICommandSource Arabirimi](../mfc/reference/icommandsource-interface.md)  
  
 [ICommandTarget Arabirimi](../mfc/reference/icommandtarget-interface.md)  
  
 [ICommandUI Arabirimi](../mfc/reference/icommandui-interface.md)  
  
 [IView Arabirimi](../mfc/reference/iview-interface.md)  
  
 [CommandHandler](../atl/commandhandler.md)  
  
 [DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)  
  
 [Uıcheckstate](../mfc/reference/uicheckstate-enumeration.md)  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Windows Forms](/dotnet/framework/winforms/index)  
  
 [Windows Forms Denetimleri](/dotnet/framework/winforms/controls/index)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)   
 [Form görünümleri](../mfc/form-views-mfc.md)