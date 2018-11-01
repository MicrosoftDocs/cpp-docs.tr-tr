---
title: MFC içinde Windows Formu Kullanıcı Denetimi Kullanma
ms.date: 1/08/2018
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
ms.openlocfilehash: d36932a3edc0129f0497cb8db4095283650c5c96
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494165"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>MFC içinde Windows Formu Kullanıcı Denetimi Kullanma

MFC Windows Forms desteği sınıfları kullanarak, MFC iletişim kutuları veya görünümler içinde bir ActiveX denetimi Windows Forms denetimleri, MFC uygulamaları içinde barındırabilirsiniz. Ayrıca, Windows Forms formlarını MFC iletişim kutusu olarak barındırılabilir.

Aşağıdaki bölümlerde nasıl yapılır:

- MFC iletişim kutusunda Windows Forms denetimi barındırma.

- MFC görünümü olarak bir Windows Forms kullanıcı denetimi barındırın.

- MFC iletişim kutusu olarak Windows Forms formu barındırın.

> [!NOTE]
> MFC Windows Forms tümleştirme ile MFC'ye dinamik olarak projeleri çalışır (hangi projelerinde `_AFXDLL` tanımlanır).

> [!NOTE]
> MFC Windows Forms arabirimi DLL (mfcmifc80.dll'ye) özel (değiştirilmiş) bir kopyasını kullanarak uygulamanızı oluşturduğunuzda Microsoft anahtarını kendi satıcı anahtarla değiştirin sürece GAC'ye yüklemek başarısız olur. Derleme imzalama hakkında daha fazla bilgi için bkz. [Derlemelerle programlama](/dotnet/framework/app-domains/programming-with-assemblies) ve [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

MFC uygulamanız Windows Forms kullanıyorsa, mfcmifc80.dll'ye uygulamanızla birlikte yeniden dağıtmanız gerekir. Daha fazla bilgi için [MFC kitaplığını yeniden dağıtma](../ide/redistributing-the-mfc-library.md).

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

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[Form görünümleri](../mfc/form-views-mfc.md)
