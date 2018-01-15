---
title: "MFC'de Form kullanıcı denetimi Windows kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 1/08/2018
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
ms.openlocfilehash: a3289509c0cfe6016fcace34c76f145a505ecf3b
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2018
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>MFC içinde Windows Formu Kullanıcı Denetimi Kullanma

MFC Windows Forms destek sınıflarını kullanarak, MFC iletişim kutuları veya görünümler içinde bir ActiveX denetimi olarak Windows Forms denetimlerini MFC uygulamalarınız içinde barındırabilir. Ayrıca, Windows Forms forms MFC iletişim kutuları olarak barındırılabilir.

Aşağıdaki bölümlerde nasıl yapılır:

- MFC iletişim kutusunda Windows Forms denetimi barındırma.

- MFC görünümü olarak Windows Forms kullanıcı denetimi barındırma.

- MFC iletişim kutusu olarak Windows Forms form barındırır.

> [!NOTE]
> MFC Windows Forms tümleştirme çalışır, ile MFC'ye dinamik olarak projelerde (hangi projelerinde `_AFXDLL` tanımlanır).

> [!NOTE]
> MFC Windows Forms arabirimi DLL (mfcmifc80.dll)'in) özel (değiştirilmiş) bir kopyasını kullanarak uygulamanızı oluşturma sırasında Microsoft anahtarı kendi satıcı anahtarınızla değiştirin sürece GAC'de yükleme başarısız olur. Derleme imzalama hakkında daha fazla bilgi için bkz: [Derlemelerle programlama](/dotnet/framework/app-domains/programming-with-assemblies) ve [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Windows Forms kullanarak örnek uygulamaları için bkz: [BirthdayPicker örnek: Windows Forms ile .NET Framework kaynakları gösteren](http://msdn.microsoft.com/ac932aed-5502-4667-be29-709bca435317), [hesaplayıcı örnek: Windows Forms Pocket hesaplayıcı](http://msdn.microsoft.com/2283b516-3b7e-45f2-80c4-fdcfb366ce25)ve [ Karalama örnek: MDI çizim uygulama](http://msdn.microsoft.com/f025da3e-659b-4222-b991-554a1b8b2358).

MFC'de Windows Forms gösteren örnek bir uygulama için bkz: [MFC ve Windows Forms tümleştirme](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

MFC uygulamanız Windows Forms kullanıyorsa, uygulamanız ile mfcmifc80.dll'ye yeniden dağıtmanız gerekir. Daha fazla bilgi için bkz: [MFC kitaplığını yeniden dağıtma](../ide/redistributing-the-mfc-library.md).

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

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)  
[Form görünümleri](../mfc/form-views-mfc.md)  
