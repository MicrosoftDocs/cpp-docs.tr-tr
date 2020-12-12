---
description: 'Daha fazla bilgi edinin: Standart denetimden denetim türetme'
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
ms.openlocfilehash: 80e63464a7ad6d869582c66d5047a255e303a6a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327876"
---
# <a name="deriving-controls-from-a-standard-control"></a>Standart Bir Denetimden Denetim Türetme

Her [CWnd](reference/cwnd-class.md)ile türetilmiş sınıfta olduğu gibi, varolan bir denetim sınıfından yeni bir sınıf türeterek bir denetimin davranışını değiştirebilirsiniz.

### <a name="to-create-a-derived-control-class"></a>Türetilmiş bir denetim sınıfı oluşturmak için

1. Mevcut bir denetim sınıfından sınıfınızı türetirsiniz ve isteğe bağlı olarak `Create` üye işlevini, temel sınıf işlevine gerekli bağımsız değişkenleri sağlayacak şekilde geçersiz kılın `Create` .

1. Belirli Windows iletilerine yanıt olarak denetimin davranışını değiştirmek için ileti işleyici üye işlevleri ve ileti eşleme girişleri sağlayın. Bkz. [Iletileri IŞLEVLERE eşleme](reference/mapping-messages-to-functions.md).

1. Denetimin işlevlerini genişletmek için yeni üye işlevleri sağlayın (isteğe bağlı).

İletişim kutusunda türetilmiş bir denetimin kullanılması ek iş gerektirir. İletişim kutusundaki denetimlerin türleri ve konumları, normalde bir iletişim kutusu-şablon kaynağında belirtilir. Türetilmiş bir denetim sınıfı oluşturursanız, kaynak derleyicisi türetilmiş sınıfınız hakkında hiçbir şey bildiğinden, bunu bir iletişim kutusu şablonunda belirtemezsiniz.

#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>Türetilmiş denetiminizi bir iletişim kutusuna yerleştirmek için

1. Türetilmiş iletişim sınıfınızın bildiriminde türetilmiş denetim sınıfının bir nesnesini ekleyin.

1. `OnInitDialog`Türetilmiş denetimin üye işlevini çağırmak için iletişim sınıfınızın üye işlevini geçersiz kılın `SubclassDlgItem` .

`SubclassDlgItem` "dinamik alt sınıflar" iletişim kutusu şablonundan oluşturulan bir denetim. Bir denetim dinamik olarak alt sınıflı olduğunda, Windows 'a kanca, kendi uygulamanızdaki bazı iletileri işleyin ve ardından kalan iletileri Windows 'a geçitirsiniz. Daha fazla bilgi için [](reference/cwnd-class.md#subclassdlgitem) `CWnd` *MFC başvurusu* içindeki sınıfın SubclassDlgItem üye işlevine bakın. Aşağıdaki örnek, çağrısı yapılacak bir geçersiz kılmayı nasıl yazacağınızı gösterir `OnInitDialog` `SubclassDlgItem` :

[!code-cpp[NVC_MFCControlLadenDialog#3](codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]

Türetilmiş denetim iletişim kutusu sınıfına katıştırıldığından, iletişim kutusu oluşturulduğunda oluşturulur ve iletişim kutusu yok edildiğinde yok edilir. Bu kodu, [El Ile denetim ekleme](adding-controls-by-hand.md)içindeki örnekle karşılaştırın.

## <a name="see-also"></a>Ayrıca bkz.

[Denetimleri yapma ve kullanma](making-and-using-controls.md)<br/>
[Denetimler](controls-mfc.md)
