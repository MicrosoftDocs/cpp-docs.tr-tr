---
title: Yardım Menüsü Birleştirme
ms.date: 11/04/2016
helpviewer_keywords:
- menus [MFC], merging
- merging Help menus [MFC]
- Help [MFC], for active document containers
ms.assetid: 9d615999-79ba-471a-9288-718f0c903d49
ms.openlocfilehash: 1bd70af6f24ee6f9873b89b2060f4b2d90149c90
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620128"
---
# <a name="help-menu-merging"></a>Yardım Menüsü Birleştirme

Bir nesne bir kapsayıcı içinde etkin olduğunda, OLE belgelerinin menü birleştirme protokolü, **Yardım** menüsünün nesnenin tüm denetimini sağlar. Sonuç olarak, Kullanıcı nesneyi devre dışı bırakmadığı sürece kapsayıcının yardım konuları kullanılamaz. Etkin belge kapsama mimarisi, hem kapsayıcının hem de etkin bir belgenin menüyü paylaşmasına izin vermek için, yerinde menü birleştirme kurallarında genişletilir. Yeni kurallar, hangi bileşenin menünün parçasını ve paylaşılan menünün nasıl oluşturulduğunu gösteren ek kurallara sahiptir.

Yeni kural basittir. Etkin belgelerde, **Yardım** menüsünde aşağıdaki gibi iki üst düzey menü öğesi düzenlenmiştir:

`Help`

`Container Help >`

`Object Help    >`

Örneğin, Office Ciltçi 'de bir Word bölümü etkin olduğunda, **Yardım** menüsü aşağıdaki gibi görünür:

`Help`

`Binder Help >`

`Word Help   >`

Her iki menü öğesi de, kapsayıcıya özgü ek menü öğelerinin ve nesnenin kullanıcıya sağlandığı basamaklı menülerdir. Burada görüntülenen öğeler kapsayıcı ve nesneler dahil değişir.

Bu birleştirilmiş **Yardım** menüsünü oluşturmak için, etkin belge kapsama mımarısı normal OLE belgeleri yordamını değiştirir. OLE belgelerine göre, birleştirilmiş menü çubuğunun altı menü grubu olabilir, bu da **Dosya**, **düzenleme**, **kapsayıcı**, **nesne**, **pencere**, **Yardım**ve bu sırada. Her grupta sıfır veya daha fazla menü olabilir. Gruplar **dosyası**, **kapsayıcı**ve **pencere** kapsayıcıya aittir ve gruplar **düzenleme**, **nesne** ve **Yardım** nesneye aittir. Nesne, bir menü birleştirme yapmak istediğinde boş bir menü çubuğu oluşturur ve kapsayıcıya geçirir. Ardından kapsayıcı, öğesini çağırarak menülerini ekler `IOleInPlaceFrame::InsertMenus` . Nesnesi Ayrıca altı uzun değerden oluşan bir dizi (**Olemenugroupgenişlikleri**) olan bir yapıyı geçirir. Menüler eklendikten sonra kapsayıcı, gruplarının her birinde kaç tane menü eklendiğini işaretler ve sonra döndürür. Ardından nesne menülerini ekler ve her kapsayıcı grubundaki menülerin sayısına dikkat edin. Son olarak, nesne birleştirilmiş menü çubuğunu ve diziyi (her bir gruptaki menülerin sayısını içeren) OLE 'ye geçirir ve bu da donuk bir "menü tanımlayıcısı" tutamacı döndürür. Daha sonra nesnesi bu tutamacı ve birleştirilmiş menü çubuğunu, ile kapsayıcısına geçirir `IOleInPlaceFrame::SetMenu` . Şu anda kapsayıcı, birleştirilmiş menü çubuğunu görüntüler ve ayrıca, OLE 'nin menü iletilerinin doğru bir şekilde dağıtımını yapabilmesi için tutamacı OLE 'e geçirir.

Değiştirilen etkin belge yordamında, nesne, kapsayıcıyı kapsayıcıya geçirmeden önce **Olemenugroupgenişlikleri** öğelerini sıfıra başlatmalıdır. Ardından kapsayıcı, tek bir özel durum ile normal bir menü eklemesi gerçekleştirir: kapsayıcı, son öğe olarak bir **Yardım** menüsü ekler ve **Olemenugroupwidth** dizisinin (yani nesnenin yardım grubuna ait olan, Width [5]) son (altıncı) girişinde 1 değerini depolar. Bu **Yardım** menüsünde yalnızca bir alt menü olan "**kapsayıcı yardım** >" basamaklı menü, daha önce açıklandığı gibi bir öğe olacak.

Nesne daha sonra normal menü ekleme kodunu yürütür, ancak **Yardım** menüsünü eklemeden önce, **Olemenugroupgenişlikleri** dizisinin altıncı girişini kontrol eder. Değer 1 ise ve son menünün adı **Yardım** (veya uygun yerelleştirilmiş dize) ise, nesne **Yardım menüsünü kapsayıcının** **Yardım** menüsünün alt menüsü olarak ekler.

Daha sonra nesnesi, **Olemenugroupgenişliklerinin** altıncı öğesini sıfır olarak ayarlar ve beşinci öğeyi bir artırır. Bu, OLE 'nin **Yardım** menüsünün kapsayıcıya ait olduğunu ve bu menüye (ve alt menülerinden) karşılık gelen menü mesajlarının kapsayıcıya yönlendirildiğini bilmesini sağlar. Daha sonra kapsayıcının, **Yardım** menüsünün nesnenin bölümüne ait olan **WM_INITMENUPOPUP**, **wm_select**, **WM_COMMAND**ve diğer menü ile ilgili iletileri iletme sorumluluğu vardır. Bu, kapsayıcının kullanıcının nesnenin **Yardım** menüsüne gezinip gezinmediğini söyleyen bir bayrak temizlemek için **WM_INITMENU** kullanılarak gerçekleştirilir. Daha sonra kapsayıcı, kapsayıcının kendisini eklememediği **Yardım** menüsündeki herhangi bir öğeden giriş veya çıkış **WM_MENUSELECT** izler. Girişte, kullanıcının bir nesne menüsüne gezindiği anlamına gelir; bu nedenle kapsayıcı "nesne yardım menüsü" bayrağını ayarlar ve en az bir **WM_MENUSELECT**, **WM_INITMENUPOPUP**ve **WM_COMMAND** iletilerini nesne penceresine iletmek için bu bayrağın durumunu kullanır. (Çıkışta kapsayıcı bayrağı temizler ve bu iletilerin kendisini işler.) Kapsayıcı, `IOleInPlaceActiveObejct::GetWindow` Bu iletilerin hedefi olarak nesnenin işlevinden döndürülen pencereyi kullanmalıdır.

Nesne, **Olemenugroupgenişliklerinin**altıncı öğesinde sıfır algılarsa, normal OLE belgeleri kurallarına göre devam eder. Bu yordam, **Yardım** menüsü birleştirme ve bu olmayanları katılan kapsayıcıları kapsamaktadır.

Nesne çağırdığında `IOleInPlaceFrame::SetMenu` , birleştirilmiş menü çubuğunu görüntülemeden önce kapsayıcı, **Yardım** menüsünün, kapsayıcının Eklenme yanına ek bir alt menüye sahip olup olmadığını denetler. Bu durumda, kapsayıcı **Yardım** menüsünü birleştirilmiş menü çubuğunda bırakır. **Yardım** menüsünde ek bir alt menü yoksa kapsayıcı, **Yardım** menüsünü birleştirilmiş menü çubuğundan kaldırır. Bu yordamda, **Yardım** menüsü birleştirme ve olmayan nesneler yer almaktadır.

Son olarak, menüyü ne zaman çözeceği, nesne eklenen **Yardım** menüsünü kaldırarak diğer eklenen menüleri kaldırmaya da kaldırılır. Kapsayıcı menülerini kaldırdığında, eklediği diğer menülere ek olarak **Yardım** menüsünü de kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[Etkin Belge Kapsayıcıları](active-document-containers.md)
