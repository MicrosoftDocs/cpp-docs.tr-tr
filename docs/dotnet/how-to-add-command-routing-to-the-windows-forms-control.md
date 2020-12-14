---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: Windows Forms denetimine komut yönlendirmesi ekleme'
title: "Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme"
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: b46087d7df3da5f402432731db4b994b257a385b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335416"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme

[CWinFormsView](../mfc/reference/cwinformsview-class.md) komutları ve Update-Command UI ILETILERINI, MFC komutlarının (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemesini sağlamak için Kullanıcı denetimine yönlendirir.

Kullanıcı denetimi, aşağıdaki örnekte gösterildiği gibi ' de komut kaynak nesnesine bir başvuru depolamak için [ICommandText](../mfc/reference/icommandtarget-interface.md#initialize) ' i kullanır `m_CmdSrc` . Kullanmak için `ICommandTarget` mfcmifc80.dll bir başvuru eklemeniz gerekir.

`CWinFormsView` yönetilen Kullanıcı denetimine ileterek ortak MFC görünüm bildirimlerinin birkaçını işler. Bu bildirimler [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate), [OnUpdate](../mfc/reference/iview-interface.md#onupdate) ve [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) yöntemlerini içerir.

Bu konu başlığı altında [, bir Iletişim kutusunda Kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) ve [nasıl yapılır: Kullanıcı denetımı ve Konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)hakkında daha önceden tamamladığınız varsayılmaktadır.

### <a name="to-create-the-mfc-host-application"></a>MFC ana bilgisayar uygulaması oluşturmak için

1. [Nasıl yapılır: bir Iletişim kutusunda Kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)bölümünde oluşturduğunuz Windows Forms denetim kitaplığını açın.

1. **Çözüm Gezgini**' de proje düğümüne sağ tıklayıp **Ekle**, **başvuru** ve Microsoft Visual Studio 10.0 \ Vc\atlmfc\liböğesine göz atarak mfcmifc80.dll bir başvuru ekleyin.

1. UserControl1.Designer.cs açın ve aşağıdaki using ifadesini ekleyin:

    ```
    using Microsoft.VisualC.MFC;
    ```

1. Ayrıca, UserControl1.Designer.cs içinde şu satırı değiştirin:

    ```
    partial class UserControl1
    ```

   şu şekilde:

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. Bunu için sınıf tanımının ilk satırı olarak ekleyin `UserControl1` :

    ```
    private ICommandSource m_CmdSrc;
    ```

1. Aşağıdaki yöntem tanımlarını öğesine ekleyin `UserControl1` (bir sonraki ADıMDA MFC DENETIMININ kimliğini oluşturacağız):

    ```
    public void Initialize (ICommandSource cmdSrc)
    {
       m_CmdSrc = cmdSrc;
       // need ID of control in MFC dialog and callback function
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));
    }

    private void singleMenuHandler (uint cmdUI)
    {
       // User command handler code
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");
    }
    ```

1. [Nasıl yapılır: Kullanıcı denetimi ve Konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)bölümünde oluşturduğunuz mfc uygulamasını açın.

1. Çağıracağı bir menü seçeneği ekleyin `singleMenuHandler` .

   **Kaynak görünümü** gidin (Ctrl + Shift + E), **menü** klasörünü genişletin ve ardından **IDR_MFC02TYPE**' e çift tıklayın. Bu, menü düzenleyicisini görüntüler.

   **Görünüm** menüsünün alt kısmına bir menü seçeneği ekleyin. **Özellikler** penceresinde menü seçeneğinin kimliğine dikkat edin. Dosyayı kaydedin.

   **Çözüm Gezgini**, Resource. h dosyasını açın, yeni eklediğiniz menü seçeneğinin kimlik değerini kopyalayın ve bu değeri `m_CmdSrc.AddCommandHandler` C# projesinin `Initialize` yönteminde (gerekirse değiştirme) çağrıya ilk parametre olarak yapıştırın `32771` .

1. Projeyi derleyin ve çalıştırın.

   **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın.

   Eklediğiniz menü seçeneğini belirleyin. . Dll içindeki yöntemin çağırdığına dikkat edin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[ICommandSource arabirimi](../mfc/reference/icommandsource-interface.md)<br/>
[ICommandTarget arabirimi](../mfc/reference/icommandtarget-interface.md)
