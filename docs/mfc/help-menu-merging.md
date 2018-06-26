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
ms.openlocfilehash: ecdc450bbab725c6f81cf23e16fa32a2246b2b3a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931298"
---
# <a name="help-menu-merging"></a>Yardım Menüsü Birleştirme
Bir nesne bir kapsayıcıda etkin olduğunda, OLE belgelerin Protokolü birleştirme menüsü nesne tam denetim verir **yardımcı** menüsü. Sonuç olarak, kullanıcı nesnesi devre dışı bırakır sürece kapsayıcının Yardım konuları kullanılabilir değildir. Etkin belge kapsama mimarisi kapsayıcı ve menü paylaşmak için etkin bir etkin belgeyi izin vermek için birleştirme yerinde menüsü kurallarında genişletir. Yeni kurallar, hangi bileşen menü hangi kısmının sahip olan ve paylaşılan menü nasıl oluşturulur hakkında yalnızca ek kurallardır.  
  
 Yeni kuralı basit bir işlemdir. Etkin belgeler içinde **yardımcı** menüsünde iki üst düzey menü öğelerini şu şekilde düzenlenmiştir vardır:  
  
 `Help`  
  
 `Container Help >`  
  
 `Object Help    >`  
  
 Örneğin, Word bölümü etkinken Office bağlayıcı sonra **yardımcı** menüsü gibi görüneceği:  
  
 `Help`  
  
 `Binder Help >`  
  
 `Word Help   >`  
  
 Her iki menü öğelerini altında kapsayıcı ve nesne özgü ek menü öğeleri kullanıcı tarafından sağlanan basamaklı Menüler ' dir. Burada görüntülenecek öğe kapsayıcısı ve nesneleri değişir söz konusu.  
  
 Bu birleştirilmiş oluşturmak için **yardımcı** menüsü, etkin belge kapsama mimarisi normal OLE belgeleri yordamı değiştirir. OLE belgeleri göre birleştirilmiş menü çubuğu altı menülerden, yani gruplarınız olabilir **dosya**, **Düzenle**, **kapsayıcı**, **nesne**,  **Pencere**, **yardımcı**bu sırası. Her grupta sıfır veya daha fazla menüleri olabilir. Grupları **dosya**, **kapsayıcı**, ve **penceresi** kapsayıcı ve gruplara ait **Düzenle**, **nesnesi,** ve **yardımcı** nesnesine ait. Nesne menü birleştirme yapmak istediğinde, boş menü çubuğu oluşturur ve kapsayıcıya geçirir. Ardından kapsayıcıyı çağırarak kendi menülerini ekler `IOleInPlaceFrame::InsertMenus`. Nesne aynı zamanda altı uzun değerler dizisidir bir yapı geçirir (**OLEMENUGROUPWIDTHS**). Menüleri ekledikten sonra kapsayıcı grupları ve ardından döndürür her birinde eklenen kaç menüleri işaretler. Ardından nesne dikkat menüleri sayısı için her bir kapsayıcı grubu ödeme menülerini ekler. Son olarak, nesnesi döndüren opak "menü tanımlayıcısı" bir tanıtıcı OLE için birleştirilmiş menü çubuğu ve (her grubu menülerde sayısını içerir) dizisi iletir. Daha sonra nesnenin o tanıtıcının ve birleştirilmiş menü çubuğu kapsayıcıya aracılığıyla geçirdiği `IOleInPlaceFrame::SetMenu`. Şu anda kapsayıcı birleştirilmiş menü çubuğunu görüntüler ve OLE uygun menü iletileri gönderme yapabilmesi için tanıtıcı OLE için de geçirir.  
  
 Değiştirilen etkin belgeyi yordamda nesne ilk başlatmalıdır **OLEMENUGROUPWIDTHS** öğeleri kapsayıcıya geçirmeden önce sıfır. Bir özel durum ile normal menü ekleme kapsayıcı gerçekleştirir sonra: kapsayıcı ekler bir **yardımcı** son öğe olarak menü ve değerini 1 (altıncı) son giriş depolar **OLEMENUGROUPWIDTHS** dizi (nesnenin Yardım gruba ait olan başka bir deyişle, genişlik [5]). Bu **yardımcı** menü bir alt olan yalnızca bir öğe sahip olur "**kapsayıcı Yardım** >" daha önce açıklandığı gibi cascade menüsü.  
  
 Nesne sonra eklemeden önce dışında kendi normal menü ekleme kodu yürütür kendi **yardımcı** menüsünde altıncı girişini denetler **OLEMENUGROUPWIDTHS** dizi. Değer 1'dir ve son menüsünün adı ise **yardımcı** (veya uygun yerelleştirilmiş dize) nesnesi ekler sonra kendi **yardımcı** menü kapsayıcının alt olarak **yardımcı** menüsü.  
  
 Nesne ardından altıncı öğesinin ayarlar **OLEMENUGROUPWIDTHS** sıfır ve beşinci öğe bire artırır. Bu biliyor OLE sağlar **yardımcı** menü kapsayıcıya aittir ve menüye (ve onun alt menüler) karşılık gelen menü iletiler kapsayıcıya yönlendirileceğini. Kapsayıcının sorumluluk iletmek için ise **WM_INITMENUPOPUP**, **WM_SELECT**, **WM_COMMAND**ve nesnenin ait diğer menü ilgili iletileri bölümünü **yardımcı** menüsü. Bu kullanarak gerçekleştirilir **WM_INITMENU** kullanıcı nesnesinin içinde olup olmadığını gezinen kapsayıcıyı belirten bir bayrak temizlemek için **yardımcı** menüsü. Kapsayıcı sonra izleyen **WM_MENUSELECT** giriş veya çıkış üzerinde herhangi bir öğeyi ' **yardımcı** kapsayıcı kendisini eklemediniz menüsü. Girişte kapsayıcı "içinde nesne Yardım menüsünden" bayrağını ayarlar ve bu bayrağı durumunu herhangi kullanır, kullanıcı bir nesne menüsüne, gittiğinizde gelir **WM_MENUSELECT**, **WM_INITMENUPOPUP**ve  **WM_COMMAND** nesne penceresi için en az olarak iletileri. (Çıkış, kapsayıcı bayrağını temizler ve ardından aynı bu iletiler kendisini işler.) Kapsayıcı nesnesinin döndürülen penceresi kullanmalısınız `IOleInPlaceActiveObejct::GetWindow` işlev bu iletiler için hedef olarak.  
  
 Nesne altıncı öğesinin sıfır algılar, **OLEMENUGROUPWIDTHS**, normal OLE belgeleri kurallara göre devam eder. Bu yordamı katılan kapsayıcı kapsar **yardımcı** menü değişmeyen yanı sıra birleştirme.  
  
 Nesne çağırdığında `IOleInPlaceFrame::SetMenu`birleştirilmiş menü çubuğu, kapsayıcı denetimleri olup görüntüleme önce **yardımcı** menüsünde ne kapsayıcı ekledi yanı sıra bir ek alt vardır. Bu nedenle, kapsayıcı bırakırsa kendi **yardımcı** birleştirilmiş menü çubuğunda menüsü. Varsa **yardımcı** menüsünde ek alt sahip değil ve kapsayıcı kaldıracak kendi **yardımcı** birleştirilmiş menü çubuğundan menüsü. Bu yordamı katılan nesneleri kapsayan **yardımcı** menü değişmeyen yanı sıra birleştirme.  
  
 Menü Ayır zamanı geldiğinde nesne son olarak, eklenen kaldırır **yardımcı** diğer kaldırma yanı sıra menü menüleri eklenir. Kapsayıcı menülerini kaldırdığında kaldıracak kendi **yardımcı** eklenmiş diğer menüleri yanı sıra menüsü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin Belge Kapsayıcıları](../mfc/active-document-containers.md)

