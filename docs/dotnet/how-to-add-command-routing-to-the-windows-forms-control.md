---
title: "Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme"
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: ad64a12051c22a0cfca99d3ec9c5abef579902f4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365166"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme

[CWinFormsView,](../mfc/reference/cwinformsview-class.md) MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemesine izin vermek için komutları ve güncelleştirme komutu kullanıcı iletilerini kullanıcı denetimine yönlendirir.

Kullanıcı denetimi, aşağıdaki örnekte gösterildiği gibi komut kaynağı nesnesine `m_CmdSrc`bir başvuru depolamak için [ICommandTarget::Initialize](../mfc/reference/icommandtarget-interface.md#initialize) kullanır. Kullanmak `ICommandTarget` için mfcmifc80.dll bir referans eklemeniz gerekir.

`CWinFormsView`ortak MFC görünüm bildirimlerinden birkaçını yönetilen kullanıcı denetimine ileterek işler. Bu bildirimler [OnInitialUpdate,](../mfc/reference/iview-interface.md#oninitialupdate) [OnUpdate](../mfc/reference/iview-interface.md#onupdate) ve [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) yöntemlerini içerir.

Bu konu, daha önce [nasıl](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) tamamladığınızı varsayar: İletişim Kutusunda Kullanıcı Denetimi ve Ana Bilgisayar Oluşturma ve Nasıl [Oluştur: Kullanıcı Denetimi ve Ana Bilgisayar MDI Görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

### <a name="to-create-the-mfc-host-application"></a>MFC ana bilgisayar uygulamasını oluşturmak için

1. Nasıl Yapılır: [İletişim Kutusunda Kullanıcı Denetimi ve Ana Bilgisayar Oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)'da oluşturduğunuz Windows Forms Control Kitaplığını açın.

1. **Çözüm Gezgini'nde**proje düğümüne sağ tıklayarak yapabileceğiniz mfcmifc80.dll'ye bir başvuru ekleyin, **Ekle**, **Başvuru**ekle'yi seçin ve ardından Microsoft Visual Studio 10.0\VC\atlmfc\lib adresine göz atın.

1. UserControl1.Designer.cs açın ve aşağıdaki ifadesini ekleyin:

    ```
    using Microsoft.VisualC.MFC;
    ```

1. Ayrıca, UserControl1.Designer.cs olarak, bu satırı değiştirin:

    ```
    partial class UserControl1
    ```

   şu şekilde:

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. Bunu sınıf tanımının ilk satırı `UserControl1`olarak ekleyin:

    ```
    private ICommandSource m_CmdSrc;
    ```

1. Aşağıdaki yöntem tanımlarını `UserControl1` ekleyin (bir sonraki adımda MFC denetiminin kimliğini oluşturacağız):

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

1. Nasıl yapılacağını zımbımla oluşturduğunuz MFC uygulamasını [açın: Kullanıcı Denetimi ve Barındırıcı MDI Görünümü oluşturun.](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

1. Çağıracak `singleMenuHandler`bir menü seçeneği ekleyin.

   Kaynak **Görünümü'ne** (Ctrl+Shift+E) gidin, **Menü** klasörünü genişletin ve **ardından IDR_MFC02TYPE'yi**çift tıklatın. Bu menü düzenleyicisi görüntüler.

   **Görünüm** menüsünün alt kısmında bir menü seçeneği ekleyin. **Özellikler** penceresindeki menü seçeneğinin kimliğine dikkat edin. Dosyayı kaydedin.

   **Çözüm Gezgini'nde,** Kaynak.h dosyasını açın, az önce eklediğiniz menü seçeneğinin kimlik değerini kopyalayın ve bu değeri `Initialize` C# projesinin yöntemindeki `32771` `m_CmdSrc.AddCommandHandler` çağrıya ilk parametre olarak yapıştırın (gerekirse değiştirme).

1. Projeyi oluşturun ve çalıştırın.

   **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   Hata **Ayıklama** menüsünde hata **ayıklama olmadan Başlat'ı**tıklatın.

   Eklediğiniz menü seçeneğini seçin. .dll'deki yöntemin çağrıldığına dikkat edin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[ICommandSource Arayüzü](../mfc/reference/icommandsource-interface.md)<br/>
[ICommandTarget Arayüzü](../mfc/reference/icommandtarget-interface.md)
