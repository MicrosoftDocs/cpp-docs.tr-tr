---
title: Klavye ve Fare Özelleştirmesi
ms.date: 11/19/2018
helpviewer_keywords:
- customizations [MFC], keyboard and mouse (MFC Extensions)
- keyboard and mouse customizations (MFC Extensions)
ms.assetid: 1f789f1b-5f2e-4b11-b974-e3e2a2e49d82
ms.openlocfilehash: 262555b060f226a86438a2189eda44d83c55d5a2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621497"
---
# <a name="keyboard-and-mouse-customization"></a>Klavye ve Fare Özelleştirmesi

MFC, uygulamanızın kullanıcısına klavye ve fare girişini nasıl işlediğini özelleştirme olanağı tanır. Kullanıcı komutlara klavye kısayolları atayarak klavye girişini özelleştirebilir. Kullanıcı, kullanıcının uygulamanın belirli bir pencerelerinin içini çift tıkladığı zaman yürütülmesi gereken komutu seçerek de fare girişini özelleştirebilir. Bu konuda, uygulamanızın girişinin nasıl özelleştirileceği açıklanmaktadır.

**Özelleştirme** iletişim kutusunda, Kullanıcı fare ve klavye için özel denetimleri değiştirebilir. Bu iletişim kutusunu görüntülemek için Kullanıcı **Görünüm** menüsünde **özelleştirmeyi** Işaret eder ve ardından **araç çubukları ve yerleştirme**' i tıklatır. İletişim kutusunda Kullanıcı **klavye** sekmesine veya **fare** sekmesine tıklar.

## <a name="keyboard-customization"></a>Klavye özelleştirmesi

Aşağıdaki çizimde **Özelleştirme** Iletişim kutusunun **klavye** sekmesi gösterilmektedir.

![Özelleştir iletişim kutusundaki klavye sekmesi](../mfc/media/mfcnextkeyboardtab.png "Özelleştir iletişim kutusundaki klavye sekmesi") <br/>
Klavye özelleştirme sekmesi

Kullanıcı, bir komuta bir veya daha fazla klavye kısayolu atamak için klavye sekmesiyle etkileşime girer. Kullanılabilir komutlar sekmenin sol tarafında listelenir. Kullanıcı menüden kullanılabilir herhangi bir komutu seçebilir. Yalnızca menü komutları bir klavye kısayoluyla ilişkilendirilebilir. Kullanıcı yeni bir kısayol girdikten sonra, **ata** düğmesi etkin hale gelir. Kullanıcı bu düğmeye tıkladığında, uygulama seçili komutu bu kısayol ile ilişkilendirir.

Şu anda atanmış olan klavye kısayollarının hepsi, sağ sütundaki liste kutusunda listelenir. Kullanıcı aynı zamanda ayrı Kısayollar seçebilir ve bunları kaldırabilir ya da uygulama için tüm eşlemeleri sıfırlayabilir.

Uygulamanızda bu özelleştirmeyi desteklemek istiyorsanız, bir [CKeyboardManager](reference/ckeyboardmanager-class.md) nesnesi oluşturmanız gerekir. Bir nesne oluşturmak için `CKeyboardManager` [CWinAppEx:: InitKeyboardManager](reference/cwinappex-class.md#initkeyboardmanager)işlevini çağırın. Bu yöntem bir klavye Yöneticisi oluşturur ve başlatır. Bir klavye yöneticisini el ile oluşturursanız, yine de `CWinAppEx::InitKeyboardManager` başlatmak için çağırmanız gerekir.

Uygulamanızı oluşturmak için Sihirbazı kullanırsanız, sihirbaz klavye yöneticisini başlatır. Uygulamanız klavye yöneticisini başlattıktan sonra, çerçeve **Özelleştirme** iletişim kutusuna bir **klavye** sekmesi ekler.

## <a name="mouse-customization"></a>Fare özelleştirmesi

Aşağıdaki çizimde **Özelleştirme** Iletişim kutusunun **fare** sekmesi gösterilmektedir.

![Özelleştir iletişim kutusunda fare sekmesi](../mfc/media/mfcnextmousetab.png "Özelleştir iletişim kutusunda fare sekmesi") <br/>
Fare özelleştirme sekmesi

Kullanıcı, fare çift tıklama eylemine bir menü komutu atamak için bu sekmeyle etkileşime girer. Kullanıcı pencerenin sol tarafındaki bir görünümü seçer ve ardından çift tıklama eylemiyle bir komutu ilişkilendirmek için sağ taraftaki denetimleri kullanır. Kullanıcı **Kapat**' ı tıkladıktan sonra, Kullanıcı görünümün herhangi bir yerini çift tıkladığı zaman uygulama ilişkili komutu yürütür.

Varsayılan olarak, Sihirbazı kullanarak bir uygulama oluşturduğunuzda fare özelleştirmesi etkin değildir.

#### <a name="to-enable-mouse-customization"></a>Fare özelleştirmeyi etkinleştirmek için

1. [CWinAppEx:: InitMouseManager](reference/cwinappex-class.md#initmousemanager)çağırarak bir [CMouseManager](reference/cmousemanager-class.md) nesnesi başlatın.

1. [CWinAppEx:: GetMouseManager](reference/cwinappex-class.md#getmousemanager)kullanarak fare yöneticisine bir işaretçi alın.

1. [CMouseManager:: AddView](reference/cmousemanager-class.md#addview) metodunu kullanarak, fare yöneticisine görünümler ekleyin. Bunu, fare yöneticisine eklemek istediğiniz her görünüm için yapın.

Uygulamanız fare yöneticisini başlattıktan sonra, çerçeve, **Özelleştirme** Iletişim kutusuna **fare** sekmesini ekler. Herhangi bir görünüm eklememiyorsanız, sekmeye erişmek işlenmemiş bir özel duruma neden olur. Görünümler listesini oluşturduktan sonra, **fare** sekmesi Kullanıcı tarafından kullanılabilir.

Fare yöneticisine yeni bir görünüm eklediğinizde, buna benzersiz bir KIMLIK verirsiniz. Bir pencere için fare özelleştirmeyi desteklemek istiyorsanız, WM_LBUTTONDBLCLICK iletisini işleyin ve [CWinAppEx:: OnViewDoubleClick](reference/cwinappex-class.md#onviewdoubleclick) işlevini çağırmanız gerekir. Bu işlevi çağırdığınızda parametrelerden biri söz konusu pencerenin KIMLIĞIDIR. Programcı, KIMLIK numaralarının ve bunlarla ilişkili nesnelerin izlenmesi için sorumluluğudur.

## <a name="security-concerns"></a>Güvenlik sorunları

Kullanıcı [tanımlı araçlar](user-defined-tools.md)bölümünde açıklandığı gibi, Kullanıcı Kullanıcı tanımlı BIR araç kimliğini çift tıklama olayı ile ilişkilendirebilirler. Kullanıcı bir görünümü çift tıkladığında, uygulama ilişkili KIMLIKLE eşleşen bir Kullanıcı aracı arar. Uygulama eşleşen bir araç bulursa, aracı yürütür. Uygulama eşleşen bir araç bulamazsa, KIMLIĞI çift tıklanmış görünüme sahip WM_COMMAND bir ileti gönderir.

Özelleştirilmiş ayarlar kayıt defterinde saklanır. Bir saldırgan, kayıt defterini düzenleyerek geçerli bir Kullanıcı aracı KIMLIĞINI rastgele bir komutla değiştirebilir. Kullanıcı bir görünümü çift tıkladığında, görünüm, saldırganın planlanan komutu işler. Bu, beklenmeyen ve potansiyel olarak tehlikeli davranışa neden olabilir.

Ayrıca, bu tür bir saldırı Kullanıcı arabirimi korumalarını atlayabilir. Örneğin, bir uygulamanın yazdırma devre dışı olduğunu varsayalım. Diğer bir deyişle, Kullanıcı arabiriminde, **Yazdır** menüsü ve düğmesi kullanılamaz. Normalde bu, uygulamanın yazdırılmasını önler. Ancak, bir saldırgan kayıt defterini düzenlediyse, bir Kullanıcı artık Görünüm ' e çift tıklayarak, kullanılamayan Kullanıcı arabirimi öğelerini atlayarak Print komutunu doğrudan gönderebilir.

Bu tür saldırılara karşı koruma sağlamak için uygulama komut işleyicinizde kod ekleyerek bir komutun yürütülmeden önce geçerli olduğunu doğrulayın. Bir komutun uygulamaya gönderilmesini engellemek için Kullanıcı arabirimine bağlı değildir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC için Özelleştirme](customization-for-mfc.md)<br/>
[CKeyboardManager sınıfı](reference/ckeyboardmanager-class.md)<br/>
[CMouseManager Sınıfı](reference/cmousemanager-class.md)<br/>
[Özelleştirmenin güvenlik etkileri](security-implications-of-customization.md)
