---
title: Kalıcı olmayan özellik sayfası oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
ms.openlocfilehash: 90f6dcd5659d308a4b39d6a7d5a42003fc1f2111
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685694"
---
# <a name="creating-a-modeless-property-sheet"></a>Kalıcı olmayan özellik sayfası oluşturma

Normalde, oluşturduğunuz Özellik sayfaları kalıcı olacaktır. Kalıcı bir özellik sayfası kullanırken, uygulamanın başka bir bölümünü kullanmadan önce kullanıcının özellik sayfasını kapatması gerekir. Bu makalede, uygulamanın diğer bölümlerini kullanırken Kullanıcı özellik sayfasını açık tutmaya izin veren engelleyici olmayan bir özellik sayfası oluşturmak için kullanabileceğiniz yöntemler açıklanır.

Bir özellik sayfasını kalıcı iletişim kutusu yerine kalıcı olmayan iletişim kutusu olarak göstermek için, [DoModal](../mfc/reference/cpropertysheet-class.md#domodal)yerine [CPropertySheet:: Create](../mfc/reference/cpropertysheet-class.md#create) öğesini çağırın. Ayrıca, engelleyici olmayan bir özellik sayfasını desteklemek için bazı ek görevler de uygulamalısınız.

Ek görevlerden biri, özellik sayfası açıkken değişiklik yaptığı dış nesne ve özellik sayfası arasında veri alışverişi yapılır. Bu genellikle standart kalıcı olmayan iletişim kutuları ile aynı görevdir. Bu görevin bir kısmı, kalıcı olmayan özellik sayfası ve özellik ayarlarının uygulandığı dış nesne arasında bir iletişim kanalı uygulamadır. Kalıcı olmayan özellik sayfası için [CPropertySheet](../mfc/reference/cpropertysheet-class.md) öğesinden bir sınıf türetirsiniz bu uygulama oldukça kolaydır. Bu makalede, bu işlemi yaptığınız varsayılır.

Kalıcı olmayan özellik sayfası ve dış nesne (örneğin, görünümdeki geçerli seçim) arasında iletişim kurmak için bir yöntem, özellik sayfasından dış nesneye bir işaretçi tanımlamaktır. Odak bir dış nesneden diğerine değiştiği zaman işaretçiyi değiştirmek için @no__t -1-Derived sınıfında `SetMyExternalObject` gibi bir işlev tanımlayın. @No__t-0 işlevinin, yeni seçilen dış nesneyi yansıtacak şekilde her bir özellik sayfası için ayarları sıfırlaması gerekir. Bunu gerçekleştirmek için `SetMyExternalObject` işlevi, `CPropertySheet` sınıfına ait [CPropertyPage](../mfc/reference/cpropertypage-class.md) nesnelerine erişebilmelidir.

Özellik sayfası içindeki özellik sayfalarına erişim sağlamanın en kolay yolu, `CPropertyPage` nesnelerini @no__t -1-Derived nesnesine katıştırmanız sağlamaktır. @No__t -1-türetilmiş nesnesindeki `CPropertyPage` nesne ekleme, kalıcı iletişim kutuları için tipik tasarımdan farklıdır, burada Özellik sayfası sahibinin `CPropertyPage` nesnelerini oluşturduğu ve bunları [CPropertySheet:: AddPage](../mfc/reference/cpropertysheet-class.md#addpage)aracılığıyla Özellik sayfasına geçirir.

Kalıcı olmayan özellik sayfası ayarlarının bir dış nesneye ne zaman uygulanacağını belirlemek için birçok Kullanıcı Arabirimi seçeneği vardır. Her bir alternatif, Kullanıcı herhangi bir değeri değiştirdiğinde geçerli özellik sayfasının ayarlarını uygulamadır. Diğer bir seçenek de bir Uygula düğmesi sağlamaktır ve bu, kullanıcının, değişiklikleri dış nesneye kaydetmeden önce özellik sayfalarında birikmesini sağlar. Uygula düğmesini işleme yolları hakkında daha fazla bilgi için, [Uygula düğmesini işleme](../mfc/handling-the-apply-button.md)başlıklı makaleye bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)<br/>
[Veri değişimi](../mfc/exchanging-data.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
