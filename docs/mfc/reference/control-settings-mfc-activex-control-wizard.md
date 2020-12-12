---
description: 'Hakkında daha fazla bilgi edinin: denetim ayarları, MFC ActiveX Denetim Sihirbazı'
title: Denetim Ayarları, MFC ActiveX Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.settings
helpviewer_keywords:
- MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
ms.openlocfilehash: 31e8c5fd257128e17017d3d0fa801fc812f99397
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301600"
---
# <a name="control-settings-mfc-activex-control-wizard"></a>Denetim Ayarları, MFC ActiveX Denetim Sihirbazı

Denetimin nasıl davranmasını istediğinizi belirtmek için sihirbazın bu sayfasını kullanın. Örneğin, denetimi standart Windows Denetim türleri üzerinde temel alabilir, davranışını ve görünümünü iyileştirir veya denetimin diğer denetimler için bir kapsayıcı olarak davrandığını belirtebilirsiniz.

Bu sayfada denetimin verimliliğini en üst düzeye çıkarmak için seçenekleri seçme hakkında daha fazla bilgi için bkz. [MFC ActiveX denetimleri: iyileştirme](../../mfc/mfc-activex-controls-optimization.md).

## <a name="uielement-list"></a>UIElement Listesi

- **Temelinde denetim oluştur**

   Bu listede, denetiminizin devralması gereken denetim türünü seçebilirsiniz. Liste, için kullanılabilir olan denetim sınıflarının `CreateWindowEx` ve commctrl. h içinde belirtilen ek ortak denetimlerin bir alt kümesidir. Seçiminiz, `PreCreateWindow` *ProjName* CTRL. cpp dosyasındaki işlevindeki denetimin stilini belirler. Daha fazla bilgi için bkz. [MFC ActiveX denetimleri: altsınıflama a Windows Control](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).

   |Denetim|Açıklama|
   |-------------|-----------------|
   |**Bu**|Bir Windows düğme denetimi|
   |**Öğesı**|Windows Birleşik giriş kutusu denetimi|
   |**Düzenle**|Windows düzenleme kutusu denetimi|
   |**KUTUSUNA**|Bir Windows liste kutusu denetimi|
   |**KAYDıRMA çubuğu**|Bir Windows kaydırma çubuğu denetimi|
   |**SE**|Bir Windows statik denetimi|
   |**msctls_hotkey32**|Sık kullanılan anahtar ortak denetimi|
   |**msctls_progress32**|İlerleme çubuğu ortak denetimi|
   |**msctls_statusbar32**|Bir durum çubuğu ortak denetimi|
   |**msctls_trackbar32**|İzleme çubuğu ortak denetimi|
   |**msctls_updown32**|Bir döndürme düğmesi (veya yukarı açılan) ortak denetim|
   |**SysAnimate32**|Animasyon ortak denetimi|
   |**SysHeader32**|Üst bilgi ortak denetimi|
   |**SysListView32**|Liste görünümü ortak denetimi|
   |**SysTabControl32**|Bir sekme ortak denetimi|
   |**SysTreeView32**|Ağaç görünümü ortak denetimi|

- **Görünür olduğunda etkinleştirir**

   Erişildiğinde denetim için bir pencere oluşturulduğunu belirtir. Varsayılan olarak, **görünür olduğunda etkinleştir** seçeneği belirlenir. Kapsayıcı gerektirene kadar denetim etkinleştirmesini erteetmek istiyorsanız (örneğin, bir kullanıcı fareyle tıkladığında), bu seçeneği temizleyin. Bu özellik devre dışı bırakıldığında, denetim, gerekli olana kadar pencere oluşturma masrafına tabi değildir. Daha fazla bilgi için bkz. [Visible 'Da etkinleştir seçeneğini](../../mfc/turning-off-the-activate-when-visible-option.md)kapatma.

- **Çalışma zamanında görünmez**

   Denetimin çalışma zamanında Kullanıcı arabirimine sahip olmadığını belirtir. Zamanlayıcı, görünmez olmasını isteyebileceğiniz bir denetim türüdür.

- **Hakkında bir kutu iletişim kutusu vardır**

   Denetimin, sürüm numarasını ve telif hakkı bilgilerini görüntüleyen standart Windows **hakkında** iletişim kutusu olduğunu belirtir.

   > [!NOTE]
   > Kullanıcının denetim için yardım 'a nasıl eriştiği, yardım 'ı nasıl uyguladığınıza ve denetim yardımını kapsayıcı yardımı ile tümleştirdiğinize bağlıdır.

   Bu seçeneği belirlediğinizde, `AboutBox` denetim yöntemini proje denetim sınıfına ekler (C *ProjName* CTRL. cpp) ve proje dağıtım eşlemesine AboutBox ekler. Varsayılan olarak, bu seçenek seçilidir.

- **İyileştirilmiş çizim kodu**

   Kapsayıcının özgün GDI nesnelerini, aynı cihaz bağlamına çizilen tüm kapsayıcı denetimleri yapıldıktan sonra otomatik olarak geri yüklemelerini belirtir. Bu özellik hakkında daha fazla bilgi için bkz. [Denetim çizimini iyileştirme](../../mfc/optimizing-control-drawing.md).

- **Penceresiz etkinleştirme**

   Denetimin etkinleştirildiğinde bir pencere üretmemesini belirtir. Penceresiz etkinleştirme, dikdörtgensel olmayan veya saydam denetimlere izin verir ve penceresiz bir denetim, bir pencerenin gerektirdiği bir denetimden daha az sistem yükü gerektirir. Penceresiz bir denetim, kırpılmamış bir cihaz bağlamı veya titreşimsiz etkinleştirmeye izin vermez. 1996 ' den önce oluşturulan kapsayıcılar penceresiz etkinleştirmeyi desteklemez. Bu seçeneğin nasıl kullanılacağı hakkında daha fazla bilgi için, bkz. [penceresiz etkinleştirme sağlama](../../mfc/providing-windowless-activation.md).

- **Kırpılmamış cihaz bağlamı**

   Tarafından yapılan çağrıyı devre dışı bırakmak için denetim üstbilgisindeki [Cotacontrol:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags) (*ProjName* CTRL. h) değerini geçersiz kılar `IntersectClipRect` `COleControl` . Bu seçeneği belirlediğinizde, küçük bir hız avantajı sağlar. **Penceresiz etkinleştirme**' yi seçerseniz bu özellik kullanılamaz. Daha fazla bilgi için bkz. [kırpılmamış cihaz bağlamı kullanma](../../mfc/using-an-unclipped-device-context.md).

- **Titreşimsiz etkinleştirme**

   Çizim işlemlerini ve denetimin etkin ve etkin olmayan durumları arasında gerçekleşen görsel titreşimi ortadan kaldırır. **Penceresiz etkinleştirme**' yi seçerseniz bu özellik kullanılamaz. Bu seçeneği belirlediğinizde, `noFlickerActivate` bayrak [Coelcontrol:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags)tarafından döndürülen bayraklardan biridir. Daha fazla bilgi için bkz. [Flicker-Free etkinleştirme sağlama](../../mfc/providing-flicker-free-activation.md).

- **Nesne Ekle iletişim kutusunda kullanılabilir**

   Denetimin, etkin kapsayıcılar için **nesne Ekle** iletişim kutusunda kullanılabilir olacağını belirtir. Bu seçeneği belirlediğinizde `afxRegInsertable` bayrak, tarafından döndürülen bayraklardan biridir `AfxOleRegisterControlClass` . Kullanıcı, **nesne Ekle** iletişim kutusunu kullanarak yeni oluşturulan veya varolan nesneleri bileşik bir belgeye ekleyebilir.

- **Etkin olmadığında fare işaretçisi bildirimleri**

   Denetimin etkin olup olmadığını fare işaretçisi bildirimlerinin işlemesini sağlar. Bu seçeneği belirlediğinizde, `pointerInactive` bayrak [Coelcontrol:: GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags)tarafından döndürülen bayraklardan biridir. Bu seçeneğin nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [etkin olmadığında fare etkileşimi sağlama](../../mfc/providing-mouse-interaction-while-inactive.md).

- **Basit bir çerçeve denetimi görevi görür**

   Denetimin OLEMISC_SIMPLEFRAME bitini ayarlayarak denetimin diğer denetimler için bir kapsayıcı olduğunu belirtir. Daha fazla bilgi için bkz. [basit çerçeve site içerme](/windows/win32/com/simple-frame-site-containment).

- **Özellikleri zaman uyumsuz olarak yükler**

   Önceki zaman uyumsuz verilerin sıfırlanmasına izin vermez ve denetimin zaman uyumsuz özelliğinin yeni bir yükünü başlatır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimi Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Uygulama ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[Denetim adları, MFC ActiveX denetimi Sihirbazı](../../mfc/reference/control-names-mfc-activex-control-wizard.md)
