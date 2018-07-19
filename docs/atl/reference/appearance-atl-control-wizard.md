---
title: Görünüm, ATL denetimi Sihirbazı | Microsoft Docs
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
ms.openlocfilehash: 3dd95e3e25cd015fd326c236f15a965e3fb9e801
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025886"
---
# <a name="appearance-atl-control-wizard"></a>ATL denetimi Sihirbazı görünümü
"Arama sonuçları" Özet buraya ekleyin.  
  
 Sihirbazın bu sayfası denetimi için ek kullanıcı öğesi seçeneklerini belirlemek için kullanın. Bu sayfa olarak tanımlanan denetimleri için kullanılabilir **standart denetimler** altında **denetim türü** üzerinde [ATL denetimi Sihirbazı, seçenekleri](../../atl/reference/options-atl-control-wizard.md) sayfası.  
  
## <a name="uielement-list"></a>UIElement Listesi  
**Durumu görüntüle**  
Kapsayıcı içindeki denetiminin görünümünü ayarlar.  
  
 -   **Donuk**: içindeki bit VIEWSTATUS_OPAQUE ayarlar [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) numaralandırma ve geçirilen tüm denetim dikdörtgen çizer [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) yöntemi. Denetim tamamen opak görünür ve kapsayıcı hiçbiri denetim sınırlarını gösterir.      
      
        Bu ayar, daha hızlı bir denetim çizmek kapsayıcı sağlar. Bu seçeneği seçili değilse, Denetim saydam bölümleri içerebilir.  
      
        Donuk bir denetimi yalnızca düz bir arka plan olabilir.  
      
 -   VIEWSTATUS numaralandırmada bit VIEWSTATUS_SOLIDBKGND ayarlar. Denetimin arka plan, herhangi bir desen ile düz renk olarak görünür.  
      
  Bu seçenek yalnızca **donuk** seçeneği de belirlenir.  
  
**Temel denetim ekleme**  
Denetim ekleyerek temel bir Windows Denetim türünde ayarlar bir [CContainedWindow](ccontainedwindowt-class.md) sınıfı denetimi uygulamak için veri üyesi. Ayrıca, ileti eşlemesi ve denetimi için Windows iletileri işlemek için ileti işleyici işlevlerini ekler. Listeden varsa oluşturmak için istediğiniz Windows Denetim türünü seçin.  

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
Görünümünü ve davranışını ek seçenekler denetimi için ayarlar.  
  
 -   **Çalışma zamanında görünmez**: denetimin çalışma zamanında görünmez olmasını ayarlar. Görünmez denetimler, zaman aralıklarında olayları tetikleme gibi arka plan işlemleri gerçekleştirmek için kullanabilirsiniz.  
      
 -   **Düğme gibi davranan**: içindeki bit OLEMISC_ACTSLIKEBUTTON ayarlar [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) yapacak bir denetimi etkinleştirmek için sabit bir düğme ister. Bu seçeneğin belirlenmesi, kapsayıcı denetimin istemci site varsayılan düğme olarak işaretledi, kendi kendini bir kalın kenarlığa sahip çizim varsayılan düğme olarak görüntülemek, düğme denetimi sağlar. Bkz: [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) daha fazla bilgi için.  
      
  -   **Etiket gibi davranan**: OLEMISC numaralandırmada bit OLEMISC_ACTSLIKELABEL kapsayıcının yerel etiketi değiştirmek bir denetimi etkinleştirmek için ayarlar. Kapsayıcı bu bayrağıyla yapmanız gerekenler herhangi bir şey olmadığını belirler.  
  
**Diğer**  
Denetim için ek davranışı seçeneklerini ayarlar.  
  
 -   **DC normalleştirilmiş**: denetimin kendisini çizmek için çağrıldığında normalleştirilmiş bir cihaz bağlamı oluşturmak için ayarlar. Bu eylem denetimin görünümünü standartlaştırır ancak çizim daha az verimli kolaylaştırır.  
      
 -   **Sadece penceresini**: denetiminizin penceresiz olamayacağını belirtir. Bu seçeneği belirlemezseniz denetiminizdir penceresiz nesneleri destekleyen kapsayıcılarında otomatik olarak penceresiz ve penceresiz nesneleri desteklemeyen kapsayıcılarında otomatik olarak pencereli. Bu seçeneğin belirlenmesi, denetiminizin bile penceresiz nesneleri destekler kapsayıcılarda pencereli olmasını zorlar.  
      
 -   **Insertable**: denetiminizin görünür olması için bu seçeneği belirleyin **Nesne Ekle** Word ve Excel gibi uygulamaların iletişim kutusu. Denetim, ardından bu iletişim kutusu üzerinden katıştırılmış nesneleri destekleyen herhangi bir uygulama tarafından eklenebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Denetim Sihirbazı](../../atl/reference/atl-control-wizard.md)   
 [Örnek SUBEDIT: Aktarılabileceği standart Windows denetimi](http://msdn.microsoft.com/30e46bdc-ed92-417c-b6b8-359017265a7b)

