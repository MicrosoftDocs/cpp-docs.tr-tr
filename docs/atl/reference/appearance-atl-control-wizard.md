---
title: Görünüm, ATL Denetim Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1d27b46f529d8423bdaf733928a9f3e46b3f185
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="appearance-atl-control-wizard"></a>Görünüm, ATL Denetim Sihirbazı
"Arama sonuçları" Özet buraya ekleyin.  
  
 Sihirbazın bu sayfası denetimi için ek kullanıcı öğesi seçeneklerini belirlemek için kullanın. Bu sayfa olarak tanımlanan denetimleri için kullanılabilir **standart denetimler** altında **denetim türü** üzerinde [seçenekleri, ATL Denetim Sihirbazı](../../atl/reference/options-atl-control-wizard.md) sayfası.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Durumu görüntüle**  
 Kapsayıcı içinde denetiminin görünümünü ayarlar.  
  
-   **Donuk**: kümeleri `VIEWSTATUS_OPAQUE` içinde bit [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) numaralandırma ve tüm denetim dikdörtgen geçirilen çizer [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) yöntemi. Denetim tamamen opak görünür ve kapsayıcı hiçbiri denetim sınırlarını gösterir.  
  
     Bu ayar denetimi daha hızlı bir şekilde çizmek kapsayıcı yardımcı olur. Bu seçenek seçilmezse, Denetim saydam bölümleri içerebilir.  
  
     Donuk bir denetim düz bir arka plan olabilir.  
  
-   Ayarlar `VIEWSTATUS_SOLIDBKGND` içinde bit `VIEWSTATUS` numaralandırması. Denetimin arka planının hiçbir düzendeki düz renk olarak görünür.  
  
     Bu seçenek yalnızca **donuk** seçeneği de belirlenmediğinde.  
  
 **Temel denetim ekleme**  
 Bir Windows denetim türüne ekleyerek bağlı için denetimi ayarlar bir [CContainedWindow](ccontainedwindowt-class.md) denetimi uygulama sınıfı veri üyesi. Ayrıca, ileti eşlemesi ve denetimi için Windows iletilerini işlemek için ileti işleyici işlevleri ekler. Listeden varsa oluşturmak için istediğiniz Windows denetimi türünü seçin.  

  
-   `Button`  
  
-   `ListBox`  
  
-   `SysAnimate32`  
  
-   `SysListView32`  
  
-   `ComboBox`  
  
-   `RichEdit`  
  
-   `SysDateTimePick32`  
  
-   `SysMonthCal32`  
  
-   `ComboBoxEx32`  
  
-   `ScrollBar`  
  
-   `SysHeader32`  
  
-   `SysTabControl32`  
  
-   `Edit`  
  
-   `Static`  
  
-   `SysIPAddress32`  
  
-   `SysTreeView32`  
  
 **Çeşitli durumu**  
 Ek Görünüm ve davranış seçenekleri denetimi için ayarlar.  
  
-   **Çalışma zamanında görünmez**: çalışma zamanında görünmez olmasını denetimi ayarlar. Görünmez denetimler aralıklarla olaylarını tetikleme gibi arka planda işlemlerini gerçekleştirmek için kullanabilirsiniz.  
  
-   **Düğme gibi davranır**: kümeleri `OLEMISC_ACTSLIKEBUTTON` içinde bit [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) görev yapması denetimi etkinleştirmek için numaralandırma ister bir düğme. Kapsayıcı denetimin istemci sitesi varsayılan düğme olarak işaretledi, bu seçeneğin belirlenmesi kendisini kendisini kalın çerçeve çizerek bir varsayılan düğme olarak görüntülemek, düğme denetimi sağlar. Bkz: [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) daha fazla bilgi için.  
  
-   **Etiket gibi davranan**: kümeleri `OLEMISC_ACTSLIKELABEL` içinde bit `OLEMISC` kapsayıcının yerel etiketi değiştirmek denetimi etkinleştirmek için numaralandırması. Kapsayıcı bu bayrağı ile Yapılacaklar herhangi bir şey belirler.  
  
 **Diğer**  
 Denetim için ek davranışı seçeneklerini ayarlar.  
  
-   **DC normalleştirilmiş**: denetim kendisini çizmek için çağrıldığında normalleştirilmiş cihaz bağlamı oluşturmak için ayarlar. Bu eylem denetimin görünümünü standartlaştıran ancak çizim daha az verimli kolaylaştırır.  
  
-   **Yalnızca penceresinin**: denetiminizi penceresiz olamaz belirtir. Bu seçeneği seçmezseniz, Denetim penceresiz nesneleri destekler kapsayıcılarında otomatik olarak penceresiz ve penceresiz nesneleri desteklemezler kapsayıcılarında otomatik olarak pencereli olur. Bu seçeneğin belirlenmesi denetiminizi bile penceresiz nesneleri destekler kapsayıcılarında pencereli olmasını zorlar.  
  
-   **Belirten gösterge**: denetiminizi görünmesini sağlamak için bu seçeneği seçin **Nesne Ekle** Word ve Excel gibi uygulamalarının iletişim kutusu. Denetim, ardından bu iletişim kutusu üzerinden katıştırılmış nesneler destekleyen herhangi bir uygulama tarafından eklenebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Denetim Sihirbazı](../../atl/reference/atl-control-wizard.md)   
 [Örnek SUBEDIT: Aktarılabileceği standart Windows denetimi](http://msdn.microsoft.com/en-us/30e46bdc-ed92-417c-b6b8-359017265a7b)

