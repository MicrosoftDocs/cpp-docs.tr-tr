---
title: Kalıcı Olmayan Özellik Sayfası Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
ms.openlocfilehash: 7a44d96adf0a25a401fbc2e561bd7d32758a37d2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617163"
---
# <a name="creating-a-modeless-property-sheet"></a>Kalıcı Olmayan Özellik Sayfası Oluşturma

Normalde, oluşturduğunuz Özellik sayfaları kalıcı olacaktır. Kalıcı bir özellik sayfası kullanırken, uygulamanın başka bir bölümünü kullanmadan önce kullanıcının özellik sayfasını kapatması gerekir. Bu makalede, uygulamanın diğer bölümlerini kullanırken Kullanıcı özellik sayfasını açık tutmaya izin veren engelleyici olmayan bir özellik sayfası oluşturmak için kullanabileceğiniz yöntemler açıklanır.

Bir özellik sayfasını kalıcı iletişim kutusu yerine kalıcı olmayan iletişim kutusu olarak göstermek için, [DoModal](reference/cpropertysheet-class.md#domodal)yerine [CPropertySheet:: Create](reference/cpropertysheet-class.md#create) öğesini çağırın. Ayrıca, engelleyici olmayan bir özellik sayfasını desteklemek için bazı ek görevler de uygulamalısınız.

Ek görevlerden biri, özellik sayfası açıkken değişiklik yaptığı dış nesne ve özellik sayfası arasında veri alışverişi yapılır. Bu genellikle standart kalıcı olmayan iletişim kutuları ile aynı görevdir. Bu görevin bir kısmı, kalıcı olmayan özellik sayfası ve özellik ayarlarının uygulandığı dış nesne arasında bir iletişim kanalı uygulamadır. Kalıcı olmayan özellik sayfası için [CPropertySheet](reference/cpropertysheet-class.md) öğesinden bir sınıf türetirsiniz bu uygulama oldukça kolaydır. Bu makalede, bu işlemi yaptığınız varsayılır.

Kalıcı olmayan özellik sayfası ve dış nesne (örneğin, görünümdeki geçerli seçim) arasında iletişim kurmak için bir yöntem, özellik sayfasından dış nesneye bir işaretçi tanımlamaktır. `SetMyExternalObject` `CPropertySheet` Odak bir dış nesneden diğerine değiştiği zaman işaretçiyi değiştirmek için-türetilmiş sınıfta bir işlev (gibi) tanımlayın. `SetMyExternalObject`İşlevin, her özellik sayfası için ayarları yeni seçilen dış nesneyi yansıtacak şekilde sıfırlaması gerekir. Bunu gerçekleştirmek için, `SetMyExternalObject` işlevin sınıfına ait olan [CPropertyPage](reference/cpropertypage-class.md) nesnelerine erişebilmesi gerekir `CPropertySheet` .

Özellik sayfası içindeki özellik sayfalarına erişim sağlamanın en kolay yolu, `CPropertyPage` nesneleri türetilmiş nesneye katıştırmanız olur `CPropertySheet` . `CPropertyPage`Türetilmiş nesnedeki nesneleri katıştırma `CPropertySheet` , kalıcı iletişim kutuları için tipik tasarımdan farklılık gösterir. Bu, özellik sayfasının sahibinin `CPropertyPage` nesneleri oluşturduğu ve bunları [CPropertySheet:: AddPage](reference/cpropertysheet-class.md#addpage)aracılığıyla Özellik sayfasına aktardığı, kalıcı iletişim kutuları için tipik tasarımdan farklıdır.

Kalıcı olmayan özellik sayfası ayarlarının bir dış nesneye ne zaman uygulanacağını belirlemek için birçok Kullanıcı Arabirimi seçeneği vardır. Her bir alternatif, Kullanıcı herhangi bir değeri değiştirdiğinde geçerli özellik sayfasının ayarlarını uygulamadır. Diğer bir seçenek de bir Uygula düğmesi sağlamaktır ve bu, kullanıcının, değişiklikleri dış nesneye kaydetmeden önce özellik sayfalarında birikmesini sağlar. Uygula düğmesini işleme yolları hakkında daha fazla bilgi için, [Uygula düğmesini işleme](handling-the-apply-button.md)başlıklı makaleye bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](property-sheets-mfc.md)<br/>
[Veri Değişimi](exchanging-data.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
