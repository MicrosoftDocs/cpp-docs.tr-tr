---
title: Kalıcı Olmayan Özellik Sayfası Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
ms.openlocfilehash: 9012700ef145079cf01ee1eac1cee58449ab5b79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524906"
---
# <a name="creating-a-modeless-property-sheet"></a>Kalıcı Olmayan Özellik Sayfası Oluşturma

Normalde, oluşturduğunuz özellik sayfalarını kalıcı olur. Bir kalıcı özellik sayfası kullanılırken, kullanıcının herhangi bir uygulamanın parçası kullanmadan önce özellik sayfasını kapatmalısınız. Bu makalede, özellik sayfası kullanılırken uygulamanın diğer kısımlarını açık tutmak kullanıcıya izin veren bir kalıcı olmayan özellik sayfası oluşturmak için kullanabileceğiniz yöntemleri açıklar.

Bir özellik sayfası yerine modsuz iletişim kutusu olarak kalıcı bir iletişim kutusu görüntülemek için çağrı [CPropertySheet::Create](../mfc/reference/cpropertysheet-class.md#create) yerine [DoModal](../mfc/reference/cpropertysheet-class.md#domodal). Kalıcı olmayan özellik sayfası desteklemek için bazı ek görevleri de uygulamanız gerekir.

Ek görevlerinden birini ve özellik sayfası ve özellik sayfası açıldığında değiştirme dış nesne arasında veri değiştiriyor. Standart kalıcı olmayan iletişim kutuları için aynı görev genellikle budur. Bu görev bir parçası bir kalıcı olmayan özellik sayfası ve özellik ayarlarının uygulandığı dış nesne arasındaki iletişim kanalını uygular. Bu uygulama öğesinden bir sınıf türetirseniz çok daha kolay [CPropertySheet](../mfc/reference/cpropertysheet-class.md) , kalıcı olmayan özellik sayfası için. Bu makalede, yaptıktan varsayılır.

Kalıcı olmayan özellik sayfası ve dış arasında iletişim kurmak için bir yöntemi olan nesne (örneğin, bir görünüm geçerli seçimde) işaretçisinden bir özellik sayfası için dış nesne tanımlamak için. Bir fonksiyon tanımlayın (gibi adlı `SetMyExternalObject`) içinde `CPropertySheet`-türetilmiş sınıf işaretçisi odağı bir dış nesneden değiştiğinde değiştirmek için. `SetMyExternalObject` İşlevi yeni seçilen dış nesne yansıtacak şekilde her bir özellik sayfası için ayarlara gerekiyor. Bunu gerçekleştirmek için `SetMyExternalObject` işlevi erişebilir olmalıdır [CPropertyPage](../mfc/reference/cpropertypage-class.md) ait nesneleri `CPropertySheet` sınıfı.

Özellik sayfaları içinde bir özellik sayfası erişim sağlamak için en uygun yolu eklemek için olan `CPropertyPage` nesneler `CPropertySheet`-türetilmiş bir nesneye. Gömme `CPropertyPage` nesneler `CPropertySheet`-özellik sayfası sahibi olduğu oluşturur, kalıcı iletişim kutuları için tipik tasarım türetilmiş nesneden farklıdır `CPropertyPage` nesneleri ve özellik sayfası geçirir [ CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage).

Kalıcı olmayan özellik sayfası ayarları için bir dış nesne ne zaman uygulanması gereken belirlemek için çok sayıda kullanıcı arabirimi seçenekleri vardır. Bir kullanıcının herhangi bir değer değiştiğinde geçerli özellik sayfası ayarları uygulamak için alternatiftir. Başka bir alternatif için dış nesne yapmadan önce değişiklikleri özellik sayfalarındaki accumulate izin verir ve Uygula düğmesini, sağlamaktır. Uygula düğmesini işleme için yollar hakkında daha fazla bilgi için bkz [Uygula düğmesini işleme](../mfc/handling-the-apply-button.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)<br/>
[Veri Değişimi](../mfc/exchanging-data.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

