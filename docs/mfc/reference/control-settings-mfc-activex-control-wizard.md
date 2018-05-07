---
title: Denetim ayarları, MFC ActiveX Denetim Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.ctl.settings
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2161cea739d918bc0f5772a6cb08c29082a6e670
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="control-settings-mfc-activex-control-wizard"></a>Denetim Ayarları, MFC ActiveX Denetim Sihirbazı
Sihirbazın bu sayfası nasıl hareket etmesi için denetimi istediğinizi belirtmek için kullanın. Örneğin, standart Windows Denetim türleri denetiminde temel kendi davranış ve görünümünü en iyi duruma getirme veya denetimi diğer denetimler için bir kapsayıcı olarak davranamaz gösterir.  
  
 Denetim verimliliğini en üst düzeye çıkarmak için bu sayfadaki seçenekler seçme hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: iyileştirme](../../mfc/mfc-activex-controls-optimization.md).  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Göre denetimi oluşturma**  
 Bu listede denetiminizi alması gerektiğini denetim türünü seçebilirsiniz. Bir alt kümesi için kullanılabilen Denetim sınıfları listesidir `CreateWindowEx` ve commctrl.h içinde belirtilen ek ortak denetimleri. Seçiminizi denetim stilini belirler `PreCreateWindow` işlevi *ProjName*Ctrl.cpp dosya. Daha fazla bilgi için bkz: [MFC ActiveX denetimleri: bir Windows denetimini alt sınıf yapma](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
|Denetim|Açıklama|  
|-------------|-----------------|  
|**DÜĞMESİ**|Windows düğme denetimi|  
|**COMBOBOX**|Bir Windows birleşik giriş kutusu denetimi|  
|**DÜZENLEME**|Bir Windows düzenleme kutusu denetimi|  
|**LISTBOX**|Windows liste kutusu denetimi|  
|**KAYDIRMA ÇUBUĞU**|Windows kaydırma çubuğu denetimi|  
|**STATİK**|Windows statik denetimi|  
|**msctls_hotkey32**|Sık kullanılan tuş ortak denetimi|  
|**msctls_progress32**|Bir ilerleme çubuğu ortak denetimi|  
|**msctls_statusbar32**|Bir durum çubuğu ortak denetimi|  
|**msctls_trackbar32**|Ortak denetim çubuğu İzle|  
|**msctls_updown32**|Bir değer değiştirme düğmesi (veya yukarı-aşağı) ortak denetimi|  
|**SysAnimate32**|Animasyon ortak denetimi|  
|**SysHeader32**|Üstbilgi ortak denetimi|  
|**SysListView32**|Liste Görünümü ortak denetimi|  
|**SysTabControl32**|Sekme ortak denetimi|  
|**SysTreeView32**|Ağaç görünümü ortak denetimi|  
  
 **Görünür zaman etkinleştirir**  
 Bunu erişildiğinde bir pencere için Denetim oluşturulduğunu belirtir. Varsayılan olarak, **etkinleştirir görünür olduğunda** seçeneği işaretlidir. Denetimi etkinleştirme (örneğin bir kullanıcı fare tıkladığında) gerektiriyor kapsayıcı kadar erteleme istiyorsanız bu seçeneği temizleyin. Bu özellik devre dışı olduğunda gerekli olana kadar denetimi penceresi oluşturma gider azaltabilir. Daha fazla bilgi için bkz: [görünürken etkinleştir seçeneğini devre dışı kapatma](../../mfc/turning-off-the-activate-when-visible-option.md).  
  
 **Çalışma zamanında görünmez**  
 Denetimin çalışma zamanında kullanıcı arabirimi olmadan olduğunu belirtir. Süreölçer görünmez olmasını isteyebilirsiniz denetim türüdür.  
  
 **Hakkında kutusunu iletişim**  
 Denetim standart Windows olduğunu belirtir **hakkında** iletişim kutusu, sürüm numarasını ve telif hakkı bilgileri görüntüler.  
  
> [!NOTE]
>  Kullanıcı denetimi için Yardım nasıl eriştiğini nasıl Yardım uyguladık ve kapsayıcı yardımıyla denetim Yardım olup tümleşik bağlıdır. Yardım, üzerinde tümleştirme hakkında daha fazla bilgi için [MSDN Kitaplığı](http://go.microsoft.com/fwlink/p/?linkid=150542) Web sitesi, "Ekleme Context-Sensitive yardımcı olmak için bir MFC ActiveX denetimi" arayın.  
  
 Bu seçeneği belirlediğinizde, ekler `AboutBox` kontrol proje denetim sınıftaki yöntemi (C*ProjName*Ctrl.cpp) ve AboutBox proje gönderme Haritası ekler. Varsayılan olarak, bu seçenek seçilidir.  
  
 **En iyi duruma getirilmiş çizim kodu**  
 Kapsayıcı özgün GDI nesneleri otomatik olarak tüm aynı cihaz bağlamı çizilir, Çekildi kapsayıcı denetimleri yükler olduğunu belirtir. Bu özellik hakkında daha fazla bilgi için bkz: [denetim çizimini iyileştirme](../../mfc/optimizing-control-drawing.md).  
  
 **Penceresiz etkinleştirme**  
 Etkinleştirildiğinde, bu denetimi bir pencere üretmez belirtir. Penceresiz etkinleştirme için dikdörtgen olmayan veya saydam denetimleri sağlar ve daha az sistem yüke penceresine sahip bir denetim gerektiren penceresiz bir denetim gerektirir. Penceresiz bir denetim kesilmemiş cihaz bağlamı veya titreşimsiz etkinleştirme için izin vermiyor. 1996 önce oluşturulan kapsayıcıları penceresiz etkinleştirme desteklemez. Bu seçenek kullanma hakkında daha fazla bilgi için bkz: [penceresiz etkinleştirme sağlama](../../mfc/providing-windowless-activation.md).  
  
 **Kesilmemiş cihaz bağlamı**  
 Geçersiz kılmaları [COleControl::GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags) denetim üstbilgisinde (*projname*ctrl.h) çağrısı devre dışı bırakmak için `IntersectClipRect` tarafından yapılan `COleControl`. Bu seçeneği belirlediğinizde, bir küçük hızı avantaj sağlar. Seçerseniz **penceresiz etkinleştirme**, bu özellik kullanılamıyor. Daha fazla bilgi için bkz: [kesilmemiş bir cihaz bağlamı kullanma](../../mfc/using-an-unclipped-device-context.md).  
  
 **Titreşimsiz etkinleştirme**  
 Çizim işlemler ve denetim etkin ve etkin olmayan durumlar arasında oluşan eşlik eden visual titreşimi ortadan kaldırır. Seçerseniz **penceresiz etkinleştirme**, bu özellik kullanılamıyor. Bu seçeneği ayarlarken `noFlickerActivate` bayrağı tarafından döndürülen bayrakları biridir [COleControl::GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Daha fazla bilgi için bkz: [titreşimsiz etkinleştirme sağlama](../../mfc/providing-flicker-free-activation.md).  
  
 **Nesne Ekle iletişim kutusunda kullanılabilir**  
 Denetim kullanılabilir olacağını belirtir **Nesne Ekle** etkin kapsayıcıları için iletişim kutusu. Bu seçeneği belirlediğinizde `afxRegInsertable` bayrağı tarafından döndürülen bayrakları biridir `AfxOleRegisterControlClass`. Kullanarak **Nesne Ekle** iletişim kutusu, varolan nesneleri bileşik bir belgeye veya bir kullanıcı yeni oluşturulan ekleyebilirsiniz.  
  
 **Fare işaretçisini bildirimleri etkin olmadığında**  
 Denetim etkin olsun veya olmasın işlem fare işaretçisini bildirimleri denetimi sağlar. Bu seçeneği belirlediğinizde `pointerInactive` bayrağı tarafından döndürülen bayrakları biridir [COleControl::GetControlFlags](../../mfc/reference/colecontrol-class.md#getcontrolflags). Bu seçenek kullanma hakkında daha fazla bilgi için bkz: [sağlama fare etkileşimi sırasında etkin olmayan](../../mfc/providing-mouse-interaction-while-inactive.md).  
  
 **Basit çerçeve denetim görevi görür**  
 Ayarlayarak denetimi diğer denetimler için bir kapsayıcı olduğunu belirtir `OLEMISC_SIMPLEFRAME` denetimi için bit. Daha fazla bilgi için üzerinde [MSDN Kitaplığı](http://go.microsoft.com/fwlink/p/?linkid=150542) Web sitesi, "Basit çerçeve Site kapsama" arayın.  
  
 **Zaman uyumsuz olarak özelliklerini yükler**  
 Önceki herhangi bir zaman uyumsuz veri sıfırlanmasını sağlar ve denetim zaman uyumsuz özelliğinin yeni bir yük başlatır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Uygulama ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Denetim Adları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-names-mfc-activex-control-wizard.md)

