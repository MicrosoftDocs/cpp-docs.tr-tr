---
description: 'Ayrıntılar hakkında daha fazla bilgi edinin: görünüm, ATL Denetim Sihirbazı'
title: Görünüm, ATL Denetim Sihirbazı
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: f8ae2951249d7093eef7a32a7cde167aa359aa02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165569"
---
# <a name="appearance-atl-control-wizard"></a>Görünüm, ATL Denetim Sihirbazı

Denetimin ek kullanıcı öğesi seçeneklerini belirlemek için sihirbazın bu sayfasını kullanın. Bu sayfa, [Seçenekler, atl Denetim Sihirbazı](../../atl/reference/options-atl-control-wizard.md) sayfasında **Denetim türü** altında **standart denetimler** olarak tanımlanan denetimler için kullanılabilir.

## <a name="uielement-list"></a>UIElement Listesi

- **Durumu görüntüle**

   Kapsayıcının içindeki denetimin görünümünü ayarlar.

  - **Donuk**: [viewstatus](/windows/win32/api/ocidl/ne-ocidl-viewstatus) numaralandırmasındaki VIEWSTATUS_OPAQUE bitini ayarlar ve [CComControlBase:: OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) yöntemine geçirilen tüm denetim dikdörtgenini çizer. Denetim tamamen donuk görünür ve kapsayıcının hiçbiri denetim sınırlarının arkasında gösterilir.

      Bu ayar kapsayıcının denetimi daha hızlı çizmesini sağlar. Bu seçenek seçilmezse, Denetim saydam parçalar içerebilir.

      Yalnızca donuk bir denetim düz bir arka plana sahip olabilir.

  - **Düz arka plan**: viewstatus numaralandırmasında VIEWSTATUS_SOLIDBKGND bitini ayarlar. Denetimin arka planı, bir kalıbı olmayan bir düz renk olarak görünür.

      Bu seçenek yalnızca **donuk** seçeneği de işaretliyse kullanılabilir.

- **Temelinde Denetim Ekle**

   Denetimi uygulayan sınıfa bir [CContainedWindow](ccontainedwindowt-class.md) veri üyesi ekleyerek, denetimi bir Windows denetim türüne göre ayarlar. Ayrıca, denetim için Windows iletilerini işlemek üzere bir ileti Haritası ve ileti işleyici işlevleri de ekler. Varsa, oluşturmak istediğiniz Windows denetiminin türünü listeden seçin.

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

- **Çeşitli durum**

   Denetim için ek görünüm ve davranış seçeneklerini ayarlar.

  - **Çalışma zamanında görünmez**: çalışma zamanında denetimi görünmez olacak şekilde ayarlar. Arka planda işlemleri gerçekleştirmek için, zaman aralıklı aralıklarla olayları başlatma gibi görünmez denetimleri kullanabilirsiniz.

  - **Düğme gibi davranır**: bir denetimin bir düğme gibi davranmasını sağlamak Için, [olemisc](/windows/win32/api/oleidl/ne-oleidl-olemisc) numaralandırmasındaki OLEMISC_ACTSLIKEBUTTON bitini ayarlar. Kapsayıcı denetimin istemci sitesini varsayılan düğme olarak işaretlediyse, bu seçeneğin belirlenmesi düğme denetiminizin kendisini, bir kalın kareyle birlikte çizerek varsayılan bir düğme olarak görüntülemesini sağlar. Daha fazla bilgi için bkz. [CComControlBase:: Getambentdisplayasdefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) .

  - **Etiket gibi davranır**: bir denetimin yerel etiketini değiştirmesini sağlamak IÇIN, olemisc numaralandırmasındaki OLEMISC_ACTSLIKELABEL bitini ayarlar. Kapsayıcı, varsa, bu bayrağa ne yapılacağını belirler.

- **Diğer**

   Denetim için ek davranış seçeneklerini ayarlar.

  - **NORMALLEŞTIRILMIŞ DC**: denetimi, kendisini çizmek için çağrıldığında Normalleştirilmemiş bir cihaz bağlamı oluşturmak için ayarlar. Bu eylem, denetimin görünümünü standartlaştırır, ancak çizimi daha az verimli hale getirir.

  - **Yalnızca pencere**: denetiminizin penceresiz olduğunu belirtir. Bu seçeneği seçmezseniz, denetiminiz penceresiz nesneleri destekleyen kapsayıcılarda otomatik olarak penceresiz ve penceresiz nesneleri desteklemeyen kapsayıcılarda otomatik olarak pencereli hale gelir. Bu seçeneğin belirlenmesi, penceresiz nesneleri destekleyen kapsayıcılarda bile denetiminizi pencereli olmaya zorlar.

  - **Eklenebilir**: denetim, Word ve Excel gibi uygulamaların **nesne Ekle** iletişim kutusunda görünmesini sağlamak için bu seçeneği belirleyin. Daha sonra denetiminiz, bu iletişim kutusu aracılığıyla katıştırılmış nesneleri destekleyen herhangi bir uygulama tarafından eklenebilir.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Denetim Sihirbazı](../../atl/reference/atl-control-wizard.md)<br/>
[Alt öğeleri DıT örneği: üst sınıflar standart bir Windows denetimi](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)
