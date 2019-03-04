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
ms.openlocfilehash: a33273c46562e8beba12910702d9ddc1a092575d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262616"
---
# <a name="mfc-activex-controls"></a>MFC ActiveX Denetimleri

ActiveX denetimi Bileşen Nesne Modeli (çok çeşitli OLE işlevselliği destekleyen ve çok sayıda yazılım gereksinimlerini karşılayacak şekilde özelleştirilebilir COM) dayalı bir yeniden kullanılabilir yazılım bileşenidir.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. Daha fazla bilgi için [ActiveX denetimlerini](activex-controls.md).

ActiveX denetimleri, sıradan bir ActiveX denetim kapsayıcıları hem World Wide Web sayfalarında Internet'teki kullanmak için tasarlanmıştır. Burada veya ile açıklanan, MFC ActiveX denetimleri oluşturabilirsiniz [Etkin Şablon kitaplığı (ATL)](../atl/active-template-library-atl-concepts.md).

ActiveX denetimi kendisini çizebilirsiniz kendi penceresinde (örneğin, fare tıklamaları) olaylara yanıt verme ve özelliklere ve yöntemlere benzer Otomasyon nesneleri içeren bir arabirim üzerinden yönetiliyor olabilir.

Bu denetimler veritabanı erişim gibi pek çok kullanımı için izleme veya grafik verilerini geliştirilebilir. Kendi taşınabilirlik yanı sıra, daha önce mevcut olmayan özellikler mevcut OLE kapsayıcıları ile uyumluluk ve bunların menüleri OLE kapsayıcı menüleri ile tümleştirme olanağı gibi ActiveX denetimleri için ActiveX denetimlerini destekler. Ayrıca, bir ActiveX denetimini sürücüsünde okuma/yazma özellikleri ve bir dizi denetimi kullanıcı tarafından çağrılabilen bir yöntem kullanıma sunmak denetimin izin Otomasyonu, tam olarak destekler.

ActiveX denetimlerinin penceresiz ve etkin olduğunda, yalnızca bir pencere oluşturma denetimleri oluşturabilirsiniz. Penceresiz denetimleri, uygulamanızın görünümünü hızlandırmak ve saydam ve dikdörtgen olmayan denetimler olan mümkün kılar. ActiveX denetimi özelliklerini zaman uyumsuz olarak da yükleyebilirsiniz.

ActiveX denetimi tüm OLE kapsayıcısı içinde kullanılabilmesi için bir işlem sunucusu (küçük nesne genellikle) olarak uygulanır. Tam işlevselliğini bir ActiveX denetimini ActiveX denetimlerini kullanan olacak şekilde tasarlanan OLE kapsayıcısı içinde kullanıldığında kullanılabilir olduğunu unutmayın. Bkz: [diğer uygulamalar için bağlantı noktası ActiveX denetimlerini](../mfc/containers-for-activex-controls.md) ActiveX denetimlerini destekleyen kapsayıcılar listesi. Bundan sonra "Denetim kapsayıcısı," olarak adlandırılan bu kapsayıcı türü denetimin özellikleri ve yöntemleri kullanarak bir ActiveX denetimini çalışabilir ve olayları şeklinde ActiveX denetiminden bildirimleri alır. Aşağıdaki şekil, bu etkileşim gösterilmektedir.

![ActiveX denetimi kapsayıcısı ve denetim etkileşim özelliği](../mfc/media/vc37221.gif "etkileşim özelliği, ActiveX denetimi kapsayıcısı ve Denetim") <br/>
Pencereli bir ActiveX denetimini ActiveX denetimi kapsayıcısı arasındaki etkileşimi

ActiveX denetimleri, en iyi duruma getirme bazı son için bilgi [MFC ActiveX denetimleri: En iyi duruma getirme](../mfc/mfc-activex-controls-optimization.md).

MFC ActiveX denetimi oluşturmak için bkz [bir ActiveX denetimi projesi oluşturma](../mfc/reference/mfc-activex-control-wizard.md).

Daha fazla bilgi için bkz.:

- [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

- [Etkin Belgeler](../mfc/active-documents.md)

- [ActiveX denetimleri anlama](/windows/desktop/com/activex-controls)

- [Internet'te kullanılacak mevcut bir ActiveX denetimini güncelleştirme](../mfc/upgrading-an-existing-activex-control.md)

##  <a name="_core_basic_components_of_an_activex_control"></a> ActiveX denetimi temel bileşenleri

ActiveX denetimi, çeşitli programlama öğeleri verimli bir şekilde bir denetim kapsayıcısı ve kullanıcı ile etkileşim kurmak için kullanır. Sınıf bunlar [COleControl](../mfc/reference/colecontrol-class.md), bir olay tetikleyicisinin tetikleme işlevler kümesi ve gönderim eşleme.

Geliştirdiğiniz her ActiveX denetimi nesne güçlü bir özellikler kümesi kendi MFC taban sınıfından devralan `COleControl`. Bu özellikler, yerinde etkinleştirme ve Otomasyon mantığı içerir. `COleControl` Denetim nesnesi olayları tetiklemesine olanağı yanı sıra bir MFC pencere nesnesi ile aynı işlevlere sağlayabilirsiniz. `COleControl` de sağlayabilirsiniz [penceresiz denetimleri](../mfc/providing-windowless-activation.md), bir pencere, kullanan bazı işlevlerini ile ilgili Yardım için kapsayıcı üzerindeki sağlar (fare yakalama, klavye odağı kaydırma), ancak çok daha hızlı görüntü sunar.

Denetim sınıfı öğesinden türetildiği için `COleControl`gönderebilir devralan veya "fire," iletileri, olaylar, belirli koşullar karşılandığında denetim kapsayıcısı çağrılır. Bu olaylar, önemli bir şeyler olduğunda denetim kapsayıcısı denetiminde olur bildirmek için kullanılır. Olaya parametreleri ekleyerek denetim kapsayıcısı için bir olay hakkında ek bilgi gönderebilir. ActiveX denetim olayları hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri: Olayları](../mfc/mfc-activex-controls-events.md).

Son öğeden bir dizi (yöntemler olarak adlandırılır) işlevleri ve denetim kullanıcı özniteliklerine (özellikler olarak adlandırılan) kullanıma sunmak için kullanılan gönderme haritasıdır. Denetim kapsayıcısı veya denetim kullanıcı denetimi çeşitli yollarla işlemek için özellikleri sağlar. Kullanıcı denetiminin görünümünü değiştirme, denetimin belirli değerleri değiştirin veya belirli bir parça denetiminde veri erişim denetiminin isteklerde. Bu arabirim denetim geliştiricisi tarafından belirlenir ve kullanılarak tanımlanan **sınıf görünümü**. ActiveX denetim yöntemleri ve özellikleri hakkında daha fazla bilgi için bkz: makaleleri [MFC ActiveX denetimleri: Yöntemleri](../mfc/mfc-activex-controls-methods.md) ve [özellikleri](../mfc/mfc-activex-controls-properties.md).

##  <a name="_core_interaction_between_controls_with_windows_and_activex_control_containers"></a> Windows denetimleriyle ActiveX denetim kapsayıcıları arasındaki etkileşimi

Bir denetim kapsayıcısı bir denetimi kullanıldığında, iki mekanizma iletişim kurmak için kullanır: özellikler ve yöntemler sunar ve olayları tetikler. Aşağıdaki şekil, bu iki mekanizma nasıl uygulandığını gösterir.

![ActiveX denetimi kapsayıcısı ile iletişim kuran](../mfc/media/vc37222.gif "ActiveX denetimi kapsayıcısı ile iletişim kurar") <br/>
Bir ActiveX denetimini ActiveX denetimi kapsayıcısı arasındaki iletişimi

Önceki şekilde, ayrıca diğer OLE arabirimleri (yanı sıra otomasyon ve olaylar) denetimleri tarafından nasıl işlendiğini gösterilmektedir.

Tüm kapsayıcı ile denetim iletişim tarafından gerçekleştirilir `COleControl`. Kapsayıcının isteklerinin bazılarını işlemek için `COleControl` üye denetim sınıfına uygulanan işlevleri çağırır. Tüm yöntemler ve bazı özellikler bu şekilde ele alınır. Denetimin sınıf de kapsayıcı ile iletişimi üye işlevlerini çağırarak başlatabilirsiniz `COleControl`. Bu şekilde harekete geçirilen olaylar.

##  <a name="_core_active_and_inactive_states_of_an_activex_control"></a> Etkin ve etkin olmayan bir ActiveX denetimini durumları

Bir denetimi iki temel durum vardır: etkin ve etkin değil. Geleneksel olarak, bu durumları denetimi bir pencere kaldı tarafından ayırt. Etkin bir denetim bir pencere vardı; Etkin olmayan bir denetim belirtmiyor. Penceresiz etkinleştirme tanıtımıyla Bu ayrım artık Evrensel değildir ancak yine de birçok denetim için geçerlidir.

Olduğunda bir [penceresiz denetime](../mfc/providing-windowless-activation.md) çağırır fare yakalama, klavye odağına, kaydırma ve pencere hizmetlerinden kapsayıcısı etkin gider. Ayrıca [etkin olmayan bir denetim için fare etkileşimi sağlamak](../mfc/providing-mouse-interaction-while-inactive.md), yanı sıra, denetimleri oluşturma [bir pencere oluşturmak için etkinleştirilmiş bekleyin](../mfc/turning-off-the-activate-when-visible-option.md).

Bir denetim bir pencere etkin olduğunda, tam denetim kapsayıcısı, kullanıcı ve Windows ile etkileşim kurabilirsiniz. Aşağıdaki şekilde ActiveX denetimini, denetimi kapsayıcısı ve işletim sistemi arasındaki iletişim yollarını gösterir.

![İleti işleme etkin pencere ActiveX denetiminde](../mfc/media/vc37223.gif "ileti etkin pencere ActiveX denetiminde işleme") <br/>
Windows ileti işleme bir pencereli ActiveX denetiminde (etkin olduğunda)

##  <a name="_core_serializing_activex_elements"></a> Seri hale getirme

Denetimin özelliklerini değerini kalıcı depolama alanına yazılacak bazen kalıcı adlandırılır, verileri seri hale getirme olanağı sağlar. Denetimleri nesnenin durumu depodan okuyarak daha sonra yeniden oluşturulabilir.

Bir denetim depolama ortamına erişim almak için sorumlu olmadığını unutmayın. Bunun yerine, denetimin kapsayıcı uygun zamanlarda kullanmak için bir depolama ortamına ile denetim sağlamaktan sorumludur. Seri hale getirme hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri: Seri hale getirme](../mfc/mfc-activex-controls-serializing.md). Seri hale getirme en iyi duruma getirme hakkında daha fazla bilgi için bkz: [en iyi duruma getirme kalıcılığı ve başlatmayı](../mfc/optimizing-persistence-and-initialization.md) ActiveX denetimleri: En iyi duruma getirme.

##  <a name="_core_installing_activex_control_classes_and_tools"></a> ActiveX denetim sınıfları ve araçlarını yükleme

Visual C++'ı yüklediğinizde, MFC ActiveX sınıfları ve perakende denetlemek ve ActiveX denetimlerini (varsayılan olarak seçilidir) kurulumunda seçtiyseniz, çalışma zamanı dll otomatik olarak yüklenir ActiveX denetiminde hata ayıklama.

Varsayılan olarak, ActiveX denetim sınıfları ve araçları, Visual Studio .NET \Program altındaki sonraki alt dizinlerde yüklenir:

- **\Common7\Tools**

   Test kapsayıcısı dosyaları (TstCon32.exe hem de Yardım dosyaları) içerir.

- **\Vc7\atlmfc\include**

   MFC ActiveX denetimleri geliştirmek için gereken dosyaları içerir

- **\Vc7\atlmfc\src\mfc**

   MFC içinde belirli bir ActiveX denetim sınıfları için kaynak kodunu içerir

- **\Vc7\atlmfc\lib**

   MFC ActiveX denetimleri geliştirmek için gereken kitaplıkları içerir.

MFC ActiveX denetimleri için örnekleri vardır. Bu örnekler hakkında daha fazla bilgi için bkz. [denetimleri örnekleri: MFC tabanlı ActiveX denetimleri](../visual-cpp-samples.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
