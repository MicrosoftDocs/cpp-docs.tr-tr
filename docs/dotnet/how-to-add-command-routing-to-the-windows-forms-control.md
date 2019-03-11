---
title: 'Nasıl yapılır: Ekle komutu yönlendirme için bir Windows Forms denetimi'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: 8f633cf744314833409a3ffeacf8c850429e099c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750304"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>Nasıl yapılır: Ekle komutu yönlendirme için bir Windows Forms denetimi

[CWinFormsView](../mfc/reference/cwinformsview-class.md) komutları yönlendirir ve güncelleştirme komut UI iletilerini MFC komutlarını (örneğin, çerçeve menüsü ögeleri ve araç çubuğu düğmeleri) işlemelerine izin vermek için kullanıcı denetimi.

Kullanıcı denetimini kullanan [ICommandTarget::Initialize'ı](../mfc/reference/icommandtarget-interface.md#initialize) öğesindeki komut kaynak nesnesine bir başvuru depolamak için `m_CmdSrc`, aşağıdaki örnekte gösterildiği gibi. Kullanılacak `ICommandTarget` mfcmifc80.dll'ye bir başvuru eklemeniz gerekir.

`CWinFormsView` birkaç genel MFC görünüm bildirimlerini, bunları yönetilen kullanıcı denetimine ileterek işler. Bu bildirimler [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate), [OnUpdate](../mfc/reference/iview-interface.md#onupdate) ve [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) yöntemleri.

Bu konuda daha önce bitirdiğinizi [nasıl yapılır: Bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) ve [nasıl yapılır: Kullanıcı denetim ve konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için

1. Oluşturduğunuz Windows Forms Denetim Kitaplığı açın [nasıl yapılır: Bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

1. ' Nde proje düğümüne sağ tıklayarak bunu yapabilirsiniz, mfcmifc80.dll'ye bir başvuru ekleyin **Çözüm Gezgini**u seçerek **Ekle**, **başvuru**, öğesine göz atarak Microsoft Visual Studio 10.0\VC\atlmfc\lib.

1. UserControl1.Designer.cs açın ve aşağıdaki deyimi kullanarak:

    ```
    using Microsoft.VisualC.MFC;
    ```

1. Ayrıca, UserControl1.Designer.cs'te şu satırı değiştirin:

    ```
    partial class UserControl1
    ```

   Şu şekilde:

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. Bu sınıf tanımının ilk satırı olarak ekleyin `UserControl1`:

    ```
    private ICommandSource m_CmdSrc;
    ```

1. Eklemek için aşağıdaki yöntem tanımlarını `UserControl1` (MFC denetiminin Kimliğini sonraki adımda oluşturacağız):

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

1. Oluşturduğunuz MFC uygulamasını açınız [nasıl yapılır: Kullanıcı denetim ve konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

1. Açacak bir menü seçeneği ekleyin `singleMenuHandler`.

   Git **kaynak görünümü** (Ctrl + SHIFT + E) genişletin **menü** klasörüne gittikten sonra çift tıklayarak **IDR_MFC02TYPE**. Bu, menü düzenleyicisini görüntüler.

   Alt kısmındaki menü seçeneği ekleyin **görünümü** menüsü. Menü seçeneğinin Kimliğine dikkat edin **özellikleri** penceresi. Dosyayı kaydedin.

   İçinde **Çözüm Gezgini**, Resource.h dosyasını açın, yeni eklediğiniz menü seçeneğinin kimlik değerini kopyalayın ve bu değer, ilk parametresi olarak yapıştırın `m_CmdSrc.AddCommandHandler` C# projesinin çağrı `Initialize` ( değiştirerekyöntemi`32771` gerekiyorsa).

9. Derleme ve projeyi çalıştırın.

   Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

   Üzerinde **hata ayıklama** menüsünü tıklatın **hata ayıklama olmadan Başlat**.

   Eklediğiniz menü seçeneğini belirleyin. . Ddl'deki yöntemin çağrıldığına dikkat edin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[ICommandSource Arabirimi](../mfc/reference/icommandsource-interface.md)<br/>
[ICommandTarget Arabirimi](../mfc/reference/icommandtarget-interface.md)
