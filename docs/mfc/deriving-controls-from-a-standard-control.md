---
title: Standart Bir Denetimden Denetim Türetme
ms.date: 11/04/2016
helpviewer_keywords:
- standard controls [MFC], deriving controls from
- common controls [MFC], deriving from
- derived controls
- controls [MFC], derived
- Windows common controls [MFC], deriving from
- standard controls
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
ms.openlocfilehash: a6ce915102a8b85f135aa2c59e5e824b4fee25cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666290"
---
# <a name="deriving-controls-from-a-standard-control"></a>Standart Bir Denetimden Denetim Türetme

Herhangi bir olarak [CWnd](../mfc/reference/cwnd-class.md)-türetilmiş sınıf, var olan bir denetim sınıfından yeni bir sınıf türetilerek, denetimin davranışını değiştirebilirsiniz.

### <a name="to-create-a-derived-control-class"></a>Türetilen denetim sınıfı oluşturmak için

1. Sınıfınızı varolan bir denetimi sınıftan türetilen ve isteğe bağlı olarak geçersiz kılma `Create` üye işlevini gerekli bağımsız değişkenler için temel sınıf sağlar, böylece `Create` işlevi.

1. İleti işleyicisi üye işlevleri ve belirli Windows iletilere yanıt olarak denetimin davranışını değiştirmek için ileti eşlemesi girişleri sağlar. Bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).

1. (İsteğe bağlı) denetimi işlevlerini genişletmek için yeni üye işlevleri sağlar.

Türetilmiş bir denetim iletişim kutusunda kullanmak için ek çalışma gerekir. Normalde türlerini ve bir iletişim kutusu denetimleri konumda bir iletişim şablonunu kaynak olarak belirtilir. Türetilen denetim sınıfı oluşturursanız, kaynak derleyicisi, türetilmiş sınıf hakkında hiçbir şey bilir olduğundan bir iletişim şablonunu belirtemezsiniz.

#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>İletişim kutusunda, türetilen denetim yerleştirmek için

1. Denetim türetilmiş sınıfın bir nesnesi, türetilmiş bir iletişim kutusu sınıfı bildiriminde ekleyin.

1. Geçersiz kılma `OnInitDialog` üye işlevini çağırmak için iletişim sınıfınızı `SubclassDlgItem` türetilmiş denetimi için üye işlevi.

`SubclassDlgItem` "dinamik olarak kılabileceği" iletişim kutusu şablonundan bir denetim oluşturuldu. Bir denetimi dinamik olarak oluşturulduğunda, Windows bağlama, kendi uygulama içinde bazı iletileri işlemek ve ardından Windows açın kalan iletileri geçirmek. Daha fazla bilgi için [SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem) sınıfının üye işlevinde `CWnd` içinde *MFC başvurusu*. Aşağıdaki örnek, geçersiz kılma nasıl yazabilirsiniz gösterir `OnInitDialog` çağrılacak `SubclassDlgItem`:

[!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]

Türetilen denetim iletişim kutusu sınıfında gömülü olduğundan, iletişim kutusu oluşturulur ve iletişim kutusunu yok edildiğinde edileceği oluşturulur. Bu örnekte kodla karşılaştırın [ekleme denetimleri Yan taraftaki](../mfc/adding-controls-by-hand.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Denetimleri Yapma ve Kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

