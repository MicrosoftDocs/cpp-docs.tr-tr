---
title: "İzlenecek yol: bir uygulamaya bir CTaskDialog ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CTaskDialog, adding
- walkthroughs [MFC], dialogs
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9072769dcacc837804e7ceacaa81beecb209fc2a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-adding-a-ctaskdialog-to-an-application"></a>İzlenecek yol: Bir Uygulamaya CTaskDialog Ekleme
Bu kılavuzda tanıtır [CTaskDialog sınıfı](../mfc/reference/ctaskdialog-class.md) ve uygulamanız için bir tane ekleyin gösterilmektedir.  
  
 `CTaskDialog` Windows ileti kutusunda değiştiren bir görev iletişim kutusu [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]. `CTaskDialog` Özgün ileti kutusu artırır ve işlevsellik ekler. Windows ileti kutusu yine de desteklenen [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
> [!NOTE]
>  Windows'un öncesi [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)] desteklemeyen `CTaskDialog`. Uygulamanızı Windows'un önceki bir sürümünü çalıştıran bir kullanıcıyla bir ileti göstermek istiyorsanız bir alternatif iletişim kutusu seçeneğini program gerekir. Statik yöntemini kullanabilirsiniz [CTaskDialog::IsSupported](../mfc/reference/ctaskdialog-class.md#issupported) çalışma zamanında bir kullanıcının bilgisayarına görüntüleyebilirsiniz olup olmadığını belirlemek için bir `CTaskDialog`. Ayrıca, `CTaskDialog` uygulamanızı Unicode kitaplıkla yapılandırıldığında kullanılabilir.  
  
 `CTaskDialog` Toplamak ve bilgilerini görüntülemek için çeşitli isteğe bağlı öğeleri destekler. Örneğin, bir `CTaskDialog` komut bağlantıları, özelleştirilmiş düğmeleri, özelleştirilmiş simgeleri ve altbilgi görüntüleyebilirsiniz. `CTaskDialog` Ayrıca hangi isteğe bağlı öğeleri belirlemek için görev iletişim kutusu durumunu sorgulamak için seçilen kullanıcıya sağlayan çeşitli yöntemler vardır.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
- [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)]  
  
- [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
## <a name="replacing-a-windows-message-box-with-a-ctaskdialog"></a>Windows ileti kutusu CTaskDialog ile değiştirme  
 Aşağıdaki yordam en temel kullanımını gösteren `CTaskDialog`, olduğu Windows ileti kutusu değiştirmek için. Bu örnek ayrıca görev iletişim kutusuyla ilişkili simgeyi değiştirir. Simgeyi değiştirme yapar `CTaskDialog` Windows ileti kutusu için aynı görünür.  
  
#### <a name="to-replace-a-windows-message-box-with-a-ctaskdialog"></a>Windows ileti kutusu CTaskDialog ile değiştirmek için  
  
1.  Varsayılan ayarlarla yeni bir MFC Uygulama projesi oluşturun. Bu çağrı `MyProject`.  
  
2.  Kullanım **Çözüm Gezgini** MyProject.cpp dosyası açılamıyor.  
  
3.  Ekleme `#include "afxtaskdialog.h"` sonra listesini içerir.  
  
4.  Find yöntemi `CMyProjectApp::InitInstance`. Önce kod aşağıdaki satırları ekleyin `return TRUE;` deyimi. Bu kod Windows ileti kutusu veya kullanırız dizeleri oluşturur `CTaskDialog`.  
  
 ```  
    CString message("My message to the user");

    CString dialogTitle("My Task Dialog title");

    CString emptyString;  
 ```  
  
5.  Aşağıdaki kod 4. adımdan sonra kodu ekleyin. Bu kodu kullanıcının bilgisayarı desteklediğini garanti `CTaskDialog`. İletişim kutusu desteklenmiyorsa uygulama bunun yerine bir Windows ileti kutusu görüntüler.  
  
 ```  
    if (CTaskDialog::IsSupported())  
 {  
 
 }  
    else 
 {  
    AfxMessageBox(message);

 }  
 ```  
  
6.  Aşağıdaki kod sonra köşeli ayraçlar arasında Ekle `if` 5. adım from deyimi. Bu kod oluşturur `CTaskDialog`.  
  
 ```  
    CTaskDialog taskDialog(message,
    emptyString,
    dialogTitle,
    TDCBF_OK_BUTTON);

 ```  
  
7.  Sonraki satırında, aşağıdaki kodu ekleyin. Bu kod uyarı simgesi ayarlar.  
  
 ```  
    taskDialog.SetMainIcon(TD_WARNING_ICON);

 ```  
  
8.  Sonraki satırında, aşağıdaki kodu ekleyin. Bu kod görev iletişim kutusu görüntüler.  
  
 ```  
    taskDialog.DoModal();

 ```  
  
 İstemiyorsanız, adım 7 atlayabilirsiniz `CTaskDialog` aynı simgesini Windows ileti kutusu görüntüleme. Bu adımı atlarsanız `CTaskDialog` uygulama görüntülediğinde yok simgesi vardır.  
  
 Derleme ve uygulamayı çalıştırın. Uygulama başladıktan sonra görev iletişim kutusu görüntüler.  
  
## <a name="adding-functionality-to-the-ctaskdialog"></a>İşlevsellik CTaskDialog ekleme  
 Aşağıdaki yordamda işlevini eklemek gösterilmiştir `CTaskDialog` önceki yordamda oluşturduğunuz. Kod örneği, kullanıcının seçimleri temel alarak belirli yönergeleri yürütmek nasıl gösterilir.  
  
#### <a name="to-add-functionality-to-the-ctaskdialog"></a>CTaskDialog işlevselliği eklemek için  
  
1.  Gidin **kaynak görünümü**. Göremiyorsanız **kaynak görünümü**, ondan açabilirsiniz **Görünüm** menüsü.  
  
2.  Genişletme **kaynak görünümü** seçebileceğiniz kadar **dize tablosu** klasör. Çift tıklayın ve genişletin **dize tablosu** girişi.  
  
3.  Dize tablosu altına gidin ve yeni bir giriş ekleyin. Değişiklik kimliği `TEMP_LINE1`. Resim yazısını kümesine **komut satırı 1**.  
  
4.  Başka bir yeni giriş Ekle. Değişiklik kimliği `TEMP_LINE2`. Resim yazısını kümesine **komut satırı 2**.  
  
5.  Geri MyProject.cpp gidin.  
  
6.  Sonra `CString emptyString;`, aşağıdaki kodu ekleyin:  
  
 ```  
    CString expandedLabel("Hide extra information");

    CString collapsedLabel("Show extra information");

    CString expansionInfo("This is the additional information to the user,\nextended over two lines.");

 ```  
  
7.  Bul `taskDialog.DoModal()` deyimi ve bu deyimi aşağıdaki kodla değiştirin. Bu kod görev iletişim kutusu güncelleştirir ve yeni denetimler ekler:  
  
 ```  
    taskDialog.SetMainInstruction(L"Warning");

 taskDialog.SetCommonButtons(TDCBF_YES_BUTTON | TDCBF_NO_BUTTON | TDCBF_CANCEL_BUTTON);

    taskDialog.LoadCommandControls(TEMP_LINE1,
    TEMP_LINE2);

    taskDialog.SetExpansionArea(expansionInfo,
    collapsedLabel,
    expandedLabel);

    taskDialog.SetFooterText(L"This is the a small footnote to the user");

    taskDialog.SetVerificationCheckboxText(L"Remember your selection");

 ```  
  
8.  Görev iletişim kutusu kullanıcı için görüntüler ve kullanıcının seçimi alır kodu aşağıdaki satırı ekleyin:  
  
 ```  
    INT_PTR result = taskDialog.DoModal();

 ```  
  
9. Çağrısından sonra aşağıdaki kodu ekleyin `taskDialog.DoModal()`. Bu bölüm kodunun kullanıcının giriş işler:  
  
 ```  
    if (taskDialog.GetVerificationCheckboxState())  
 { *// PROCESS IF the user selects the verification checkbox   
 }  
 
    switch (result)  
 {  
    case TEMP_LINE1: *// PROCESS IF the first command line  
    break; 
    case TEMP_LINE2: *// PROCESS IF the second command line  
    break; 
    case IDYES: *// PROCESS IF the user clicks yes  
    break; 
    case IDNO: *// PROCESS IF the user clicks no  
    break; 
    case IDCANCEL: *// PROCESS IF the user clicks cancel  
    break; 
    default: *// This case should not be hit because closing the dialog box results in IDCANCEL  
    break; 
 }  
 ```  
  
 Kodda 9. adım, belirtilen koşullar altında yürütmek istediğiniz kod ile işlem IF ile başlayan yorumları değiştirin.  
  
 Derleme ve uygulamayı çalıştırın. Uygulama yeni denetimler ve ek bilgiler kullanan görev iletişim kutusu görüntüler.  
  
## <a name="displaying-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>Bir CTaskDialog CTaskDialog nesne oluşturmadan görüntüleme  
 Aşağıdaki yordam nasıl görüntüleneceğini gösterir bir `CTaskDialog` ilk oluşturmadan bir `CTaskDialog` nesnesi. Bu örnek, önceki yordamlarda devam eder.  
  
#### <a name="to-display-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>Bir CTaskDialog nesnesi oluşturmadan bir CTaskDialog görüntülemek için  
  
1.  Henüz açık değilse MyProject.cpp dosyasını açın.  
  
2.  İçin kapanış ayracı gidin `if (CTaskDialog::IsSupported())` deyimi.  
  
3.  Ayraç hemen öncesine aşağıdaki kodu ekleyin `if` deyimi (önce `else` bloğu):  
  
 ```  
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message",
    L"Error",
    L"New Title",
    TEMP_LINE1,
    TEMP_LINE2);

 ```  
  
 Derleme ve uygulamayı çalıştırın. Uygulama iki görev iletişim kutusu görüntüler. İlk iletişim kutusunda eklemek işlevinden, için CTaskDialog yordamdır; İkinci bir iletişim kutusu son yordamdan ' dir.  
  
 Bu örnekler için tüm kullanılabilir seçenekleri gösterir olmayan bir `CTaskDialog`, ancak başlamanıza yardımcı olması. Bkz: [CTaskDialog sınıfı](../mfc/reference/ctaskdialog-class.md) sınıfı tam bir açıklaması.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [CTaskDialog sınıfı](../mfc/reference/ctaskdialog-class.md)   
 [CTaskDialog::CTaskDialog](../mfc/reference/ctaskdialog-class.md#ctaskdialog)

