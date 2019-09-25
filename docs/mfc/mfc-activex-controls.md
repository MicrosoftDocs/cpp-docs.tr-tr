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
ms.openlocfilehash: a1c7bb070a75f4406556817163931f0707706c40
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "69508121"
---
# <a name="mfc-activex-controls"></a>MFC ActiveX Denetimleri

ActiveX denetimi, çok çeşitli OLE işlevlerini destekleyen ve birçok yazılım ihtiyaçlarına uyacak şekilde özelleştirilebilen bileşen nesne modeli (COM) tabanlı bir yeniden kullanılabilir yazılım bileşenidir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. Daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

ActiveX denetimleri, hem sıradan ActiveX denetim kapsayıcılarında hem de Internet üzerinde World Wide Web sayfalarında kullanılmak üzere tasarlanmıştır. Burada açıklandığı gibi MFC ile veya [Etkin Şablon kitaplığı (ATL)](../atl/active-template-library-atl-concepts.md)ile ActiveX denetimleri oluşturabilirsiniz.

Bir ActiveX denetimi kendi penceresinde kendisini çizebilir, olaylara yanıt verebilir (fare tıklamaları gibi) ve otomasyon nesnelerindeki özelliklere benzer özellikler ve Yöntemler içeren bir arabirim aracılığıyla yönetilebilir.

Bu denetimler, veritabanı erişimi, veri izleme veya grafikleme gibi birçok kullanım için geliştirilebilir. Taşınabilirlik özelliklerinin yanı sıra, ActiveX denetimleri, var olan OLE kapsayıcılarıyla uyumluluk ve menülerini OLE Container menülerle tümleştirme gibi ActiveX denetimleri için kullanılamayan özellikleri de destekler. Ayrıca, ActiveX denetimi, denetimin kullanıcı tarafından çağrılabilen Read\write özelliklerini ve bir dizi yöntemi kullanıma sunmasına olanak sağlayan Otomasyonu tamamen destekler.

Yalnızca etkin hale geldiğinde bir pencere oluşturmak için Penceresiz ActiveX denetimleri ve denetimleri oluşturabilirsiniz. Penceresiz denetimler uygulamanızın görüntülenmesini hızlandırır ve saydam ve dikdörtgen olmayan denetimlerin olmasını mümkün kılar. ActiveX denetim özelliklerini zaman uyumsuz olarak da yükleyebilirsiniz.

Bir ActiveX denetimi, herhangi bir OLE kapsayıcısında kullanılabilecek bir işlem içi sunucu (genellikle küçük bir nesne) olarak uygulanır. ActiveX denetiminin tam işlevselliğinin yalnızca, ActiveX denetimlerinin farkında olacak şekilde tasarlanan bir OLE kapsayıcısı içinde kullanıldığı durumlarda kullanılabileceğini unutmayın. ActiveX denetimlerini destekleyen kapsayıcıların listesi için bkz. [bağlantı noktası ActiveX denetimleri diğer uygulamalar](../mfc/containers-for-activex-controls.md) . Bundan sonra "Denetim kapsayıcısı" olarak adlandırılan bu kapsayıcı türü, denetimin özelliklerini ve yöntemlerini kullanarak ActiveX denetimini işleyebilir ve olaylar biçiminde ActiveX denetiminden bildirimler alır. Aşağıdaki şekilde bu etkileşim gösterilmektedir.

![ActiveX denetim kapsayıcısını ve denetimini birbirine yürütme](../mfc/media/vc37221.gif "ActiveX denetim kapsayıcısını ve denetimini birbirine yürütme") <br/>
Bir ActiveX Denetim kapsayıcısı ve bir pencereli ActiveX denetimi arasındaki etkileşim

ActiveX denetimlerinizi iyileştirmeye ilişkin bazı son bilgiler için bkz [. MFC ActiveX denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md).

MFC ActiveX denetimi oluşturmak için bkz. [ActiveX denetim projesi oluşturma](../mfc/reference/mfc-activex-control-wizard.md).

Daha fazla bilgi için bkz.:

- [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

- [Etkin Belgeler](../mfc/active-documents.md)

- [ActiveX denetimlerini anlama](/windows/win32/com/activex-controls)

- [Mevcut bir ActiveX denetimini Internet 'te kullanılacak şekilde yükseltme](../mfc/upgrading-an-existing-activex-control.md)

##  <a name="_core_basic_components_of_an_activex_control"></a>ActiveX denetiminin temel bileşenleri

Bir ActiveX denetimi, bir denetim kapsayıcısı ve kullanıcıyla verimli bir şekilde etkileşim kurmak için çeşitli programlama öğeleri kullanır. Bunlar sınıf [Coelcontrol](../mfc/reference/colecontrol-class.md), olay tetikleme işlevleri kümesi ve bir dağıtım haritası.

Geliştirdiğiniz her ActiveX denetim nesnesi, `COleControl`MFC temel sınıfından güçlü bir özellik kümesi devralır. Bu özellikler yerinde etkinleştirme ve otomasyon mantığını içerir. `COleControl`, bir MFC penceresi nesnesiyle aynı işlevselliğe sahip denetim nesnesini ve olayları tetikleyebilme olanağını sağlayabilir. `COleControl`Ayrıca, bir pencerenin sağladığı bazı işlevlerden (fare yakalama, klavye odağı, kaydırma) yardımcı olması için kapsayıcılarından yararlanan [Penceresiz denetimler](../mfc/providing-windowless-activation.md)sağlayabilir, ancak çok daha hızlı bir görüntü sunun.

Denetim sınıfı öğesinden `COleControl`türetildiğinden, belirli koşullar karşılandığında denetim kapsayıcısına olaylar olarak adlandırılan iletileri gönderme veya "tetikleme" özelliğini devralır. Bu olaylar, denetimde önemli bir şeyler olduğunda denetim kapsayıcısını bilgilendirmek için kullanılır. Olaya parametreler ekleyerek denetim kapsayıcısına bir olayla ilgili ek bilgiler gönderebilirsiniz. ActiveX denetim olayları hakkında daha fazla bilgi için MFC ActiveX denetimleri [makalesine bakın: Olaylar](../mfc/mfc-activex-controls-events.md).

Son öğe, denetim kullanıcısına bir işlev kümesini (yöntemler olarak adlandırılır) ve öznitelikleri (özellikler olarak adlandırılır) göstermek için kullanılan bir dağıtım eşlemedir. Özellikler Denetim kapsayıcısının veya denetim kullanıcısının denetimi çeşitli yollarla işlemesini sağlar. Kullanıcı denetimin görünüşünü değiştirebilir, denetimin belirli değerlerini değiştirebilir veya denetimin koruduğu belirli bir veri parçasına erişim gibi denetim istekleri yapabilir. Bu arabirim denetim geliştiricisi tarafından belirlenir ve **sınıf görünümü**kullanılarak tanımlanır. ActiveX denetim yöntemleri ve özellikleri hakkında daha fazla bilgi için bkz [. MFC ActiveX denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md) ve [Özellikler](../mfc/mfc-activex-controls-properties.md).

##  <a name="_core_interaction_between_controls_with_windows_and_activex_control_containers"></a>Windows ve ActiveX denetim kapsayıcıları ile denetimler arasındaki etkileşim

Denetim kapsayıcısı içinde bir denetim kullanıldığında, iletişim kurmak için iki mekanizma kullanır: özellikleri ve yöntemleri gösterir ve olayları harekete geçirilir. Aşağıdaki şekilde, bu iki mekanizmaların nasıl uygulandığı gösterilmektedir.

![ActiveX denetimi kapsayıcında iletişim kurar](../mfc/media/vc37222.gif "ActiveX denetimi kapsayıcında iletişim kurar") <br/>
Bir ActiveX Denetim kapsayıcısı ve ActiveX denetimi arasındaki iletişim

Önceki şekilde, diğer OLE arabirimlerinin (Otomasyon ve olayların yanı sıra) denetimler tarafından nasıl işlendiği de gösterilmektedir.

Bir denetimin kapsayıcı ile olan iletişimi tarafından `COleControl`gerçekleştirilir. Kapsayıcının isteklerinin `COleControl` bazılarını işlemek için denetim sınıfına uygulanan üye işlevlerini çağırır. Tüm yöntemler ve bazı özellikler bu şekilde işlenir. Denetim sınıfı, öğesinin `COleControl`üye işlevlerini çağırarak kapsayıcı ile iletişim de başlatabilir. Olaylar bu şekilde tetiklenir.

##  <a name="_core_active_and_inactive_states_of_an_activex_control"></a>ActiveX denetiminin etkin ve etkin olmayan durumları

Bir denetimin iki temel durumu vardır: etkin ve devre dışı. Geleneksel olarak, bu durumlar denetimin bir pencere içerip içermediğini ayırt etmişti. Etkin bir denetimde pencere vardı; etkin olmayan bir denetim değildi. Penceresiz etkinleştirmenin tanıtılmasıyla, bu ayrım artık evrensel değildir, ancak yine de birçok denetim için geçerli olur.

Penceresiz bir [Denetim](../mfc/providing-windowless-activation.md) etkin olduğunda, kapsayıcısından fare yakalama, klavye odağı, kaydırma ve diğer pencere hizmetlerini çağırır. Ayrıca, [etkin olmayan denetimlere fare etkileşimi sağlayabilir](../mfc/providing-mouse-interaction-while-inactive.md)ve [bir pencere oluşturmak için etkinleştirilene kadar bekleyen](../mfc/turning-off-the-activate-when-visible-option.md)denetimler oluşturabilirsiniz.

Pencereye sahip bir denetim etkin hale geldiğinde Denetim kapsayıcısı, Kullanıcı ve Windows ile tamamen etkileşim kurabilir. Aşağıdaki şekilde, ActiveX denetimi, Denetim kapsayıcısı ve işletim sistemi arasındaki iletişimin yolları gösterilmektedir.

![Etkin pencereli ActiveX denetiminde ileti işleme](../mfc/media/vc37223.gif "Etkin pencereli ActiveX denetiminde ileti işleme") <br/>
Pencereli ActiveX denetiminde Windows Ileti Işleme (etkin olduğunda)

##  <a name="_core_serializing_activex_elements"></a>Getir

Bazen Kalıcılık olarak adlandırılan verileri seri hale getirme özelliği, denetimin özelliğinin değerini kalıcı depolama alanına yazmasını sağlar. Denetimler daha sonra, nesnenin durumu depodan okunarak yeniden oluşturulabilir.

Bir denetimin depolama ortamına erişim sağlamaktan sorumlu olmadığına unutmayın. Bunun yerine, denetimin kapsayıcısı uygun zamanlarda kullanılmak üzere bir depolama ortamı ile denetim sağlamaktan sorumludur. Serileştirme hakkında daha fazla bilgi için bkz [. MFC ActiveX denetimleri: Serileştirme](../mfc/mfc-activex-controls-serializing.md). Serileştirme iyileştirilmesi hakkında daha fazla bilgi için bkz. ActiveX denetimlerinde [kalıcılığı ve başlatmayı iyileştirme](../mfc/optimizing-persistence-and-initialization.md) : İyileştirme.

##  <a name="_core_installing_activex_control_classes_and_tools"></a>ActiveX denetim sınıfları ve araçları yükleme

Visual C++'Yı yüklediğinizde MFC ActiveX denetim sınıfları ve perakende ve hata ayıklama ActiveX denetimi çalışma zamanı dll 'leri kurulum 'da ActiveX denetimleri seçildiyse otomatik olarak yüklenir (varsayılan olarak seçilidir).

Varsayılan olarak, ActiveX denetim sınıfları ve araçları, \Program Files\Microsoft Visual Studio .NET altında aşağıdaki alt dizinlere yüklenir:

- **\Common7\Tools**

   Test kapsayıcı dosyalarını (TstCon32. exe ' nin yanı sıra yardım dosyalarını) içerir.

- **\Vc7\atlmfc\include**

   MFC ile ActiveX denetimleri geliştirmek için gereken içerme dosyalarını içerir

- **\Vc7\atlmfc\src\mfc**

   MFC 'deki belirli ActiveX denetim sınıfları için kaynak kodunu içerir

- **\Vc7\atlmfc\lib**

   MFC ile ActiveX denetimleri geliştirmek için gereken kitaplıkları içerir

MFC ActiveX denetimleri için de örnekler vardır. Bu örnekler hakkında daha fazla bilgi için bkz [. Controls Samples: MFC tabanlı ActiveX denetimleri](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
