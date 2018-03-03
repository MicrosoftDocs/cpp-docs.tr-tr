---
title: MFC ActiveX denetimleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MFC ActiveX Controls (MFC)
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c06b66be2dd9b982fc925aa69483a58fcc4799dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls"></a>MFC ActiveX Denetimleri
ActiveX denetimi, Bileşen Nesne Modeli (çok çeşitli OLE işlevselliğini destekleyen ve çok sayıda yazılım gereksinimlerine uyacak şekilde özelleştirilmiş COM) dayalı bir yeniden kullanılabilir yazılım bileşenidir. ActiveX denetimleri, hem sıradan ActiveX denetimi kapsayıcıları ve World Wide Web sayfalarında Internet üzerindeki kullanımı için tasarlanmıştır. Burada veya ile açıklanan MFC ActiveX denetimleri oluşturabilirsiniz [Etkin Şablon kitaplığı (ATL)](../atl/active-template-library-atl-concepts.md).  
  
 ActiveX denetimi kendisini çizebilirsiniz kendi penceresinde (örneğin, fare tıklamaları) olaylara yanıt ve özellikleri ve yöntemleri Otomasyon nesneleri benzer içeren bir arabirim üzerinden yönetilir.  
  
 Bu denetimler veritabanı erişimi gibi birçok kullanımı için izleme veya Grafikleme veri geliştirilebilir. Kendi taşınabilirlik yanı sıra, ActiveX denetimlerini önceden kullanılabilir varolan OLE kapsayıcıları uyumluluğunu ve OLE kapsayıcı menülerle kendi menüleri tümleştirmek yeteneği gibi ActiveX denetimlerini özelliklerini destekler. Ayrıca, bir ActiveX denetimini sürücüsünde okuma/yazma özellikleri ve bir dizi denetim kullanıcı tarafından çağrılabilir yöntem kullanıma sunmak denetimi sağlar Otomasyon tam olarak destekler.  
  
 Penceresiz ActiveX denetimlerini ve etkin olduğunda, yalnızca bir pencere oluşturma denetimleri oluşturabilirsiniz. Penceresiz denetimleri, uygulamanızın görünümünü hızlandırmak ve saydam ve dikdörtgen olmayan denetimleriniz olanaklı hale getirir. ActiveX denetimi özellikleri zaman uyumsuz olarak da yükleyebilirsiniz.  
  
 ActiveX denetimi tüm OLE kapsayıcı kullanılabilmesi için bir işlem sunucusu (genellikle küçük bir nesne) olarak uygulanır. ActiveX denetimi tam işlevselliğini yalnızca ActiveX denetimlerini haberdar olmak üzere tasarlanmış bir OLE kapsayıcısı içinde kullanıldığında kullanılabilir olduğunu unutmayın. Bkz: [diğer uygulamalar için bağlantı noktası ActiveX denetimlerini](../mfc/containers-for-activex-controls.md) ActiveX denetimlerini destekleyen kapsayıcılar listesi. Bundan böyle bir "denetimi kapsayıcısı," olarak adlandırılan bu kapsayıcı türü bir ActiveX denetimini ve denetim özellikleri ve yöntemleri kullanarak çalışabilir ve olayları biçiminde ActiveX denetiminden bildirimleri alır. Aşağıdaki şekilde bu etkileşimi gösterilmektedir.  
  
 ![ActiveX denetimi kapsayıcısı ve denetim Interplay](../mfc/media/vc37221.gif "vc37221")  
ActiveX denetimi kapsayıcısı ve bir pencereli ActiveX denetimi arasındaki etkileşimi  
  
 ActiveX denetimleri en iyi duruma getirme bazı son hakkında bilgi için bkz: [MFC ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md).  
  
 MFC ActiveX denetimi oluşturmak için bkz: [bir ActiveX denetimi projesi oluşturma](../mfc/reference/mfc-activex-control-wizard.md).  
  
 Daha fazla bilgi için bkz.:  
  
-   [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)  
  
-   [Etkin Belgeler](../mfc/active-documents.md)  
  
-   [ActiveX denetimleri anlama](http://msdn.microsoft.com/library/windows/desktop/ms693753)  
  
-   [Internet'te kullanılacak varolan bir ActiveX denetimini güncelleştirme](../mfc/upgrading-an-existing-activex-control.md)  
  
##  <a name="_core_basic_components_of_an_activex_control"></a>Bir ActiveX denetiminin temel bileşenler  
 ActiveX denetimi çeşitli programlama öğeleri verimli bir denetim kapsayıcısı ile ve kullanıcıyla etkileşim kurmak için kullanır. Sınıf bunlar [COleControl](../mfc/reference/colecontrol-class.md), bir dizi olay tetikleme işlevleri ve gönderim eşleme.  
  
 Geliştirdiğiniz her ActiveX denetimi nesne güçlü bir özellikler kümesi, MFC taban sınıfından devralıyor `COleControl`. Bu özellikler yerinde etkinleştirme ve Otomasyon mantığını içerir. `COleControl`Denetim nesnesi ile aynı işlevselliği bir MFC pencere nesnesi yanı sıra, olayları yangın olanağı sağlayabilir. `COleControl`Ayrıca sağlayabilir [penceresiz denetimleri](../mfc/providing-windowless-activation.md), hangi kullanıcıların kapsayıcı bazı işlevleri ile ilgili Yardım için bir pencere Bel sağlar (fare yakalama, klavye odağını kaydırma), ancak çok daha hızlı görüntü sunar.  
  
 Denetim sınıfı türetilen çünkü `COleControl`gönderebilir devralır veya "yangın," iletileri, olaylar, belirli koşullar karşılandığında denetimi kapsayıcısı için çağrılır. Bu olaylar, önemli bir şey olduğunda denetimi kapsayıcısı denetiminde olur bildirmek için kullanılır. Olaya parametreleri ekleyerek denetimi kapsayıcısı için bir olay hakkında ek bilgi gönderebilir. ActiveX denetim olayları hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: olaylar](../mfc/mfc-activex-controls-events.md).  
  
 Bir dizi işlevleri (yöntemleri olarak adlandırılır) ve denetim kullanıcı öznitelikleri (özellikleri olarak adlandırılır) kullanıma sunmak için kullanılan bir gönderme harita son öğedir. Özellikler denetimi kapsayıcısı ya da Denetim çeşitli şekillerde işlemek için denetim kullanıcı izin verir. Kullanıcı denetiminin görünümünü değiştirme, denetimi belirli değerlerini değiştirmek veya belirli bir denetim tutar veri erişim denetiminin isteklerde. Bu arabirim denetimi geliştirici tarafından belirlenir ve kullanılarak tanımlanan **sınıf görünümü**. ActiveX denetimi yöntemleri ve özellikleri hakkında daha fazla bilgi için makalelerine bakın [MFC ActiveX denetimleri: yöntemler](../mfc/mfc-activex-controls-methods.md) ve [özellikleri](../mfc/mfc-activex-controls-properties.md).  
  
##  <a name="_core_interaction_between_controls_with_windows_and_activex_control_containers"></a>Windows ile denetimleri ve ActiveX denetimi kapsayıcıları arasındaki etkileşimi  
 Bir denetim denetimi kapsayıcısı içinde kullanıldığında, iki mekanizma iletişim kurmak için kullandığı: özellikleri ve yöntemleri oluşturur ve olay tetikler. Aşağıdaki şekilde, bu iki mekanizma nasıl uygulandığını gösterir.  
  
 ![ActiveX denetimi kapsayıcısı ile iletişim kurar](../mfc/media/vc37222.gif "vc37222")  
ActiveX denetimi kapsayıcısı ve bir ActiveX denetimi arasındaki iletişim  
  
 Önceki şekil, ayrıca diğer OLE arabirimleri (yanında, otomasyon ve olaylar) denetimleri tarafından nasıl işleneceğini gösterir.  
  
 Tüm kapsayıcısı ile bir denetimin iletişimin tarafından gerçekleştirilir `COleControl`. Bazı kapsayıcının isteklerini işlemek için **COleControl** üye denetim sınıfına uygulanan işlevleri çağırır. Tüm yöntemleri ve bazı özellikler bu şekilde ele alınır. Denetimin sınıf de kapsayıcı ile iletişim üye işlevlerini çağırarak başlatabilirsiniz `COleControl`. Bu şekilde olaylar.  
  
##  <a name="_core_active_and_inactive_states_of_an_activex_control"></a>Etkin ve etkin olmayan bir ActiveX denetimini durumları  
 Bir denetim iki temel durumlara sahiptir: etkin ve etkin değil. Geleneksel olarak, bu durumu denetimi bir pencere kaldı tarafından ayırt. Etkin bir denetim bir pencere vardı; Etkin olmayan denetimi belirtmiyor. Penceresiz etkinleştirme giriş, bu ayrım artık Evrensel değil, ancak birçok denetimleri için hala geçerlidir.  
  
 Zaman bir [penceresiz denetim](../mfc/providing-windowless-activation.md) gider çağırır fare yakalama, klavye odağı, kaydırma ve pencere hizmetlerinden kapsayıcısı etkin. Ayrıca [etkin olmayan denetimler için fare etkileşimi sağlayan](../mfc/providing-mouse-interaction-while-inactive.md), yanı sıra denetimleri oluşturmak [bir pencere oluşturmak için etkinleştirilinceye kadar bekleyin](../mfc/turning-off-the-activate-when-visible-option.md).  
  
 Bir pencere denetim etkin olduğunda, tam denetimi kapsayıcısı, kullanıcı ve Windows ile etkileşemeyebilirsiniz. Aşağıdaki şekilde ActiveX denetimi, Denetim kapsayıcı ve işletim sistemi arasındaki iletişim yolları gösterir.  
  
 ![İleti etkin pencereli ActiveX denetiminde işleme](../mfc/media/vc37223.gif "vc37223")  
Windows ileti bir pencereli ActiveX denetiminde (etkin olduğunda) işleme  
  
##  <a name="_core_serializing_activex_elements"></a>Seri hale getirme  
 Bazen kalıcı da adlandırılır verilerini seri hale getirmek olanağı özelliklerini değerini kalıcı depolama alanına yazmak denetim sağlar. Denetimleri sonra depolama biriminden nesnenin durumu okuyarak yeniden oluşturulabilir.  
  
 Bir denetim depolama ortamına erişimi almak için sorumlu olmadığını unutmayın. Bunun yerine, denetimin kapsayıcı uygun zamanlarda kullanmak için bir depolama ortamına ile denetimi sağlamaktan sorumludur. Seri hale getirme hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: seri hale getirme](../mfc/mfc-activex-controls-serializing.md). Seri hale getirme en iyi duruma getirme hakkında daha fazla bilgi için bkz: [en iyi duruma getirme kalıcılığı ve başlatmayı](../mfc/optimizing-persistence-and-initialization.md) ActiveX denetimleri: iyileştirme.  
  
##  <a name="_core_installing_activex_control_classes_and_tools"></a>ActiveX denetim sınıfları ve araçlarını yükleme  
 Visual C++ yüklediğinizde, MFC ActiveX sınıfları ve perakende kontrol ve hata ayıklama ActiveX denetimini ActiveX denetimleri (varsayılan olarak seçilidir) kurulumunda seçtiyseniz, çalışma zamanı DLL'leri otomatik olarak yüklenir.  
  
 Varsayılan olarak, ActiveX denetim sınıfları ve araçları, \Program Visual Studio .NET altında aşağıdaki dizinlerindeki yüklenir:  
  
-   **\Common7\Tools**  
  
     Test kapsayıcısı dosyaları (TstCon32.exe, hem de Yardım dosyaları) içerir.  
  
-   **\Vc7\atlmfc\include**  
  
     MFC ActiveX denetimleriyle geliştirmek için gereken dosyaları içerir  
  
-   **\Vc7\atlmfc\src\mfc**  
  
     MFC içinde belirli ActiveX denetim sınıfları için kaynak kodunu içerir  
  
-   **\Vc7\atlmfc\lib**  
  
     MFC ActiveX denetimleriyle geliştirmek için gereken kitaplıklar içerir  
  
 MFC ActiveX denetimleri için örnek vardır. Bu örnekler hakkında daha fazla bilgi için bkz: [denetimleri örnekleri: MFC-Based ActiveX denetimleri](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
