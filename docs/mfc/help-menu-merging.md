---
title: Yardım menüsü birleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menus [MFC], merging
- merging Help menus [MFC]
- Help [MFC], for active document containers
ms.assetid: 9d615999-79ba-471a-9288-718f0c903d49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 379e67d00969518400826e1f82d8801391512ef4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435629"
---
# <a name="help-menu-merging"></a>Yardım Menüsü Birleştirme

Bir nesne bir kapsayıcı içinde etkin olduğunda, menü OLE belgeleri Protokolü birleştirme nesne tam denetim verir **yardımcı** menüsü. Kullanıcı nesnesi devre dışı bırakır. sonuç olarak, kapsayıcının Yardım konuları kullanılamaz. Etkin belge kapsama mimarisi için yerinde menü kapsayıcı hem menüsünden paylaşmak için etkin olan etkin bir belge izin vermek için birleştirme kuralları genişletir. Yeni Paylaşılan menüsünün nasıl oluşturulur ve hangi bileşen menü hangi kısmının sahibi hakkında yalnızca ek kuralları kurallardır.

Yeni kural, basit bir işlemdir. Etkin belge içinde **yardımcı** menü sahip iki üst düzey menü öğeleri şu şekilde düzenlenmiştir:

`Help`

`Container Help >`

`Object Help    >`

Örneğin, bir sözcük bölümünde etkinken Office bağlayıcı sonra **yardımcı** menüsü gibi görüneceği:

`Help`

`Binder Help >`

`Word Help   >`

Her iki menü öğe altında ise kapsayıcıyı ve nesne için belirli herhangi bir ek menü öğelerini kullanıcı tarafından sağlanan basamaklı menüler şunlardır. Öğeleri burada görüntülenecek nesneleri ve kapsayıcı ile değişir dahil.

Bu birleştirilmiş oluşturulacağını **yardımcı** menüsü, etkin belge kapsama mimarisi normal OLE belgeleri yordamı değiştirir. OLE belgeleri göre birleştirilmiş menü çubuğunun altı menü, yani grubunuz olabilir **dosya**, **Düzenle**, **kapsayıcı**, **nesne**,  **Pencere**, **yardımcı**bu sırası. Her grupta sıfır veya daha fazla menüye olabilir. Grupları **dosya**, **kapsayıcı**, ve **penceresi** kapsayıcı ve gruplara ait **Düzenle**, **nesnesi,** ve **yardımcı** nesnesine ait. Nesne menü birleştirme yapmak istediği zaman, bir boş menü çubuğu oluşturur ve kapsayıcıya geçirir. Ardından kapsayıcıyı çağırarak kendi menülerini ekler `IOleInPlaceFrame::InsertMenus`. Nesne ayrıca altı uzun değerler dizisi bir yapısı geçirir (**OLEMENUGROUPWIDTHS**). Menüler ekledikten sonra kapsayıcı kaç menüler, grupları ve ardından döndürür her birinde eklenen işaretler. Ardından her bir kapsayıcı grubu dikkat menüleri sayısı için ödeme menülerini nesnesi ekler. Son olarak, nesnesi döndüren "menü tanımlayıcısı" donuk bir tanıtıcı OLE için birleştirilmiş bir menü çubuğu ve (her grubu menülerde sayısı içeren) bir dizi iletir. Daha sonra nesne, işleyici ve birleştirilmiş bir menü çubuğu kapsayıcıya üzerinden geçirir `IOleInPlaceFrame::SetMenu`. Şu anda kapsayıcı birleştirilmiş menü çubuğunu görüntüler ve böylece OLE uygun menü iletileri gönderme yapabilirsiniz tanıtıcı OLE için de geçirir.

Değiştirilen etkin belgeyi yordamda nesne ilk başlatmalıdır **OLEMENUGROUPWIDTHS** öğeleri kapsayıcıya iletmeden önce sıfır. Kapsayıcı bir özel durum ile bir normal menü ekleme gerçekleştirir, ardından: kapsayıcı ekleme bir **yardımcı** son öğe olarak menü ve 1 değeri son (altıncı) girişi depolar **OLEMENUGROUPWIDTHS** dizi (nesnenin Yardım grubuna ait olduğu diğer bir deyişle, genişlik, [5]). Bu **yardımcı** menüsünde tek bir alt öğenin sahip olur "**kapsayıcı Yardım** >" daha önce açıklandığı gibi basamaklı menüsü.

Nesne ardından eklemeden önce dışında normal menü ekleme kodu yürütür, **yardımcı** menüsünde, altıncı girişi denetler **OLEMENUGROUPWIDTHS** dizisi. Değer 1'dir ve son menünün adını ise **yardımcı** (veya uygun yerelleştirilmiş dizesi), ardından nesnesi ekler, **yardımcı** kapsayıcının alt menüsünde **yardımcı** menüsü.

Nesne altıncı öğesinin ardından ayarlar **OLEMENUGROUPWIDTHS** sıfır ve beşinci öğeye bire artırır. Bu biliyor OLE sağlar **yardımcı** menü kapsayıcıya ait ve bu menü (ve alt menülerinden) karşılık gelen menü iletiler kapsayıcıya yönlendirileceğini. Kapsayıcının sorumluluk iletmek için ise **WM_INITMENUPOPUP**, **WM_SELECT**, **WM_COMMAND**, nesnenin ait diğer menü ilgili iletiler kısmını **yardımcı** menüsü. Bu kullanılarak başarılır **WM_INITMENU** kullanıcı nesnesinin içinde olup olmadığını gezinen kapsayıcıyı belirten bir bayrak temizlemek için **yardımcı** menüsü. Kapsayıcı ardından izleyen **WM_MENUSELECT** girişine veya herhangi bir öğeyi çıkın **yardımcı** Kapsayıcının kendisi eklemediğiniz menüsü. Girişte kapsayıcı "içindeki nesnenin Yardım menüsünden" bayrağını ayarlar ve tüm iletmek için bu bayrak durumunu kullanır, kullanıcı, bir nesne menüsüne çıkıldığında olan geldiğini **WM_MENUSELECT**, **WM_INITMENUPOPUP**ve  **WM_COMMAND** iletileri, nesne penceresi için en düşük. (Çıkış, kapsayıcı bayrağını temizler ve kendi aynı bu iletileri işler.) Kapsayıcı nesnenin döndürülen penceresi kullanmalısınız `IOleInPlaceActiveObejct::GetWindow` işlevi bu iletileri görmek için hedef olarak.

Nesne altıncı öğesinin sıfır algılar, **OLEMENUGROUPWIDTHS**, normal OLE belgeleri kurallara göre geçer. Bu yordamı katılmak kapsayıcıları kapsar **yardımcı** menü desteklemeyenler yanı sıra birleştirme.

Nesne çağırdığında `IOleInPlaceFrame::SetMenu`olup birleştirilmiş menü çubuğundan kapsayıcı denetimleri görüntüleme önce **yardımcı** ne kapsayıcıya eklenen ek olarak bir ek alt menüsünde vardır. Bu nedenle, kapsayıcı ayrılırsa, **yardımcı** birleştirilmiş menü çubuğundaki menü. Varsa **yardımcı** ek bir alt menü yok, kapsayıcıyı kaldırır, **yardımcı** birleştirilmiş menü çubuğundan menüsü. Bu yordamı katılan nesneleri kapsayan **yardımcı** menü desteklemeyenler yanı sıra birleştirme.

Son olarak, bu menü ayrıştırmak için zamanı geldiğinde, nesne eklenmiş kaldırır **yardımcı** diğer kaldırma yanı sıra menü menüleri eklenmiş. Kapsayıcının menülerini kaldırdığında, Kaldır, **yardımcı** eklenmiş bir menü yanı sıra menü.

## <a name="see-also"></a>Ayrıca Bkz.

[Etkin Belge Kapsayıcıları](../mfc/active-document-containers.md)

