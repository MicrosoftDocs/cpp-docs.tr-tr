---
title: MFC ActiveX Denetimleri
ms.date: 11/19/2018
f1_keywords:
- MFC ActiveX Controls (MFC)
helpviewer_keywords:
- COleControl class [MFC], MFC ActiveX controls
- ActiveX controls [MFC], MFC
- containers [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], serializing
- MFC ActiveX controls [MFC], containers
- serialization [MFC], MFC ActiveX controls
- dispatch maps [MFC], for MFC ActiveX controls
- MFC ActiveX controls [MFC], active/inactive state
- events [MFC], ActiveX controls
- MFC ActiveX controls [MFC]
ms.assetid: c911fb74-3afc-4bf3-a0f5-7922b14d9a1b
ms.openlocfilehash: e9cc38eebed0b1f8e0932e89ef1452261aefd7dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365436"
---
# <a name="mfc-activex-controls"></a>MFC ActiveX Denetimleri

ActiveX denetimi, çok çeşitli OLE işlevselliğini destekleyen ve birçok yazılım gereksinimlerine uyacak şekilde özelleştirilebilen Bileşen Nesne Modeli'ne (COM) dayalı yeniden kullanılabilir bir yazılım bileşenidir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. Daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

ActiveX denetimleri hem sıradan ActiveX kontrol kaplarında hem de Internet'te, World Wide Web sayfalarında kullanılmak üzere tasarlanmıştır. Burada açıklanan MFC veya [Active Template Library (ATL)](../atl/active-template-library-atl-concepts.md)ile ActiveX denetimleri oluşturabilirsiniz.

ActiveX denetimi kendi penceresinde kendini çizebilir, olaylara (fare tıklamaları gibi) yanıt verebilir ve Otomasyon nesnelerindekine benzer özellikler ve yöntemler içeren bir arabirim aracılığıyla yönetilebilir.

Bu denetimler veritabanı erişimi, veri izleme veya grafik gibi birçok kullanım için geliştirilebilir. ActiveX, taşınabilirliklerinin yanı sıra, activex denetimlerinde daha önce mevcut olmayan, mevcut OLE kapsayıcılarıyla uyumluluk ve menülerini OLE kapsayıcı menüleriyle tümleştirme olanağı gibi destek özelliklerini denetler. Buna ek olarak, ActiveX denetimi, denetimin okuma\yazma özelliklerini ve denetim kullanıcısı tarafından çağrılabilen bir dizi yöntemi ortaya çıkarmasını sağlayan Otomasyonu tam olarak destekler.

Yalnızca etkin olduklarında bir pencere oluşturan penceresiz ActiveX denetimleri ve denetimleri oluşturabilirsiniz. Penceresiz denetimler uygulamanızın ekranını hızlandırır ve saydam ve dikdörtgen olmayan denetimlere sahip olmayı mümkün kılar. ActiveX denetim özelliklerini eşit olarak da yükleyebilirsiniz.

ActiveX denetimi, herhangi bir OLE kapsayıcısında kullanılabilecek bir işlem sunucusu (genellikle küçük bir nesne) olarak uygulanır. ActiveX denetiminin tam işlevselliğinin yalnızca ActiveX denetimleri hakkında kullanılmak üzere tasarlanmış bir OLE kapsayıcısı içinde kullanıldığında kullanılabileceğini unutmayın. ActiveX denetimlerini destekleyen kapsayıcıların listesi için [Diğer Uygulamalara Bağlantı Noktası ActiveX Denetimleri](../mfc/containers-for-activex-controls.md) bölümüne bakın. Bundan böyle "denetim kapsayıcısı" olarak adlandırılan bu kapsayıcı türü, denetimin özelliklerini ve yöntemlerini kullanarak ActiveX denetimini çalıştırabilir ve olaylar biçiminde ActiveX denetiminden bildirimler alır. Aşağıdaki şekil bu etkileşimi göstermektedir.

![ActiveX kontrol konteyneri ve kontrolünün etkileşimi](../mfc/media/vc37221.gif "ActiveX kontrol konteyneri ve kontrolünün etkileşimi") <br/>
ActiveX Kontrol Kapsayıcısı ile Pencereli ActiveX Denetimi Arasındaki Etkileşim

ActiveX denetimlerinizi en iyi duruma getirilmesi yle ilgili bazı yeni bilgiler için [MFC ActiveX Denetimleri: Optimizasyon'a](../mfc/mfc-activex-controls-optimization.md)bakın.

MFC ActiveX denetimi oluşturmak için [bkz.](../mfc/reference/mfc-activex-control-wizard.md)

Daha fazla bilgi için bkz.

- [ActiveX Kontrol Kapları](../mfc/activex-control-containers.md)

- [Aktif Belgeler](../mfc/active-documents.md)

- [ActiveX Denetimlerini Anlama](/windows/win32/com/activex-controls)

- [Varolan ActiveX Denetimini Internet'te Kullanılacak Yükseltme](../mfc/upgrading-an-existing-activex-control.md)

## <a name="basic-components-of-an-activex-control"></a><a name="_core_basic_components_of_an_activex_control"></a>ActiveX Denetiminin Temel Bileşenleri

ActiveX denetimi, bir denetim kapsayıcısı ve kullanıcıyla verimli bir şekilde etkileşim kurmak için çeşitli programöğeleri kullanır. Bunlar [coleControl](../mfc/reference/colecontrol-class.md)sınıfı, bir dizi olay çıkarma işlevi ve bir sevk haritasıdır.

Geliştirdiğiniz her ActiveX denetim nesnesi, `COleControl`MFC taban sınıfından güçlü bir özellik kümesi ni devralır. Bu özellikler yerinde etkinleştirme ve Otomasyon mantığını içerir. `COleControl`denetim nesnesine MFC pencere nesnesi ile aynı işlevselliği ve olayları ateşleme olanağı sağlayabilir. `COleControl`pencerenin sağladığı bazı işlevlerle (fare yakalama, klavye odağı, kaydırma) yardımcı olmak için kapsayıcılarına güvenen [penceresiz denetimler](../mfc/providing-windowless-activation.md)de sağlayabilir, ancak çok daha hızlı ekran sunar.

Denetim `COleControl`sınıfı, belirli koşullar yerine getirildiğinde, olaylar olarak adlandırılan iletileri gönderme veya "ateş etme" özelliğinden türediği için, denetim kabına gelir. Bu olaylar, denetimde önemli bir şey olduğunda denetim kapsayıcısını bildirmek için kullanılır. Bir olay hakkında ek bilgileri, olaya parametreler ekleyerek denetim kapsayıcısına gönderebilirsiniz. ActiveX denetim olayları hakkında daha fazla bilgi için [MFC ActiveX Denetimleri makalesine bakın: Olaylar.](../mfc/mfc-activex-controls-events.md)

Son öğe, bir dizi işlevi (yöntem olarak adlandırılır) ve öznitelikleri (özellikleri) denetim kullanıcısına ortaya çıkarmak için kullanılan bir gönderme eşlemidir. Özellikler, denetim kapsayıcısının veya denetim kullanıcısının denetimi çeşitli şekillerde işlemesine olanak sağlar. Kullanıcı denetimin görünümünü değiştirebilir, denetimin belirli değerlerini değiştirebilir veya denetimin koruduğu belirli bir veri parçasına erişmek gibi denetim isteklerini yapabilir. Bu arabirim, denetim geliştiricisi tarafından belirlenir ve **Sınıf Görünümü**kullanılarak tanımlanır. ActiveX denetim yöntemleri ve özellikleri hakkında daha fazla bilgi için [MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md) ve [Özellikler](../mfc/mfc-activex-controls-properties.md)makalelerini görün.

## <a name="interaction-between-controls-with-windows-and-activex-control-containers"></a><a name="_core_interaction_between_controls_with_windows_and_activex_control_containers"></a>Denetimler ile Windows ve ActiveX Denetim Kapları Arasındaki Etkileşim

Bir denetim kapsayıcı içinde kullanıldığında, iletişim kurmak için iki mekanizma kullanır: özellikleri ve yöntemleri ortaya çıkarır ve olayları ateşler. Aşağıdaki şekil, bu iki mekanizmanın nasıl uygulandığını göstermektedir.

![ActiveX kontrolü konteyneri ile iletişim kurar](../mfc/media/vc37222.gif "ActiveX kontrolü konteyneri ile iletişim kurar") <br/>
ActiveX Kontrol Konteyneri ile ActiveX Kontrolü Arasındaki İletişim

Önceki şekil ayrıca diğer OLE arabirimlerinin (otomasyon ve olayların yanı sıra) denetimler tarafından nasıl işleneceğini de göstermektedir.

Bir denetimin kapsayıcı ile tüm iletişimi `COleControl`. Kapsayıcının bazı isteklerini işlemek `COleControl` için, denetim sınıfında uygulanan üye işlevleri çağırır. Tüm yöntemler ve bazı özellikler bu şekilde işlenir. Denetiminizin sınıfı, üye işlevlerini arayarak kapsayıcıyla `COleControl`iletişimi de başlatabilir. Olaylar bu şekilde ateşlenir.

## <a name="active-and-inactive-states-of-an-activex-control"></a><a name="_core_active_and_inactive_states_of_an_activex_control"></a>ActiveX Denetiminin Etkin ve Etkin Olmayan Durumları

Denetimin iki temel durum vardır: etkin ve etkin olmayan. Geleneksel olarak, bu durumlar denetimbir pencere olup olmadığı ile ayırt edildi. Etkin bir denetimin bir penceresi vardı; etkin olmayan bir denetim olmadı. Penceresiz etkinleştirme nin başlatılmasıyla, bu ayrım artık evrensel değildir, ancak yine de birçok denetim için geçerlidir.

[Penceresiz](../mfc/providing-windowless-activation.md) bir denetim etkin olduğunda, kapsayıcısından fare yakalama, klavye odağı, kaydırma ve diğer pencere hizmetlerini çağırır. Ayrıca [etkin olmayan denetimlere fare etkileşimi sağlayabilir](../mfc/providing-mouse-interaction-while-inactive.md)ve bir pencere oluşturmak için [etkinleştirilene kadar bekleyen](../mfc/turning-off-the-activate-when-visible-option.md)denetimler oluşturabilirsiniz.

Pencereli bir denetim etkin hale geldiğinde, denetim kapsayıcısı, kullanıcı ve Windows ile tam olarak etkileşim kurabilir. Aşağıdaki şekilde ActiveX denetimi, denetim konteyneri ve işletim sistemi arasındaki iletişim yollarını gösterilmektedir.

![Aktif pencereli ActiveX kontrolünde Msg işleme](../mfc/media/vc37223.gif "Aktif pencereli ActiveX kontrolünde Msg işleme") <br/>
Pencereli ActiveX Denetiminde Windows İleti İşleme (Etkin olduğunda)

## <a name="serialization"></a><a name="_core_serializing_activex_elements"></a>Seri -leştirme

Bazen kalıcılık olarak da adlandırılan verileri serihale etme yeteneği, denetimin kalıcı depolamaya özelliklerinin değerini yazmasına olanak tanır. Denetimler daha sonra depolama dan nesnenin durumu okuyarak yeniden oluşturulabilir.

Depolama ortamına erişim sağlamakiçin bir denetimin sorumlu olmadığını unutmayın. Bunun yerine, denetimin kapsayıcısı, denetimin uygun zamanlarda kullanılacak bir depolama ortamıyla sağlanmasından sorumludur. Serileştirme hakkında daha fazla bilgi için [MFC ActiveX Denetimleri makalesine bakın: Serileştirme.](../mfc/mfc-activex-controls-serializing.md) Serileştirmeyi en iyi duruma getirilmesi hakkında bilgi için ActiveX Denetimlerinde [Kalıcılığı ve Başlatmayı En İyi Duruma Çıkarma:](../mfc/optimizing-persistence-and-initialization.md) Optimizasyon'a bakın.

## <a name="installing-activex-control-classes-and-tools"></a><a name="_core_installing_activex_control_classes_and_tools"></a>ActiveX Kontrol Sınıfları ve Araçları Nın Yüklenmesi

Visual C++'ı yüklediğinizde, MFC ActiveX denetim sınıfları ve ActiveX denetimleri Kurulum'da seçilirse activex denetimleri otomatik olarak yüklenir (varsayılan olarak seçilirler).

Varsayılan olarak, ActiveX denetim sınıfları ve araçları \Program Files\Microsoft Visual Studio .NET altında aşağıdaki alt dizinlerde yüklenir:

- **\Common7\Araçlar**

   Test Kapsayıcısı dosyalarını (TstCon32.exe ve Yardım dosyalarını) içerir.

- **\Vc7\atlmfc\ekle**

   MFC ile ActiveX denetimleri geliştirmek için gereken dahil dosyaları içerir

- **\Vc7\atlmfc\src\mfc**

   MFC'deki belirli ActiveX denetim sınıfları için kaynak kodu içerir

- **\Vc7\atlmfc\lib**

   MFC ile ActiveX denetimleri geliştirmek için gereken kitaplıkları içerir

MFC ActiveX denetimleri için örnekler de vardır. Bu örnekler hakkında daha fazla bilgi için [bkz: Denetim Örnekleri: MFC Tabanlı ActiveX Denetimleri](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı Arabirimi Elemanları](../mfc/user-interface-elements-mfc.md)
