---
description: 'Daha fazla bilgi edinin: Izlenecek yol: bir uygulamaya CTaskDialog ekleme'
title: 'İzlenecek yol: Bir Uygulamaya CTaskDialog Ekleme'
ms.date: 04/25/2019
helpviewer_keywords:
- CTaskDialog, adding
- walkthroughs [MFC], dialogs
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
ms.openlocfilehash: f7462551af785b85156f3f0b0f83b2ff3ddbf4c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159901"
---
# <a name="walkthrough-adding-a-ctaskdialog-to-an-application"></a>İzlenecek yol: Bir Uygulamaya CTaskDialog Ekleme

Bu izlenecek yol [CTaskDialog sınıfını](../mfc/reference/ctaskdialog-class.md) tanıtır ve uygulamanıza nasıl ekleneceğini gösterir.

`CTaskDialog`Windows Vista veya sonraki sürümlerde Windows ileti kutusunun yerini alan bir görev iletişim kutusudur. , `CTaskDialog` Özgün ileti kutusunu geliştirir ve işlevsellik ekler. Windows ileti kutusu, Visual Studio 'da hala desteklenmektedir.

> [!NOTE]
> Windows Vista 'dan önceki Windows sürümleri, ' nı desteklemez `CTaskDialog` . Uygulamanızı Windows 'un önceki bir sürümünde çalıştıran bir kullanıcıya bir ileti göstermek istiyorsanız alternatif bir iletişim kutusu seçeneğini programmalısınız. Bir kullanıcının bilgisayarının görüntülenip görüntüleyip görüntülemeyeceği çalışma zamanında anlamak için [CTaskDialog:: IsSupported](../mfc/reference/ctaskdialog-class.md#issupported) statik yöntemini kullanabilirsiniz `CTaskDialog` . Ayrıca, `CTaskDialog` yalnızca uygulamanız Unicode kitaplığı ile oluşturulduğunda kullanılabilir.

, `CTaskDialog` Bilgi toplamak ve göstermek için birkaç isteğe bağlı öğeyi destekler. Örneğin, bir `CTaskDialog` komut bağlantıları, özelleştirilmiş düğmeler, özelleştirilmiş simgeler ve bir alt bilgi görüntüleyebilir. `CTaskDialog`Ayrıca, kullanıcının seçtiği isteğe bağlı öğeleri belirlemek için görev iletişim kutusunun durumunu sorgulamanızı sağlayan çeşitli yöntemlere sahiptir.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- Visual Studio 2010 veya sonrası

- Windows Vista veya üzeri

## <a name="replacing-a-windows-message-box-with-a-ctaskdialog"></a>Bir Windows Ileti kutusunu CTaskDialog ile değiştirme

Aşağıdaki yordam, `CTaskDialog` Windows ileti kutusunu değiştirecek olan en temel kullanımı gösterilmektedir. Bu örnek, görev iletişim kutusuyla ilişkili simgeyi de değiştirir. Simgenin değiştirilmesi, `CTaskDialog` Windows ileti kutusu ile aynı görünmesini sağlar.

### <a name="to-replace-a-windows-message-box-with-a-ctaskdialog"></a>Bir Windows Ileti kutusunu CTaskDialog ile değiştirmek için

1. Tüm varsayılan ayarlarla bir MFC uygulaması oluşturmak için **MFC Uygulama Sihirbazı** ' nı kullanın. Visual Studio sürümünüz için sihirbazın nasıl açılacağı hakkında yönergeler için bkz. [Izlenecek yol: yenı MFC kabuk denetimlerini kullanma](walkthrough-using-the-new-mfc-shell-controls.md) .

1. *MyProject*'i çağırın.

1. MyProject. cpp dosyasını açmak için **Çözüm Gezgini** kullanın.

1. Ekler `#include "afxtaskdialog.h"` listesinden sonra ekleyin.

1. Yöntemini bulun `CMyProjectApp::InitInstance` . Deyimden önce aşağıdaki kod satırlarını ekleyin `return TRUE;` . Bu kod, Windows ileti kutusu ya da içinde kullandığımız dizeleri oluşturur `CTaskDialog` .

    ```cpp
    CString message("My message to the user");
    CString dialogTitle("My Task Dialog title");
    CString emptyString;
    ```

1. 4. adımdaki koddan sonra aşağıdaki kodu ekleyin. Bu kod, kullanıcının bilgisayarının öğesini desteklemesini sağlar `CTaskDialog` . İletişim kutusu desteklenmiyorsa, uygulama bunun yerine bir Windows ileti kutusu görüntüler.

    ```cpp
    if (CTaskDialog::IsSupported())
    {

    }
    else
    {
        AfxMessageBox(message);
    }
    ```

1. 5. adımdaki deyimden sonraki köşeli ayraçlar arasına aşağıdaki kodu ekleyin **`if`** . Bu kod öğesini oluşturur `CTaskDialog` .

    ```cpp
    CTaskDialog taskDialog(message, emptyString, dialogTitle, TDCBF_OK_BUTTON);
    ```

1. Sonraki satırda aşağıdaki kodu ekleyin. Bu kod, uyarı simgesini ayarlar.

    ```cpp
    taskDialog.SetMainIcon(TD_WARNING_ICON);
    ```

1. Sonraki satırda aşağıdaki kodu ekleyin. Bu kod, görev iletişim kutusunu görüntüler.

    ```cpp
    taskDialog.DoModal();
    ```

`CTaskDialog`Windows ileti kutusuyla aynı simgenin görüntülenmesini istemiyorsanız 7. adımdan kaçının. Bu adımdan kaçındıysanız, `CTaskDialog` uygulama onu görüntülediğinde hiçbir simgesi yoktur.

Uygulamayı derleyin ve çalıştırın. Uygulama başladıktan sonra görev iletişim kutusunu görüntüler.

## <a name="adding-functionality-to-the-ctaskdialog"></a>CTaskDialog 'a Işlevsellik ekleme

Aşağıdaki yordamda, önceki yordamda oluşturduğunuz öğesine nasıl işlevsellik ekleyeceğiniz gösterilmektedir `CTaskDialog` . Örnek kod, kullanıcının seçimlerini temel alarak belirli yönergelerin nasıl yürütüleceğini gösterir.

### <a name="to-add-functionality-to-the-ctaskdialog"></a>CTaskDialog 'a Işlevsellik eklemek için

1. **Kaynak görünümü** gidin. **Kaynak görünümü** göremiyorsanız, **Görünüm** menüsünden açabilirsiniz.

1. **Dize tablosu** klasörünü seçip **kaynak görünümü** genişletin. Genişletin ve **dize tablosu** girişine çift tıklayın.

1. Dize tablosunun en altına kaydırın ve yeni bir giriş ekleyin. KIMLIĞI olarak değiştirin `TEMP_LINE1` . Başlığı **komut satırı 1** olarak ayarlayın.

1. Başka bir yeni girdi ekleyin. KIMLIĞI olarak değiştirin `TEMP_LINE2` . Yazı başlığını **komut satırı 2** olarak ayarlayın.

1. MyProject. cpp öğesine geri gidin.

1. Sonra `CString emptyString;` aşağıdaki kodu ekleyin:

    ```cpp
    CString expandedLabel("Hide extra information");
    CString collapsedLabel("Show extra information");
    CString expansionInfo("This is the additional information to the user,\nextended over two lines.");
    ```

1. İfadesini bulun `taskDialog.DoModal()` ve bu ifadeyi aşağıdaki kodla değiştirin. Bu kod, görev iletişim kutusunu güncelleştirir ve yeni denetimler ekler:

    ```cpp
    taskDialog.SetMainInstruction(L"Warning");
    taskDialog.SetCommonButtons(
        TDCBF_YES_BUTTON | TDCBF_NO_BUTTON | TDCBF_CANCEL_BUTTON);
    taskDialog.LoadCommandControls(TEMP_LINE1, TEMP_LINE2);
    taskDialog.SetExpansionArea(
        expansionInfo, collapsedLabel, expandedLabel);
    taskDialog.SetFooterText(L"This is the a small footnote to the user");
    taskDialog.SetVerificationCheckboxText(L"Remember your selection");
    ```

1. Kullanıcıya görev iletişim kutusunu görüntüleyen ve kullanıcının seçimini alan aşağıdaki kod satırını ekleyin:

    ```cpp
    INT_PTR result = taskDialog.DoModal();
    ```

1. Çağrısından sonra aşağıdaki kodu ekleyin `taskDialog.DoModal()` . Kodun bu bölümü kullanıcının girişini işler:

    ```cpp
    if (taskDialog.GetVerificationCheckboxState())
    {
        // PROCESS IF the user selects the verification checkbox
    }

    switch (result)
    {
    case TEMP_LINE1:
        // PROCESS IF the first command line
        break;
    case TEMP_LINE2:
        // PROCESS IF the second command line
        break;
    case IDYES:
        // PROCESS IF the user clicks yes
        break;
    case IDNO:
        // PROCESS IF the user clicks no
        break;
    case IDCANCEL:
        // PROCESS IF the user clicks cancel
        break;
    default:
        // This case should not be hit because closing
        // the dialog box results in IDCANCEL
        break;
    }
    ```

9. adımdaki kodda, ile başlayan açıklamaları `PROCESS IF` belirtilen koşullarda yürütmek istediğiniz kodla değiştirin.

Uygulamayı derleyin ve çalıştırın. Uygulama, yeni denetimleri ve ek bilgileri kullanan görev iletişim kutusunu görüntüler.

## <a name="displaying-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>CTaskDialog nesnesi oluşturmadan CTaskDialog görüntüleme

Aşağıdaki yordamda, önce nesne oluşturmadan nasıl görüntüleneceği gösterilmektedir `CTaskDialog` `CTaskDialog` . Bu örnek, önceki yordamları devam ettirir.

### <a name="to-display-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>CTaskDialog nesnesi oluşturmadan bir CTaskDialog görüntüleme

1. Zaten açık değilse MyProject. cpp dosyasını açın.

1. Deyimin sağ köşeli ayracına gidin `if (CTaskDialog::IsSupported())` .

1. Deyimin kapatma ayracından hemen önce aşağıdaki kodu ekleyin **`if`** ( **`else`** bloğundan önce):

    ```cpp
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message",
        L"Error",
        L"New Title",
        TEMP_LINE1,
        TEMP_LINE2);
    ```

Uygulamayı derleyin ve çalıştırın. Uygulama iki görev iletişim kutusu görüntüler. İlk iletişim kutusu, **CTaskDialog yordamına Işlevsellik eklemek için** . ikinci iletişim kutusu son yordamdan.

Bu örnekler, için tüm kullanılabilir seçenekleri `CTaskDialog` göstermemelidir, ancak başlamanıza yardımcı olur. Sınıfın tam açıklaması için bkz. [CTaskDialog sınıfı](../mfc/reference/ctaskdialog-class.md) .

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](../mfc/dialog-boxes.md)<br/>
[CTaskDialog sınıfı](../mfc/reference/ctaskdialog-class.md)<br/>
[CTaskDialog:: CTaskDialog](../mfc/reference/ctaskdialog-class.md#ctaskdialog)
