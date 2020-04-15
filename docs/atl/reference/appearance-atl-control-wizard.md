---
title: Görünüm, ATL Kontrol Sihirbazı
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: 3484fb5d0f919af0dfd18b584e96d4675e2baea8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319406"
---
# <a name="appearance-atl-control-wizard"></a>Görünüm, ATL Kontrol Sihirbazı

Denetim için ek kullanıcı öğesi seçeneklerini tanımlamak için sihirbazın bu sayfasını kullanın. Bu [sayfa, Seçenekler, ATL Denetim Sihirbazı](../../atl/reference/options-atl-control-wizard.md) sayfasında **Denetim türü** altında **Standart denetimler** olarak tanımlanan denetimler için kullanılabilir.

## <a name="uielement-list"></a>UIElement Listesi

- **Durumu görüntüleme**

   Denetimin kapsayıcı içindeki görünümünü ayarlar.

  - **Opak**: [VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus) numaralandırmasında VIEWSTATUS_OPAQUE bitini ayarlar ve [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) yöntemine geçen tüm kontrol dikdörtgenini çizer. Denetim tamamen opak görünür ve kapsayıcıların hiçbiri denetim sınırlarının arkasında görünmez.

      Bu ayar, kapsayıcının denetimi daha hızlı çekmesine yardımcı olur. Bu seçenek seçili değilse, denetim saydam parçalar içerebilir.

      Sadece opak bir denetim sağlam bir arka plana sahip olabilir.

  - **Düz Arka Plan**: VIEWSTATUS numaralandırmasında VIEWSTATUS_SOLIDBKGND bitini ayarlar. Denetimin arka planı desensiz düz bir renk olarak görünür.

      Bu seçenek yalnızca **Opak** seçenek de seçilirse kullanılabilir.

- **Buna göre denetim ekleme**

   Denetimi uygulayan sınıfa bir [CContainedWindow](ccontainedwindowt-class.md) veri üyesi ekleyerek denetimi windows denetim türüne göre ayarlar. Ayrıca, denetim için Windows iletilerini işlemek için bir ileti eşlemi ve ileti işleyicisi işlevleri ekler. Varsa oluşturmak istediğiniz Windows denetimi türünü listeden seçin.

  - **Düğme**

  - **ListBox**

  - **SysAnimate32**

  - **SysListView32**

  - **ComboBox**

  - **Richedit**

  - **SysDateTimePick32**

  - **SysMonthCal32**

  - **ComboBoxEx32**

  - **ScrollBar**

  - **SysHeader32**

  - **SysTabControl32**

  - **Düzenle**

  - **Statik**

  - **SysIPAddress32**

  - **SysTreeView32**

- **Misc durumu**

   Denetim için ek görünüm ve davranış seçenekleri ayarlar.

  - **Çalışma zamanında görünmez**: Denetimi çalışma zamanında görünmez olacak şekilde ayarlar. Zaman aralıklarında olayları ateşlemek gibi arka planda işlemleri gerçekleştirmek için görünmez denetimleri kullanabilirsiniz.

  - **Düğme gibi davranır**: [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) numaralandırmasında OLEMISC_ACTSLIKEBUTTON bitini bir düğme gibi bir denetime göre ayarlar. Kapsayıcı denetimin istemci sitesini varsayılan düğme olarak işaretlediyse, bu seçeneği seçmek düğme denetiminizin kendisini daha kalın bir çerçeveyle çizerek varsayılan düğme olarak kendisini görüntülemesini sağlar. Bkz. [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) daha fazla bilgi için.

  - **Etiket gibi davranır**: OLEMISC numaralandırmasında OLEMISC_ACTSLIKELABEL bitini, kapsayıcının yerel etiketini değiştirmek için bir denetim sağlamak için ayarlar. Konteyner bu bayrakla ne yapacağını belirler.

- **Diğer**

   Denetim için ek davranış seçenekleri ayarlar.

  - **Normalleştirilmiş DC**: Kendini çizmek için çağrıldığında normalleştirilmiş bir aygıt bağlamı oluşturmak için denetimi ayarlar. Bu eylem denetimin görünümünü standartlaştırır, ancak çizimi daha az verimli hale getirir.

  - **Yalnızca Pencere**: Denetiminizin penceresiz olamayacağını belirtir. Bu seçeneği seçmezseniz, denetiminiz penceresiz nesneleri destekleyen kapsayıcılarda otomatik olarak penceresiz olur ve penceresiz nesneleri desteklemeyen kapsayıcılara otomatik olarak pencerelenir. Bu seçeneğin seçilmesi, penceresiz nesneleri destekleyen kapsayıcılarda bile denetiminizi pencereli olmaya zorlar.

  - **Ekleye :** Word ve Excel gibi uygulamaların **Nesne Ekle** iletişim kutusunda denetiminizin görünmesini sağlamak için bu seçeneği belirleyin. Denetiminiz daha sonra bu iletişim kutusu aracılığıyla katıştılı nesneleri destekleyen herhangi bir uygulama tarafından eklenebilir.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Denetimi Sihirbazı](../../atl/reference/atl-control-wizard.md)<br/>
[SUBEDIT Örnek: Bir Standart Windows Denetimi üst sınıflar](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)
