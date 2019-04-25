---
title: Klavye ve Fare Özelleştirmesi
ms.date: 11/19/2018
helpviewer_keywords:
- customizations [MFC], keyboard and mouse (MFC Extensions)
- keyboard and mouse customizations (MFC Extensions)
ms.assetid: 1f789f1b-5f2e-4b11-b974-e3e2a2e49d82
ms.openlocfilehash: 55eaac9d800730f3a01dcdb2eef943eb48d147b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311169"
---
# <a name="keyboard-and-mouse-customization"></a>Klavye ve Fare Özelleştirmesi

MFC, klavye ve fare girişi işleme biçimini özelleştirmek için uygulamanızın kullanıcı sağlar. Kullanıcı komutları için klavye kısayolları atayarak klavye girdisi özelleştirebilirsiniz. Kullanıcı, kullanıcı uygulamasının belirli windows içinde çift tıkladığında, yürütülmesi gereken komutu seçerek fare girişi de özelleştirebilirsiniz. Bu konuda, uygulamanız için giriş özelleştirme açıklanmaktadır.

İçinde **özelleştirme** iletişim kutusunda, kullanıcı, fare ve klavye için özel denetimler değiştirebilirsiniz. Bu iletişim kutusunu görüntülemek için kullanıcı işaret **Özelleştir** üzerinde **görünümü** menüsünü ve ardından tıklama **araç çubukları ve Docking**. İletişim kutusunda kullanıcı ya da tıklar **klavye** sekmesinde veya **fare** sekmesi.

## <a name="keyboard-customization"></a>Klavye özelleştirme

Aşağıdaki çizimde gösterildiği **klavye** sekmesinde **özelleştirme** iletişim kutusu.

![Özelleştir iletişim kutusu klavye sekmede](../mfc/media/mfcnextkeyboardtab.png "klavye sekmede Özelleştir iletişim kutusu") <br/>
Klavye özelleştirme sekmesi

Bir komuta bir veya daha fazla klavye kısayolları atama klavye sekmesi kullanıcının etkileşime. Kullanılabilir komutlar sekmenin sol tarafta listelenir. Kullanıcının herhangi bir kullanılabilir komutu menüsünden seçebilirsiniz. Menü komutları, klavye kısayolu ile ilişkilendirilebilir. Kullanıcı yeni bir kısayol girdikten sonra **atama** düğmesi hale etkin. Kullanıcı bu düğmeyi tıkladığında uygulamanın bu kısayol seçili komut ilişkilendirir.

Şu anda atanmış klavye kısayollarını liste kutusunda sağ sütunda listelenir. Ayrıca kullanıcı bireysel kısayolları seçin ve bunları kaldırmanız veya uygulama için tüm eşlemeleri sıfırlayın.

Uygulamanızda Bu özelleştirmeyi desteklemek istiyorsanız, oluşturmalısınız bir [CKeyboardManager](../mfc/reference/ckeyboardmanager-class.md) nesne. Oluşturmak için bir `CKeyboardManager` nesne, işlev çağrısı [CWinAppEx::InitKeyboardManager](../mfc/reference/cwinappex-class.md#initkeyboardmanager). Bu yöntem, oluşturur ve bir klavye Yöneticisi'ni başlatır. Klavye manager el ile oluşturursanız, yine de çağırmalısınız `CWinAppEx::InitKeyboardManager` başlatmak üzere.

Uygulamanızı oluşturmak için Sihirbazı'nı kullanırsanız, sihirbazın klavye manager başlatılır. Uygulamanızı klavye Yöneticisi'ni başlatır sonra framework ekler bir **klavye** için sekmesinde **özelleştirme** iletişim kutusu.

## <a name="mouse-customization"></a>Fare özelleştirmesi

Aşağıdaki çizimde gösterildiği **fare** sekmesinde **özelleştirme** iletişim kutusu.

![Özelleştir iletişim kutusu fare sekmede](../mfc/media/mfcnextmousetab.png "fare sekmede Özelleştir iletişim kutusu") <br/>
Fare özelleştirmesi sekmesi

Kullanıcı bir menü atamak için bu sekme ile etkileşim komutu fare eylemi çift tıklayın. Kullanıcı bir görünüm penceresinin sol taraftan seçer ve sonra bir komut çift eylemle ilişkilendirilecek işlecin sağ tarafındaki denetimlerini kullanır. Sonra kullanıcı **Kapat**, kullanıcı, görünümü'nde herhangi bir yeri çift tıklattığında her uygulama ilişkili komutu yürütür.

Sihirbazı'nı kullanarak bir uygulama oluşturduğunuzda varsayılan olarak, fare özelleştirmesi etkin değil.

#### <a name="to-enable-mouse-customization"></a>Fare özelleştirmeyi etkinleştirmek için

1. Başlatma bir [CMouseManager](../mfc/reference/cmousemanager-class.md) çağırarak [CWinAppEx::InitMouseManager](../mfc/reference/cwinappex-class.md#initmousemanager).

1. Fare Yöneticisi bir işaretçi kullanarak alma [CWinAppEx::GetMouseManager](../mfc/reference/cwinappex-class.md#getmousemanager).

1. Görünümler için fare Yöneticisi'ni kullanarak ekleme [CMouseManager::AddView](../mfc/reference/cmousemanager-class.md#addview) yöntemi. Fare Manager'a eklemek istediğiniz her bir görünüm için bunu yapın.

Uygulamanızı fare Yöneticisi'ni başlatır sonra framework ekler **fare** için sekmesinde **Özelleştir** iletişim kutusu. Sekme erişme, herhangi bir görünüm eklemezseniz, işlenmeyen bir özel durum neden olur. Görünümler, listesini oluşturduktan sonra **fare** sekmesi kullanıcı tarafından kullanılabilir.

Fare Manager'a yeni bir görünüm eklediğinizde, benzersiz bir kimliği vermiş Fare özelleştirmesi için bir pencere desteklemek istiyorsanız, arama ve WM_LBUTTONDBLCLICK ileti işlemelisiniz [CWinAppEx::OnViewDoubleClick](../mfc/reference/cwinappex-class.md#onviewdoubleclick) işlevi. Bu işlev çağırdığınızda parametrelerden biri bu pencerenin kimliğidir. Kimlik numaraları ve bunlarla ilişkili nesneleri izlemek için programcının sorumluluğundadır.

## <a name="security-concerns"></a>Güvenlik konuları

Bölümünde anlatıldığı gibi [kullanıcı tanımlı Araçlar](../mfc/user-defined-tools.md), kullanıcının bir kullanıcı tanımlı araç kimliği çift olay ile ilişkilendirebilirsiniz. Kullanıcı bir görünümü çift tıkladığında, bu uygulama, ilişkili kimlik eşleştiren bir kullanıcı aracı için arar. Uygulama bir eşleşen aracı bulursa, aracı yürütür. Eşleşen bir araç uygulaması bulunamıyor, çift görünümüne Kimliğine sahip bir WM_COMMAND ileti gönderir.

Özelleştirilmiş ayarlar kayıt defterinde depolanır. Bir saldırgan, kayıt defterini düzenleyerek, düzensiz komutu ile bir geçerli kullanıcı aracı kimliği değiştirebilirsiniz. Kullanıcı bir görünümü çift tıkladığında, işlemler görünümü saldırgan ekme komutu. Bu, beklenmeyen ve potansiyel olarak tehlikeli olabilecek davranışlara neden olabilir.

Ayrıca, bu tür bir saldırıya kullanıcı arabirimi koruma devre dışı bırakabilir. Örneğin, yazdırma devre dışı bir uygulama olduğunu varsayalım. Diğer bir deyişle, kullanıcı arabiriminde **yazdırma** menü ve düğmesi kullanılamaz. Normalde bu uygulama baskı engeller. Ancak, bir saldırganın kayıt defteri düzenlediyseniz, bir kullanıcı artık yazdırma komutu görünümü çift tıklayarak doğrudan kullanılamaz kullanıcı arabirimi öğeleri atlayarak gönderebilir.

Bu tür bir saldırıya karşı koruma sağlamak için bir komut çalıştırılmadan önce geçerli olduğunu doğrulamak için uygulama komut işleyicisi için kod ekleyin. Uygulamaya gönderilen bir komut önlemek için kullanıcı arabiriminde güvenmeyin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC için Özelleştirme](../mfc/customization-for-mfc.md)<br/>
[CKeyboardManager Sınıfı](../mfc/reference/ckeyboardmanager-class.md)<br/>
[CMouseManager Sınıfı](../mfc/reference/cmousemanager-class.md)<br/>
[Özelleştirmenin Güvenlikle İlgili Etkileri](../mfc/security-implications-of-customization.md)
