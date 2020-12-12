---
description: "Hakkında daha fazla bilgi edinin: MFC 'de Windows formu Kullanıcı denetimi kullanma"
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
ms.openlocfilehash: 61022d241faba1650d1a044ef6d3667febe34cde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319033"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>MFC içinde Windows Formu Kullanıcı Denetimi Kullanma

Mfc Windows Forms destek sınıfları kullanarak MFC uygulamalarınızın içindeki Windows Forms denetimleri MFC iletişim kutularında veya görünümlerde ActiveX denetimi olarak barındırabilirsiniz. Ayrıca, Windows Forms formları MFC iletişim kutusu olarak barındırılabilir.

Aşağıdaki bölümlerde aşağıdakilerin nasıl yapılacağı açıklanır:

- MFC iletişim kutusunda bir Windows Forms denetimi barındırın.

- Bir Windows Forms Kullanıcı denetimini MFC görünümü olarak barındırın.

- MFC iletişim kutusu olarak bir Windows Forms formu barındırın.

> [!NOTE]
> MFC Windows Forms tümleştirmesi yalnızca MFC ile dinamik olarak bağlanan projelerde ( `_AFXDLL` tanımlı projeler) kullanılabilir.

> [!NOTE]
> Uygulamanızı MFC Windows Forms arabirimleri DLL 'nin (mfcmifc80.dll) özel (değiştirilmiş) bir kopyasını kullanarak oluşturduğunuzda, Microsoft anahtarını kendi satıcı anahtarınızla değiştirmediğiniz takdirde GAC 'de yüklenemeyecektir. Derleme imzalama hakkında daha fazla bilgi için bkz. [programlama derlemeleri](/dotnet/framework/app-domains/programming-with-assemblies) ve [tanımlayıcı ad derlemeleri (derleme Imzalama) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

MFC uygulamanız Windows Forms kullanıyorsa, mfcmifc80.dll uygulamanızla yeniden dağıtmanız gerekir. Daha fazla bilgi için bkz. [MFC kitaplığını yeniden dağıtma](../windows/redistributing-the-mfc-library.md).

## <a name="in-this-section"></a>Bu Bölümde

[MFC Iletişim kutusunda Windows form kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)

[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

[MFC Iletişim kutusu olarak Windows formu Kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="reference"></a>Başvuru

[CWinFormsControl sınıfı](../mfc/reference/cwinformscontrol-class.md)

[CWinFormsDialog sınıfı](../mfc/reference/cwinformsdialog-class.md)

[CWinFormsView sınıfı](../mfc/reference/cwinformsview-class.md)

[ICommandSource arabirimi](../mfc/reference/icommandsource-interface.md)

[ICommandTarget arabirimi](../mfc/reference/icommandtarget-interface.md)

[Iommanduı arabirimi](../mfc/reference/icommandui-interface.md)

[IView arabirimi](../mfc/reference/iview-interface.md)

[CommandHandler](../atl/commandhandler.md)

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)

[UICheckState](../mfc/reference/uicheckstate-enumeration.md)

## <a name="related-sections"></a>İlgili Bölümler

[Windows Forms](/dotnet/framework/winforms/index)

[Windows Forms denetimleri](/dotnet/framework/winforms/controls/index)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[Form görünümleri](../mfc/form-views-mfc.md)
