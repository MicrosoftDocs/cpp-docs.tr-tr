---
title: Denetim Ayarları, MFC ActiveX Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.settings
helpviewer_keywords:
- MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
ms.openlocfilehash: 3eedf24fa4b0bb527b374dbc9f538408f20de953
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548245"
---
# <a name="control-settings-mfc-activex-control-wizard"></a>Denetim Ayarları, MFC ActiveX Denetim Sihirbazı

Sihirbazın bu sayfasındaki davranmaya denetimin nasıl istediğinizi belirtmek için kullanın. Örneğin, temel standart Windows Denetim türleri denetiminde kendi davranış ve görünümünü en iyi duruma veya denetim, diğer denetimler için kapsayıcı olarak görev yapabilir gösterir.

Denetim verimliliğini en üst düzeye çıkarmak için bu sayfadaki seçenekler seçme hakkında daha fazla bilgi için bkz. [MFC ActiveX denetimleri: iyileştirme](../../mfc/mfc-activex-controls-optimization.md).

## <a name="uielement-list"></a>UIElement Listesi

- **Temel denetim oluşturma**

   Bu listede, Denetim devraldığı denetim türünü seçebilirsiniz. Bir alt kümesi için kullanılabilir olan denetim sınıfları listedir `CreateWindowEx` ve commctrl.h içinde belirtilen ek ortak denetimleri. Seçiminiz denetiminde stilini belirler `PreCreateWindow` işlevi *ProjName*Ctrl.cpp dosya. Daha fazla bilgi için [MFC ActiveX denetimleri: bir Windows denetimini alt sınıf yapma](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).

   |Denetim|Açıklama|
   |-------------|-----------------|
   |**DÜĞME**|Bir Windows düğme denetimi|
   |**COMBOBOX**|Windows birleşik giriş kutusu denetimi|
   |**DÜZENLE**|Windows düzenleme kutusu denetimi|
   |**LİSTE KUTUSU**|Windows liste kutusu denetimi|
   |**KAYDIRMA ÇUBUĞU**|Windows kaydırma çubuğu denetimi|
   |**STATİK**|Windows statik denetimi|
   |**msctls_hotkey32**|Sık kullanılan tuş ortak denetimi|
   |**msctls_progress32**|Bir ilerleme çubuğu ortak denetim|
   |**msctls_statusbar32**|Bir durum çubuğu ortak denetim|
   |**msctls_trackbar32**|Ortak denetim çubuğu bir izleme|
   |**msctls_updown32**|Bir değer değiştirme düğmesi (veya yukarı-aşağı) ortak denetimi|
   |**SysAnimate32**|Ortak animasyon denetimi|
   |**SysHeader32**|Ortak bir üstbilgi denetim|
   |**SysListView32**|Bir liste görünümü ortak denetimi|
   |**SysTabControl32**|Ortak sekme denetimi|
   |**SysTreeView32**|Ağaç görünümü ortak denetimi|

- **Görünür olduğunda etkinleştirilir**

   Denetim için bir pencere oluşturulur, erişildiğinde belirtir. Varsayılan olarak, **etkinleştirir görünür olduğunda** seçeneği belirlenir. Kapsayıcı (örneğin, bir kullanıcı fareye tıklayana) gerektirdiği kadar denetim etkinleştirme erteleneceği istiyorsanız bu seçeneği temizleyin. Bu özelliği devre dışıyken denetim gerekli olana kadar pencere oluşturma gider tabi değildir. Daha fazla bilgi için [görünürken etkinleştir seçeneğini kapatma](../../mfc/turning-off-the-activate-when-visible-option.md).

- **Çalışma zamanında görünmez**

   Denetimin çalışma zamanında kullanıcı arabirimi olmadan sahip olduğunu belirtir. Bir zamanlayıcı görünmez olmasını isteyebileceğiniz denetimi türüdür.

- **Bir hakkında iletişim kutusu var**

   Denetimin standart Windows sahip olduğunu belirtir **hakkında** iletişim kutusunda, sürüm numarasını ve telif hakkı bilgilerini görüntüler.

   > [!NOTE]
   > Kullanıcı denetimi için Yardım nasıl eriştiğini nasıl Yardım uygulanmıştır ve kapsayıcı yardımıyla Denetim Yardımı olup tümleştirdik bağlıdır. Hakkında Yardım, tümleştirme hakkında daha fazla bilgi için [MSDN Kitaplığı](http://go.microsoft.com/fwlink/p/?linkid=150542) Web sitesi, "Ekleyerek Context-Sensitive yardımcı olmak için bir MFC ActiveX denetimi" arayın.

   Bu seçeneği belirlediğinizde, bunu ekler `AboutBox` denetimi proje denetim sınıftaki yöntemi (C*ProjName*Ctrl.cpp) ve proje gönderme Haritası'na AboutBox ekler. Varsayılan olarak, bu seçenek seçilidir.

- **En iyi duruma getirilmiş çizim kodu**

   Kapsayıcı OnDraw yöntemini otomatik olarak tüm düzenlendi, aynı cihaz bağlamına çizilir kapsayıcı denetimlerini yükler olduğunu belirtir. Bu özellik hakkında daha fazla bilgi için bkz. [denetim çizimini iyileştirme](../../mfc/optimizing-control-drawing.md).

- **Penceresiz etkinleştirme**

   Bu etkinleştirildiğinde denetim bir pencere üretmez belirtir. Penceresiz etkinleştirme için dikdörtgen olmayan veya saydam denetimler sağlar ve bir penceresi olan bir denetim sistemi daha az yüke gerektirir penceresiz denetime gerektirir. Penceresiz denetime bir kesilmemiş cihaz bağlamı veya titreşimsiz etkinleştirme için izin vermez. Penceresiz etkinleştirme 1996 önce oluşturulan kapsayıcıları desteklemez. Bu seçenek kullanma hakkında daha fazla bilgi için bkz. [penceresiz etkinleştirme sağlama](../../mfc/providing-windowless-activation.md).

- **Kesilmemiş bir cihaz bağlamı**

   Geçersiz kılmalar [COleControl::GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags) denetimi üst bilgisindeki (*projname*ctrl.h) çağrısı devre dışı bırakmak için `IntersectClipRect` tarafından yapılan `COleControl`. Bu seçeneği belirlediğinizde, bir küçük hızı avantaj sağlar. Seçerseniz **penceresiz etkinleştirme**, bu özellik kullanılabilir değil. Daha fazla bilgi için [kesilmemiş bir cihaz bağlamı kullanma](../../mfc/using-an-unclipped-device-context.md).

- **Titreşimsiz etkinleştirme**

   Çizim işlemleri ve denetim etkin ve etkin olmayan durumlar arasında gerçekleşen eşlik eden görsel titreşimini ortadan kaldırır. Seçerseniz **penceresiz etkinleştirme**, bu özellik kullanılabilir değil. Bu seçeneği ayarladığınızda `noFlickerActivate` bayrağı tarafından döndürülen bayrakları biridir [COleControl::GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Daha fazla bilgi için [titreşimsiz etkinleştirme sağlama](../../mfc/providing-flicker-free-activation.md).

- **Nesne Ekle iletişim kutusunda kullanılabilir**

   Denetim içinde kullanılabilir olacağını belirtir **Nesne Ekle** etkin kapsayıcılar için iletişim kutusu. Bu seçeneği belirlediğinizde `afxRegInsertable` bayrağı tarafından döndürülen bayrakları biridir `AfxOleRegisterControlClass`. Kullanarak **Nesne Ekle** iletişim kutusu, varolan nesneleri bileşik bir belgeye veya bir kullanıcı yeni oluşturulan ekleyebilirsiniz.

- **Etkin olmadığında fare işaretçisi bildirimleri**

   Denetimin etkin olup olmadığını fare işaretçisi bildirimler, bir denetim olanağı sağlar. Bu seçeneği belirlediğinizde `pointerInactive` bayrağı tarafından döndürülen bayrakları biridir [COleControl::GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Bu seçenek kullanma hakkında daha fazla bilgi için bkz. [sağlama fare etkileşimi sırada etkin olmayan](../../mfc/providing-mouse-interaction-while-inactive.md).

- **Basit bir çerçeve denetimi görür**

   Denetim için bit OLEMISC_SIMPLEFRAME ayarlayarak bir denetimin diğer denetimler için kapsayıcı olduğunu belirtir. Daha fazla bilgi için üzerinde [MSDN Kitaplığı](http://go.microsoft.com/fwlink/p/?linkid=150542) Web sitesi, "Basit çerçeve Site kapsama" arayın.

- **Zaman uyumsuz olarak özelliklerini yükler**

   Önceki herhangi bir zaman uyumsuz veri sıfırlanmasını sağlar ve yeni bir yük zaman uyumsuz özelliğinin denetimin başlatır.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[Denetim Adları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-names-mfc-activex-control-wizard.md)

