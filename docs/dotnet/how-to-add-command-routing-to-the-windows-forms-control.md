---
title: "Nasıl yapılır: komut ekleme Forms Denetimi'ne yönlendiren Windows | Microsoft Docs"
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4c13b0bedf7c81431449aaed8d4fa8f067cdf3d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133655"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme
[CWinFormsView](../mfc/reference/cwinformsview-class.md) MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemeye izin vermek için kullanıcı denetimi komutlar ve güncelleştirme komut UI iletilerini yönlendirir.  
  
 Kullanıcı denetimini kullanan [ICommandTarget::Initialize'ı](../mfc/reference/icommandtarget-interface.md#initialize) komut kaynak nesnesi başvuru depolamak için `m_CmdSrc`, aşağıdaki örnekte gösterildiği gibi. Kullanılacak `ICommandTarget` mfcmifc80.dll'ye bir başvuru eklemeniz gerekir.  
  
 `CWinFormsView` genel MFC görünüm bildirimlerini çeşitli yönetilen kullanıcı denetimine ileterek işler. Bu bildirimler dahil [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate), [in](../mfc/reference/iview-interface.md#onupdate) ve [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) yöntemleri.  
  
 Bu konuda daha önce tamamlandı varsayılır [nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) ve [nasıl yapılır: kullanıcı denetimi ve konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için  
  
1.  Windows Forms denetimi oluşturduğunuz kitaplığı açmak [nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
2.  ' Nde proje düğümüne sağ tıklayarak yapabilirsiniz mfcmifc80.dll'ye bir başvuru ekleyin **Çözüm Gezgini**, seçme **Ekle**, **başvuru**ve için gözatma Microsoft Visual Studio 10.0\VC\atlmfc\lib.  
  
3.  UserControl1.Designer.cs açın ve aşağıdaki ekleme deyimini kullanarak:  
  
    ```  
    using Microsoft.VisualC.MFC;  
    ```  
  
4.  Ayrıca, UserControl1.Designer.cs içinde bu satırı değiştirin:  
  
    ```  
    partial class UserControl1  
    ```  
  
     Bunun için:  
  
    ```  
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget  
    ```  
  
5.  Bu sınıf tanımı ilk satır olarak ekleyin `UserControl1`:  
  
    ```  
    private ICommandSource m_CmdSrc;  
    ```  
  
6.  Aşağıdaki yöntem tanımları ekleme `UserControl1` (MFC denetiminin Kimliğini sonraki adımda oluşturacağız):  
  
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
  
7.  Oluşturduğunuz MFC uygulamasında açmak [nasıl yapılır: kullanıcı denetimi ve konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
8.  Çağıracağı menü seçeneği ekleyin `singleMenuHandler`.  
  
     Git **kaynak görünümü** (Ctrl + Shift + E) genişletin **menü** klasörü ve çift tıklatarak **IDR_MFC02TYPE**. Menü düzenleyicisi görüntüler.  
  
     Menü seçeneği sonuna ekleyin **Görünüm** menüsü. Menü seçeneğinin Kimliğini fark **özellikleri** penceresi. Dosyayı kaydedin.  
  
     İçinde **Çözüm Gezgini**Resource.h dosyasını açın, eklediğiniz menü seçeneğinin kimlik değerini kopyalayın ve bu değer ilk parametre olarak Yapıştır `m_CmdSrc.AddCommandHandler` C# projesinde 's çağırmak `Initialize` ( değiştirmeyöntemi`32771` gerekirse).  
  
9. Oluşturun ve projeyi çalıştırın.  
  
     Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat hata ayıklama olmadan**.  
  
     Eklediğiniz menü seçeneğini belirleyin. .Dll yöntemi çağrılır dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC görünümü olarak Windows Forms kullanıcı denetimi barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [ICommandSource arabirimi](../mfc/reference/icommandsource-interface.md)   
 [ICommandTarget arabirimi](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](http://msdn.microsoft.com/Library/22096734-e074-4aca-8523-4b15590109f9)