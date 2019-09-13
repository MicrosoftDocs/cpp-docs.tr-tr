---
title: MFC içinde Windows Formu Kullanıcı Denetimi Kullanma
ms.date: 01/08/2018
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
ms.openlocfilehash: efabbf84778d925ec1de03f5f4ea0ca09185bd81
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926054"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>MFC içinde Windows Formu Kullanıcı Denetimi Kullanma

Mfc Windows Forms destek sınıfları kullanarak MFC uygulamalarınızın içindeki Windows Forms denetimleri MFC iletişim kutularında veya görünümlerde ActiveX denetimi olarak barındırabilirsiniz. Ayrıca, Windows Forms formları MFC iletişim kutusu olarak barındırılabilir.

Aşağıdaki bölümlerde aşağıdakilerin nasıl yapılacağı açıklanır:

- MFC iletişim kutusunda bir Windows Forms denetimi barındırın.

- Bir Windows Forms Kullanıcı denetimini MFC görünümü olarak barındırın.

- MFC iletişim kutusu olarak bir Windows Forms formu barındırın.

> [!NOTE]
> Mfc Windows Forms tümleştirmesi yalnızca MFC ile dinamik olarak bağlanan projelerde (tanımlı projeler `_AFXDLL` ) kullanılabilir.

> [!NOTE]
> Uygulamanızı MFC Windows Forms arabirimleri DLL (mfcmifc80. dll) ' nin özel (değiştirilmiş) kopyasını kullanarak oluşturduğunuzda, Microsoft anahtarını kendi satıcı anahtarınızla değiştirmediğiniz takdirde GAC 'de yüklenemeyecektir. Derleme imzalama hakkında daha fazla bilgi için bkz. [programlama, derlemeler](/dotnet/framework/app-domains/programming-with-assemblies) ve [tanımlayıcı ad derlemeleri (derleme imzalama)C++(/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

MFC uygulamanız Windows Forms kullanıyorsa, mfcmifc80. dll ' yi uygulamanızla yeniden dağıtmanız gerekir. Daha fazla bilgi için bkz. [MFC kitaplığını yeniden dağıtma](../windows/redistributing-the-mfc-library.md).

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

[UICheckState](../mfc/reference/uicheckstate-enumeration.md)

## <a name="related-sections"></a>İlgili Bölümler

[Windows Forms](/dotnet/framework/winforms/index)

[Windows Forms Denetimleri](/dotnet/framework/winforms/controls/index)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[Form görünümleri](../mfc/form-views-mfc.md)
