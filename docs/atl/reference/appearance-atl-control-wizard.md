---
title: ATL denetimi Sihirbazı görünümü
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: 4d3b0519951636fad4175dc35261ba35b3694ffa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248959"
---
# <a name="appearance-atl-control-wizard"></a>ATL denetimi Sihirbazı görünümü

Sihirbazın bu sayfası denetimi için ek kullanıcı öğesi seçeneklerini belirlemek için kullanın. Bu sayfa olarak tanımlanan denetimleri için kullanılabilir **standart denetimler** altında **denetim türü** üzerinde [ATL denetimi Sihirbazı, seçenekleri](../../atl/reference/options-atl-control-wizard.md) sayfası.

## <a name="uielement-list"></a>UIElement Listesi

- **Durumu görüntüle**

   Kapsayıcı içindeki denetiminin görünümünü ayarlar.

   - **Donuk**: İçindeki bit VIEWSTATUS_OPAQUE ayarlar [VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) numaralandırma ve geçirilen tüm denetim dikdörtgen çizer [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) yöntemi. Denetim tamamen opak görünür ve kapsayıcı hiçbiri denetim sınırlarını gösterir.

      Bu ayar, daha hızlı bir denetim çizmek kapsayıcı sağlar. Bu seçeneği seçili değilse, Denetim saydam bölümleri içerebilir.

      Donuk bir denetimi yalnızca düz bir arka plan olabilir.

   - **Düz bir arka plan**: VIEWSTATUS numaralandırmada bit VIEWSTATUS_SOLIDBKGND ayarlar. Denetimin arka plan, herhangi bir desen ile düz renk olarak görünür.

      Bu seçenek yalnızca **donuk** seçeneği de belirlenir.

- **Temel denetim ekleme**

   Denetim ekleyerek temel bir Windows Denetim türünde ayarlar bir [CContainedWindow](ccontainedwindowt-class.md) sınıfı denetimi uygulamak için veri üyesi. Ayrıca, ileti eşlemesi ve denetimi için Windows iletileri işlemek için ileti işleyici işlevlerini ekler. Listeden varsa oluşturmak için istediğiniz Windows Denetim türünü seçin.

   - **Düğme**

   - **ListBox**

   - **SysAnimate32**

   - **SysListView32**

   - **ComboBox**

   - **RichEdit**

   - **SysDateTimePick32**

   - **SysMonthCal32**

   - **ComboBoxEx32**

   - **ScrollBar**

   - **SysHeader32**

   - **SysTabControl32**

   - **Düzenle**

   - **Static**

   - **SysIPAddress32**

   - **SysTreeView32**

- **Çeşitli durumu**

   Görünümünü ve davranışını ek seçenekler denetimi için ayarlar.

   - **Çalışma zamanında görünmez**: Denetimin çalışma zamanında görünmez olmasını ayarlar. Görünmez denetimler, zaman aralıklarında olayları tetikleme gibi arka plan işlemleri gerçekleştirmek için kullanabilirsiniz.

   - **Düğme gibi davranan**: İçindeki bit OLEMISC_ACTSLIKEBUTTON ayarlar [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) yapacak bir denetimi etkinleştirmek için sabit bir düğme ister. Bu seçeneğin belirlenmesi, kapsayıcı denetimin istemci site varsayılan düğme olarak işaretledi, kendi kendini bir kalın kenarlığa sahip çizim varsayılan düğme olarak görüntülemek, düğme denetimi sağlar. Bkz: [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) daha fazla bilgi için.

   - **Etiket gibi davranan**: Bir denetimi kapsayıcının yerel etiket değiştirilecek etkinleştirmeyi OLEMISC numaralandırmada bit OLEMISC_ACTSLIKELABEL ayarlar. Kapsayıcı bu bayrağıyla yapmanız gerekenler herhangi bir şey olmadığını belirler.

- **Diğer**

   Denetim için ek davranışı seçeneklerini ayarlar.

   - **Normalleştirilmiş DC**: Denetim kendisini çizmek için çağrıldığında normalleştirilmiş bir cihaz bağlamı oluşturmak için ayarlar. Bu eylem denetimin görünümünü standartlaştırır ancak çizim daha az verimli kolaylaştırır.

   - **Sadece penceresini**: Denetiminiz penceresiz olamayacağını belirtir. Bu seçeneği belirlemezseniz denetiminizdir penceresiz nesneleri destekleyen kapsayıcılarında otomatik olarak penceresiz ve penceresiz nesneleri desteklemeyen kapsayıcılarında otomatik olarak pencereli. Bu seçeneğin belirlenmesi, denetiminizin bile penceresiz nesneleri destekler kapsayıcılarda pencereli olmasını zorlar.

   - **Insertable**: Denetiminiz görünür olması için bu seçeneği belirleyin **Nesne Ekle** Word ve Excel gibi uygulamaların iletişim kutusu. Denetim, ardından bu iletişim kutusu üzerinden katıştırılmış nesneleri destekleyen herhangi bir uygulama tarafından eklenebilir.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Denetimi Sihirbazı](../../atl/reference/atl-control-wizard.md)<br/>
[Örnek SUBEDIT: Aktarılabileceği standart Windows denetimi](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)
