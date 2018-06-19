---
title: Klavye ve fare özelleştirmesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- customizations [MFC], keyboard and mouse (MFC Extensions)
- keyboard and mouse customizations (MFC Extensions)
ms.assetid: 1f789f1b-5f2e-4b11-b974-e3e2a2e49d82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45b073ff2a9565c9106111299ba5b1b9d5a47351
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351669"
---
# <a name="keyboard-and-mouse-customization"></a>Klavye ve Fare Özelleştirmesi
MFC klavye ve fare girişi işleme biçimini özelleştirmek için uygulamanızın verir. Kullanıcı, komutları için klavye kısayolları atayarak klavye girişi özelleştirebilirsiniz. Kullanıcı, kullanıcı uygulamayı belirli windows içinde tıklattığında yürütülmesi gereken komutu seçerek fare girdisi de özelleştirebilirsiniz. Bu konu, uygulamanız için giriş özelleştirmeyi açıklar.  
  
 İçinde **özelleştirme** iletişim kutusu, kullanıcının fare ve klavye için özel denetimleri değiştirebilirsiniz. Bu iletişim kutusunu görüntülemek için kullanıcının işaret **Özelleştir** üzerinde **Görünüm** menüsüne ve ardından tıklama **araç çubukları ve Docking**. Kullanıcı ya da iletişim kutusunda, **klavye** sekmesini veya **fare** sekmesi.  
  
## <a name="keyboard-customization"></a>Klavye özelleştirme  
 Aşağıdaki çizimde gösterildiği **klavye** sekmesinde **özelleştirme** iletişim kutusu.  
  
 ![Özelleştir iletişim kutusu klavye sekmesinde](../mfc/media/mfcnextkeyboardtab.png "mfcnextkeyboardtab")  
Klavye özelleştirme sekmesi  
  
 Kullanıcı, bir komut için bir veya daha fazla klavye kısayolları atamak için klavye sekmesi ile etkileşim kurar. Kullanılabilir komutlar sekmesinin sol tarafta listelenir. Kullanıcının herhangi bir kullanılabilir komutunu menüsünden seçebilirsiniz. Yalnızca menü komutlarını bir klavye kısayolu ile ilişkili olabilir. Kullanıcı yeni bir kısayol girdikten sonra **atamak** düğmesi etkin hale gelir. Kullanıcı bu düğmesine tıkladığında, uygulamayı seçilen komutu bu kısayol ile ilişkilendirir.  
  
 Şu anda atanmış klavye kısayollarını sağ sütundaki liste kutusunda listelenir. Ayrıca kullanıcı tek tek kısayolları seçin ve bunları kaldırmak veya uygulama için tüm eşlemelerini Sıfırla.  
  
 Bu özelleştirme uygulamanızda desteklemek istiyorsanız, oluşturmalısınız bir [CKeyboardManager](../mfc/reference/ckeyboardmanager-class.md) nesnesi. Oluşturmak için bir `CKeyboardManager` nesne, bir işlevi çağırmak [CWinAppEx::InitKeyboardManager](../mfc/reference/cwinappex-class.md#initkeyboardmanager). Bu yöntem oluşturur ve bir klavye Yöneticisi'ni başlatır. Klavye Yöneticisi elle oluşturursanız, hala çağırmalısınız `CWinAppEx::InitKeyboardManager` başlatmak üzere.  
  
 Uygulamanızı oluşturmak için Sihirbazı'nı kullanırsanız, sihirbazın klavye Yöneticisi'ni başlatın. Uygulamanızı klavye Yöneticisi'ni başlatır sonra framework ekler bir **klavye** için sekme **özelleştirme** iletişim kutusu.  
  
## <a name="mouse-customization"></a>Fare özelleştirmesi  
 Aşağıdaki çizimde gösterildiği **fare** sekmesinde **özelleştirme** iletişim kutusu.  
  
 ![Özelleştir iletişim kutusu fare sekmesinde](../mfc/media/mfcnextmousetab.png "mfcnextmousetab")  
Fare özelleştirme sekmesi  
  
 Bir menüyü atamak için bu sekmeyi kullanıcı etkileşim fare komutuna eylem çift tıklayın. Kullanıcı bir görünüm penceresinin sol tarafındaki seçer ve sonra komut çift tıklatma eylemi ile ilişkilendirmek için sağ taraftaki denetimlerini kullanır. Sonra kullanıcı **Kapat**, kullanıcının herhangi bir yere görünümünde çift tıklamalar her uygulama ilişkili komutu çalıştırır.  
  
 Sihirbazı'nı kullanarak bir uygulama oluşturduğunuzda varsayılan olarak, fare özelleştirmesi etkin değil.  
  
#### <a name="to-enable-mouse-customization"></a>Fare özelleştirmesi etkinleştirmek için  
  
1.  Başlatma bir [CMouseManager](../mfc/reference/cmousemanager-class.md) çağırarak nesne [CWinAppEx::InitMouseManager](../mfc/reference/cwinappex-class.md#initmousemanager).  
  
2.  Bir işaretçi fare Yöneticisi'ni kullanarak elde [CWinAppEx::GetMouseManager](../mfc/reference/cwinappex-class.md#getmousemanager).  
  
3.  Görünümler için fare Yöneticisi'ni kullanarak eklemek [CMouseManager::AddView](../mfc/reference/cmousemanager-class.md#addview) yöntemi. Fare Yöneticisi eklemek istediğiniz her görünüm için bunu yapabilirsiniz.  
  
 Uygulamanızı fare Yöneticisi'ni başlatır sonra framework ekler **fare** için sekme **Özelleştir** iletişim kutusu. Herhangi bir görünüm eklemezseniz sekmesini erişme işlenmeyen bir özel durum neden olur. Görünümler, listesini oluşturduktan sonra **fare** sekmesinde kullanıcı için kullanılabilir.  
  
 Yeni bir görünüm için fare Yöneticisi eklediğinizde, benzersiz bir kimliği vermiş Fare özelleştirmesi için bir pencere desteklemek istiyorsanız, işlemelidir `WM_LBUTTONDBLCLICK` ileti ve çağrı [CWinAppEx::OnViewDoubleClick](../mfc/reference/cwinappex-class.md#onviewdoubleclick) işlevi. Bu işlev çağırdığınızda, parametrelerden biri o penceresi kimliğidir. Kimlik numaraları ve bunlarla ilişkili nesneleri izlemek için programcı sorumluluğundadır.  
  
## <a name="security-concerns"></a>Güvenlik sorunları  
 Bölümünde açıklandığı gibi [kullanıcı tanımlı Araçlar](../mfc/user-defined-tools.md), kullanıcının bir kullanıcı tarafından tanımlanan aracı kimliği çift olay ile ilişkilendirebilirsiniz. Kullanıcı bir görünüm tıklattığında uygulama ilişkili kimliği eşleşen bir kullanıcı için aracı arar. Uygulama bir eşleşen aracı bulursa, aracı yürütür. Uygulama bir eşleşen aracı bulamazsanız, tıklatıldığında görünümüne Kimliğine sahip bir WM_COMMAND ileti gönderir.  
  
 Özelleştirilmiş ayarları kayıt defterine depolanır. Kayıt defterini düzenleyerek, bir saldırganın geçerli bir kullanıcı aracı kimliği düzensiz komutu ile değiştirebilirsiniz. Kullanıcı bir görünüm tıklattığında görünümü saldırgan ekme komutu işler. Bu, beklenmeyen ve potansiyel olarak tehlikeli olabilecek davranışlara neden olabilir.  
  
 Ayrıca, bu tür bir saldırı kullanıcı arabirimi korumaları devre dışı bırakabilir. Örneğin, bir uygulama yazdırma devre dışı olduğunu varsayalım. Diğer bir deyişle, kendi kullanıcı arabiriminde **yazdırma** menü ve düğmesi kullanılamaz. Normalde bu yazdırma uygulamadan önler. Ancak bir saldırgan kayıt düzenlediyseniz, bir kullanıcı şimdi yazdırma komutu doğrudan Görüntüle'yi tıklatarak kullanılabilir kullanıcı arabirimi öğeleri atlayarak gönderebilir.  
  
 Bu tür bir saldırıya karşı koruma sağlamak için bir komut çalıştırılmadan önce geçerli olduğunu doğrulamak için uygulama komutu işleyicisine kodu ekleyin. Uygulamaya gönderilen bir komut önlemek için kullanıcı arabirimi bağlı değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC için özelleştirme](../mfc/customization-for-mfc.md)   
 [CKeyboardManager sınıfı](../mfc/reference/ckeyboardmanager-class.md)   
 [CMouseManager sınıfı](../mfc/reference/cmousemanager-class.md)   
 [Özelleştirmenin Güvenlikle İlgili Etkileri](../mfc/security-implications-of-customization.md)

