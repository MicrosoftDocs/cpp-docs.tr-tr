---
title: 'İzlenecek yol: Uygulamaya bir CTaskDialog ekleme'
ms.date: 04/25/2019
helpviewer_keywords:
- CTaskDialog, adding
- walkthroughs [MFC], dialogs
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
ms.openlocfilehash: 8cf2223b2859a2dfa6ecc7582ec2f171a056152c
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64558201"
---
# <a name="walkthrough-adding-a-ctaskdialog-to-an-application"></a>İzlenecek yol: Uygulamaya bir CTaskDialog ekleme

Bu izlenecek yolda tanıtır [CTaskDialog sınıfı](../mfc/reference/ctaskdialog-class.md) ve uygulamanız için bir ekleme işlemi gösterilmektedir.

`CTaskDialog` Windows ileti kutusu Windows Vista veya sonraki sürümlerde yerini alan bir görev iletişim kutusu. `CTaskDialog` Özgün ileti kutusu artırır ve işlevsellik ekler. Windows ileti kutusunda Visual Studio'da hala desteklenmektedir.

> [!NOTE]
> Windows Vista'dan önceki Windows sürümlerinde değil Destek `CTaskDialog`. Uygulamanızı önceki bir Windows sürümünü çalıştıran bir kullanıcıya bir ileti göstermek istiyorsanız bir alternatif iletişim kutusu seçeneğini program gerekir. Statik yöntemi kullanabileceğiniz [CTaskDialog::IsSupported](../mfc/reference/ctaskdialog-class.md#issupported) çalışma zamanında kullanıcının bilgisayarına görüntüleyebilirsiniz olup olmadığını belirlemek için bir `CTaskDialog`. Ayrıca, `CTaskDialog` Unicode kitaplığıyla uygulamanızı yapılandırıldığında kullanılabilir.

`CTaskDialog` Toplamak ve bilgileri görüntülemek için çeşitli isteğe bağlı öğeleri destekler. Örneğin, bir `CTaskDialog` komut bağlantıları, özelleştirilmiş bir düğme, özelleştirilmiş simgeleri ve altbilgi görüntüleyebilirsiniz. `CTaskDialog` Ayrıca hangi isteğe bağlı öğeler belirlemek için görev iletişim kutusu durumunu sorgulamak için seçtiğiniz kullanıcı olanak tanıyan çeşitli yöntemler vardır.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- Visual Studio 2010 veya sonrası

- Windows Vista veya üzeri

## <a name="replacing-a-windows-message-box-with-a-ctaskdialog"></a>Windows ileti kutusu ile bir CTaskDialog değiştirme

Aşağıdaki yordam en temel kullanımını göstermektedir `CTaskDialog`, olan Windows ileti kutusu değiştirilecek. Bu örnek ayrıca görevi iletişim kutusuyla ilişkili simgeyi değiştirir. Simgeyi değiştirme yapar `CTaskDialog` Windows ileti kutusuna aynı görünür.

### <a name="to-replace-a-windows-message-box-with-a-ctaskdialog"></a>Windows ileti kutusu ile bir CTaskDialog değiştirmek için

1. Kullanım **MFC Uygulama Sihirbazı** tüm varsayılan ayarlarla bir MFC uygulaması oluşturmak için. Bkz: [izlenecek yol: Yeni MFC Kabuk denetimlerini kullanma](walkthrough-using-the-new-mfc-shell-controls.md) Visual Studio sürümünüz için Sihirbazı'nı açmak yönergeler.

1. Bu çağrı *MyProject*. 

1. Kullanım **Çözüm Gezgini** MyProject.cpp dosyasını açın.

1. Ekleme `#include "afxtaskdialog.h"` sonra listesini içerir.

1. Find yöntemi `CMyProjectApp::InitInstance`. Önce kod aşağıdaki satırları ekleyin `return TRUE;` deyimi. Windows ileti kutusu veya kullandığımız dizeleri Bu kod oluşturur `CTaskDialog`.

    ```cpp
    CString message("My message to the user");
    CString dialogTitle("My Task Dialog title");
    CString emptyString;
    ```

1. Aşağıdaki kod, 4. adımdan koddan sonra ekleyin. Bu kod, kullanıcının bilgisayarında desteklediğini garanti eder `CTaskDialog`. İletişim desteklenmiyorsa, uygulama bunun yerine Windows ileti kutusu görüntüler.

    ```cpp
    if (CTaskDialog::IsSupported())
    {

    }
    else
    {
        AfxMessageBox(message);
    }
    ```

1. Sonra köşeli ayraçlar arasına aşağıdaki kodu `if` 5. adımdaki deyimi. Bu kod oluşturur `CTaskDialog`.

    ```cpp
    CTaskDialog taskDialog(message, emptyString, dialogTitle, TDCBF_OK_BUTTON);
    ```

1. Sonraki satırda şu kodu ekleyin. Bu kod, bir uyarı simgesi ayarlar.

    ```cpp
    taskDialog.SetMainIcon(TD_WARNING_ICON);
    ```

1. Sonraki satırda şu kodu ekleyin. Bu kod, görev iletişim kutusu görüntüler.

    ```cpp
    taskDialog.DoModal();
    ```

İstemiyorsanız, 7. adım önleyebilirsiniz `CTaskDialog` aynı simgesi Windows ileti kutusunda görüntülenecek. Bu adım, kaçının, `CTaskDialog` uygulama görüntülendiğinde yok simgesi vardır.

Derleme ve uygulamayı çalıştırın. Uygulama, başladıktan sonra görev iletişim kutusu görüntüler.

## <a name="adding-functionality-to-the-ctaskdialog"></a>İşlevselliği CTaskDialog ekleme

Aşağıdaki yordam işlevsellik ekleme işlemi açıklanır `CTaskDialog` , önceki yordamda oluşturduğunuz. Örnek kod, kullanıcı seçimlerine göre belirli yönergeleri yürütmek gösterilir.

### <a name="to-add-functionality-to-the-ctaskdialog"></a>CTaskDialog için işlevselliği eklemek için

1. Gidin **kaynak görünümü**. Göremiyorsanız **kaynak görünümü**, ondan açabileceğiniz **görünümü** menüsü.

1. Genişletin **kaynak görünümü** seçimi gösterilene kadar **dize tablosu** klasör. Genişletin ve çift **dize tablosu** girişi.

1. Dize tablosu alt kısma kaydırın ve yeni bir giriş ekleyin. Kimliği değiştirme `TEMP_LINE1`. Başlığı ayarlayın **komut satırı 1**.

1. Başka bir yeni giriş ekleyin. Kimliği değiştirme `TEMP_LINE2`. Başlığı ayarlayın **komut satırı 2**.

1. MyProject.cpp için geri gidin.

1. Sonra `CString emptyString;`, aşağıdaki kodu ekleyin:

    ```cpp
    CString expandedLabel("Hide extra information");
    CString collapsedLabel("Show extra information");
    CString expansionInfo("This is the additional information to the user,\nextended over two lines.");
    ```

1. Bulma `taskDialog.DoModal()` deyimi ve o ifadeyi aşağıdaki kodla değiştirin. Bu kod, görev iletişim kutusu güncelleştirir ve yeni denetimler ekler:

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

1. Görev iletişim kutusu kullanıcı için görüntüler ve kullanıcının seçimi alan kod aşağıdaki satırı ekleyin:

    ```cpp
    INT_PTR result = taskDialog.DoModal();
    ```

1. Çağrısından sonra aşağıdaki kodu ekleyin `taskDialog.DoModal()`. Kullanıcının girişinin kodun bu bölümünü işler:

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

9. adım kodunda ile başlayan açıklamaları değiştirin `PROCESS IF` belirtilen koşullar altında yürütmek istediğiniz kodu.

Derleme ve uygulamayı çalıştırın. Uygulama yeni denetimler ve ek bilgileri kullanan görev iletişim kutusu görüntüler.

## <a name="displaying-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>CTaskDialog nesnesi oluşturmadan bir CTaskDialog görüntüleme

Aşağıdaki yordam nasıl görüntüleneceğini gösterir bir `CTaskDialog` ilk oluşturmadan bir `CTaskDialog` nesne. Bu örnek, önceki yordamlarda devam eder.

### <a name="to-display-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>CTaskDialog nesnesi oluşturmadan bir CTaskDialog görüntülemek için

1. Zaten açık değilse MyProject.cpp dosyasını açın.

1. Sağ köşeli ayraç için gidin `if (CTaskDialog::IsSupported())` deyimi.

1. Sağ köşeli ayraç hemen önce aşağıdaki kodu ekleyin `if` deyimi (önce `else` blok):

    ```cpp
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message",
        L"Error",
        L"New Title",
        TEMP_LINE1,
        TEMP_LINE2);
    ```

Derleme ve uygulamayı çalıştırın. Uygulama, iki görev iletişim kutusu görüntüler. İlk iletişim kutusunda dandır **için CTaskDialog işlevsellik eklemek** yordamı; ikinci bir iletişim kutusudur son yordamdan.

Bu örnekler için tüm kullanılabilir seçenekleri gösteren olmayan bir `CTaskDialog`, ancak çalışmaya başlamanıza yardımcı olacaktır. Bkz: [CTaskDialog sınıfı](../mfc/reference/ctaskdialog-class.md) sınıf tam bir açıklaması.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[CTaskDialog Sınıfı](../mfc/reference/ctaskdialog-class.md)<br/>
[CTaskDialog::CTaskDialog](../mfc/reference/ctaskdialog-class.md#ctaskdialog)
