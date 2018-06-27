---
title: 'TN035: Visual C++ ile birden çok kaynak dosya ve üstbilgi dosyası kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.resources
dev_langs:
- C++
helpviewer_keywords:
- resource files, multiple
- TN035
ms.assetid: 1f08ce5e-a912-44cc-ac56-7dd93ad73fb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c23e0a978ab8cb3c63566bd8d5ce64ecb2a80d4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952421"
---
# <a name="tn035-using-multiple-resource-files-and-header-files-with-visual-c"></a>TN035: Visual C++'da Birden Fazla Kaynak Dosya ve Üstbilgi Dosyası Kullanma
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not Visual C++ kaynak Düzenleyici birden çok kaynak dosyaları nasıl desteklediğini açıklar ve proje veya birden çok proje ve o desteğinden nasıl yararlanabileceğinizi arasında paylaşılan tek bir paylaşılan üstbilgi dosyaları. Bu Not Bu soruların yanıtları:  
  
-   Bir projeye birden çok kaynak dosyaları ve/veya üst bilgi dosyaları ve bunu nasıl bölüneceği istediğinizde  
  
-   Ortak üstbilgisi nasıl paylaşır. H dosyasının iki arasında. RC dosyaları  
  
-   Nasıl birden çok proje kaynakları bölün. RC dosyaları  
  
-   Nasıl (ve araçları) yapı arasındaki bağımlılıkları da yönetmeye. RC. CPP, ve. H dosyaları  
  
 Projenize bir ek kaynak dosya eklerseniz, ClassWizard eklenen dosya kaynaklarında tanımaz bilmeniz gerekir.  
  
 Bu Not gibi yukarıdaki soruları yanıtlamak için yapılandırılmış:  
  
- **Nasıl Visual C++ yöneten kaynak dosyaları ve üst bilgi dosyaları'na genel bakış** nasıl Visual C++'ta kaynak kümesi içeren komutu birden fazla kaynak dosya ve üstbilgi dosyası aynı projede kullanmanıza olanak sağlayan bir genel bakış sağlar.  
  
- **AppWizard oluşturulan analizini. RC ve. H dosyaları** AppWizard oluşturulmuş bir uygulama tarafından kullanılan birden çok kaynağı ve başlık dosyaları bakar. Bu dosyalar ek kaynak dosya ve üstbilgi dosyası projenize eklemek isteyebilirsiniz için iyi bir modeli işlevini görür.  
  
- **Ek üstbilgi dosyaları dahil olmak üzere** burada birden çok üst bilgi dosyaları eklemek isteyebilirsiniz ve bunun nasıl yapılacağı ayrıntıları sağlar açıklar.  
  
- **Üstbilgi dosyası iki arasında paylaştırma. RC dosyaları** bir üstbilgi dosyası birden çok arasında nasıl paylaşabilirsiniz gösterir. RC dosyaları farklı projelerinde veya belki de aynı projede.  
  
- **Aynı projede birden çok kaynak dosyalarını kullanma** burada birden çok projenize bölmeniz isteyebilirsiniz açıklar. RC dosyaları ve bunun nasıl yapılacağı ayrıntıları sağlar.  
  
- **Zorlama düzenlenemez Visual C++ dosyalarının** nasıl Visual C++ değil düzenleyin ve kasıtsız olarak özel bir kaynak yeniden biçimlendirin emin olabilirsiniz açıklar.  
  
- **Birden çok Visual tarafından C++ düzenlenebilir paylaşılan semboller yönetme. RC dosyaları** birden çok aynı simgeleri paylaşmayı açıklar. RC dosyaları ve nasıl yinelenen kimliği sayısal değerler atamaktan kaçının.  
  
- **Arasındaki bağımlılıkları yönetme. RC. CPP, ve. H dosyaları** nasıl gereksiz yeniden derlenmesi Visual C++ önler açıklar. Kaynak sembol dosyalarını bağımlı CPP dosyaları.  
  
- **Visual C++ yönetir kümesi içeren bilgilerini** nasıl Visual C++ (iç içe) birden çok izler hakkında teknik ayrıntılar sağlar. RC dosyaları ve birden çok üst bilgi dosyaları # tarafından include'd bir. RC dosyası.  
  
 **Kaynak dosya ve üstbilgi dosyası nasıl Visual C++ genel bakış yönetir**  
  
 Visual C++ tek bir yönetir. RC kaynak dosyasını ve karşılık gelen bir. H üstbilgi dosyası dosyaları sıkı şekilde bağlı bir çift olarak. Ne zaman düzenleme ve kaydetme kaynaklarında bir. RC dosya, dolaylı olarak düzenleyin ve simgeleri ilgili kaydedin. H dosyası. Açın ve birden çok Düzenle rağmen. RC dosyaları (Visual C++'ın MDI kullanıcı arabirimini kullanarak) için bir defada herhangi verilen. RC dosyası dolaylı olarak tam olarak bir karşılık gelen üst bilgi dosyasını düzenleyin.  
  
 **Sembol üstbilgi dosyası**  
  
 Varsayılan olarak, Visual C++ her zaman karşılık gelen üstbilgi dosyası kaynak adları. Kaynak dosyasının (örn., UYGULAMAM adı bakılmaksızın H. RC). Kullanarak **kaynağını içeren** komutunu **Görünüm** Visual C++'ta menüsünde Sembol üstbilgi dosyası dosyasında güncelleştirerek bu üstbilgi dosyası adını değiştirebilirsiniz **kümesi içeren**iletişim kutusu.  
  
 **Salt okunur sembol yönergeleri**  
  
 Visual C++ yalnızca bir üst bilgi dosyası herhangi için verilen düzenler ancak. RC dosyası, Visual C++ ek salt okunur üstbilgi dosyalarında tanımlanan simge başvurularını destekler. Kullanarak **kaynağını içeren** komutunu **Görünüm** menü Visual C++'da, herhangi bir sayıda ek salt okunur üstbilgi dosyaları salt okunur sembol yönergeleri belirtebilirsiniz. İçinde yeni bir kaynak eklediğinizde "salt okunur" kısıtlama anlamına gelir. RC dosya salt okunur üstbilgi dosyasında tanımlanan bir simge kullanabilirsiniz; ancak kaynak silerseniz, simgenin salt okunur üstbilgi dosyasında tanımlanmış kalıyor. Bir salt okunur simgeye atanmış sayısal değer değiştirilemez.  
  
 **Derleme zamanı yönergeleri**  
  
 Visual C++ kaynak dosyaları, iç içe geçmiş bir burada da destekler. RC dosyası # içinde başka bir include'd. Düzenlediğinizde bir verilen. Visual C++, hesaptaki kaynakları kullanarak RC dosya #include'd dosyaları görünür değil. Ancak zaman derleyin. RC dosya #include'd dosyaları da derlenmiş. Kullanarak **kaynağını içeren** komutunu **Görünüm** menüsünde Visual C++'ta, herhangi bir sayıda belirtebilirsiniz #include'd. RC dosyaları derleme zamanı yönergeleri olarak.  
  
 Ne olacağını unutmayın Visual C++ okuyorsanız bir. RC dosya # başka bir kullanıcının include. RC dosya *değil* derleme zamanı yönergesi belirtilmiş. Visual C++ getirdiğinizde bu durumdan doğabilecek bir. Daha önce el ile bir metin düzenleyicisiyle koruma RC dosyası. Visual C++ zaman okur #include'd. RC dosyayı bu birleştirir # kaynakları üst include'd. RC dosyası. Üst kaydettiğinizde. RC dosya # değiştirilir, aslında deyimi, include # kaynakları include'd. Bu birleştirme olmasını istemiyorsanız, kaldırmalısınız # üst deyiminden include. RC dosya *önceki* Visual C++; okumak için Visual C++ kullanarak Ekle tekrar aynı # deyimi bir derleme zamanı yönerge olarak include.  
  
 Visual C++ kaydeder bir. RC yukarıdaki üç tür dosya kümesi içerir (sembol üstbilgi dosyası, salt okunur sembol yönergeleri ve bilgileri derleme zamanı yönergeleri) içinde # yönergeleri include *ve* TEXTINCLUDE kaynakları. Normalde, uğraşmanız gerekmez bir uygulama ayrıntılarını TEXTINCLUDE kaynakları açıklanacak [nasıl Visual C++ yönetir içeren bilgi kümesi](#_mfcnotes_tn035_set_includes).  
  
 **AppWizard oluşturulan analizini. RC ve. H dosyaları**  
  
 AppWizard tarafından üretilen uygulama kodunu inceleyerek, Visual C++ birden çok kaynak dosya ve üstbilgi dosyası nasıl yönettiğini içine değerli bilgiler sağlar. Varsayılan seçenekleri kullanarak AppWizard tarafından üretilen bir UYGULAMAM uygulaması aşağıda incelenmesi kod parçalarını arasındadır.  
  
 AppWizard oluşturulan uygulama birden çok kaynak dosyaları ve birden çok üst bilgi dosyaları, aşağıdaki çizimde özetlendiği gibi kullanır:  
  
```  
RESOURCE.H     AFXRES.H      
 \       /                
 \     /  
    MYAPP.RC 
 |  
 |                
    RES\MYAPP.RC2 
    AFXRES.RC 
    AFXPRINT.RC 
```  
  
 Visual C++ dosyası/kümesi içerir komutunu kullanarak bu birden çok dosya ilişkileri görüntüleyebilirsiniz.  
  
 MYAPP.RC  
 Visual C++ kullanarak Düzenle uygulama kaynak dosyası.  
  
 KAYNAK. H uygulamaya özgü üstbilgi dosyasıdır. Her zaman kaynak adı verilir. H AppWizard, Visual C++'ın varsayılan ile tutarlı olarak üstbilgi dosyası adlandırma. # Bu üstbilgi dosyası kaynak dosyasının (UYGULAMAM. işlemindeki ilk deyim için include RC):  
  
```  
//Microsoft Visual C++ generated resource script  
//  
#include "resource.h"  
```  
  
 RES\MYAPP.RC2  
 Visual C++ tarafından düzenlenebilir değildir ama derlenmiş en son bulunan kaynaklar içeriyor. EXE dosyası. Visual C++ sürümü kaynak (Bu sürümdeki yeni bir özellik) dahil olmak üzere standart kaynakların tümünü düzenleyebilirsiniz beri AppWizard varsayılan olarak, bu tür bir kaynaklar oluşturur. Bu dosyayı kendi özel biçimlendirilmiş kaynakları eklemek istediğiniz durumda boş bir dosya AppWizard tarafından oluşturulur.  
  
 Özel biçimlendirilmiş kaynaklar kullanırsanız, bunları RES\MYAPP için ekleyebilirsiniz. RC2 ve onları Visual C++ metin düzenleyicisi kullanarak düzenleyebilirsiniz.  
  
 AFXRES. RC ve AFXPRINT. RC framework'ün belirli özellikler tarafından gerekli standart kaynakları içerir. RES\MYAPP gibi. RC2, bu iki framework tarafından sağlanan kaynak dosyalarıdır # UYGULAMAM sonunda include'd. Derleme zamanı yönergeleri kümesi içeren iletişim kutusunun RC ve bunlar belirtilir. Bu nedenle, doğrudan görüntülediğinizde veya UYGULAMAM düzenlerken bu çerçevesi kaynakları düzenleyin. Visual C++ ' ta RC ancak uygulama ikili olarak derlenir. RES dosya ve son. EXE dosyası. Bunları değiştirmek için yordamları da dahil olmak üzere standart çerçevesi kaynakları hakkında daha fazla bilgi için bkz: [Teknik Not 23](../mfc/tn023-standard-mfc-resources.md).  
  
 AFXRES. H tanımlar standart simgeler gibi `ID_FILE_NEW`framework tarafından kullanıldı ve özellikle AFXRES kullanılır. RC. AFXRES. H ayrıca #include's WINRES. H WINDOWS kümesini içerir. Tarafından oluşturulan Visual C++ gerekli H. RC dosyaları yanı sıra AFXRES. RC. AFXRES içinde tanımlanan simgeler. H, uygulama kaynak dosyasının (UYGULAMAM. düzenlerken kullanılabilir RC). Örneğin, `ID_FILE_NEW` UYGULAMAM dosya yeni menü öğesi için kullanılır. RC'ın menü kaynağı. Değiştiremez veya bu framework tanımlı sembolleri silin.  
  
## <a name="_mfcnotes_tn035_including"></a> Ek üstbilgi dosyaları dahil olmak üzere  
  
 Yalnızca iki üst bilgi dosyaları AppWizard oluşturulan uygulama içerir: kaynak. H ve AFXRES. H. Yalnızca kaynak. H uygulama özeldir. Aşağıdaki durumlarda ek salt okunur üstbilgi dosyaları eklemeniz gerekebilir:  
  
 Üstbilgi dosyası birden çok proje veya aynı projenin birden çok parçaları arasında paylaşmak istediğiniz veya üstbilgi dosyası bir dış kaynak tarafından sağlanır.  
  
 Üst bilgi dosyasını biçimlendirme ve değiştirmek veya dosya kaydettiğinde filtrelemek için Visual C++ istiyor musunuz açıklamaları vardır. Örneğin, belki de, korumak istediğiniz #define's gibi simgesel aritmetik kullanın:  
  
```  
#define RED 0  
#define BLUE 1  
#define GREEN 2  
#define ID_COLOR_BUTTON 1001  
#define ID_RED_BUTTON (ID_COLOR_BUTTON + RED)  
#define ID_BLUE_BUTTON (ID_COLOR_BUTTON + BLUE)  
#define ID_GREEN_BUTTON (ID_COLOR_BUTTON + GREEN)  
```  
  
 Kullanarak ek salt okunur üstbilgi dosyaları içerebilir **kaynağını içeren** belirtmek için komut # olarak ikinci bir salt okunur simgesi yönergesi olarak deyimi include:  
  
```  
#include "afxres.h"  
#include "second.h"  
```  
  
 Yeni dosya ilişki diyagramı şimdi şöyle görünür:  
  
```  
    AFXRES.H 
RESOURCE.H     SECOND.H      
 \       /                
 \     /  
    MYAPP.RC 
 |  
 |                
    RES\MYAPP.RC2 
    AFXRES.RC 
    AFXPRINT.RC 
```  
  
 **Üstbilgi dosyası iki arasında paylaştırma. RC dosyaları**  
  
 Üstbilgi dosyası iki arasında paylaşmak isteyebilirsiniz. Farklı projelere ya da aynı projesi büyük olasılıkla RC dosyaları. Bunu yapmak için yalnızca her ikisi de yukarıda salt okunur yönergeleri teknik uygulayın. RC dosyaları. Durumda burada iki. RC dosyaları olan farklı uygulamalar için (farklı projeleri), sonuç aşağıdaki çizimde gösterilmiştir:  
  
```  
    RESOURCE.H AFXRES.H   RESOURCE.H    
 (for MYAPP1) SECOND.H   (for MYAPP2)               
 \       /     \       /             
 \     /       \     /               
    MYAPP1.RC MYAPP2.RC */    \        /     \ */      \      /       \              
RES\MYAPP1.RC2  AFXRES.RC     RES\MYAPP2.RC2                
    AFXPRINT.RC 
```  
  
 İkinci üstbilgi dosyası iki tarafından paylaşıldığı durumda. RC dosyaları aynı uygulamada (Proje) aşağıda ele alınmıştır.  
  
 **Aynı projede birden çok kaynak dosyalarını kullanma**  
  
 Visual C++ ve kaynak derleyicisi birden çok destekler. RC dosyaları aynı projede #include ait bir. RC dosyanın başka bir içinde. Birden çok iç içe geçme izin verilir. Projenizin kaynaklar birden çok bölmek için çeşitli nedenleri vardır. RC dosyaları:  
  
-   Kaynaklar birden çok bölerseniz kaynakları birden çok proje takım üyeleri arasında çok sayıda yönetmek daha kolaydır. RC dosyaları. Kaynak denetimi Yönetim Paketi dosyaları kullanıma alma ve değişiklikleri denetlemek için kullanabileceğiniz kaynakları birden fazla bölme kullanıyorsanız. RC dosyaları kaynakları yapılan değişiklikleri yönetme daha iyi denetleyebilmek verir.  
  
-   #İfdef, #endif, gibi önişlemci yönergeleri kullanmak istiyorsanız, ve #define, kaynaklarınızın bölümleri için bunları kaynak derleyicisi tarafından derlenen salt okunur kaynakları yalıtmak gerekir.  
  
-   Bileşen. RC dosyaları yükleyin ve Visual C++'ta daha hızlı bir bileşik kaydedin. RC dosyası.  
  
-   Bir metin düzenleyicisiyle okunabilir bir biçimde bir kaynak korumak istiyorsanız, onu tutmalısınız bir. Bir Visual C++ içinden ayrı RC dosyasını düzenler.  
  
-   Ardından kullanıcı tanımlı bir kaynak tarafından başka bir özel veri Düzenleyicisi yorumlanabilir bir ikili dosya veya metin form durumda tutmanıza ihtiyacınız varsa, onu ayrı bir tutmalısınız. Visual C++ onaltılık veri biçimi değiştirmez şekilde RC dosyası. . MFC Gelişmiş kavramları örnekteki WAV (ses) dosya kaynaklarını [SPEAKN](../visual-cpp-samples.md) iyi bir örnektir.  
  
 Yapabilecekleriniz # SANİYENİN include. Derleme zamanı yönergeleri kümesi içeren iletişim kutusunda RC:  
  
```  
#include "res\myapp.rc2"  // non-Visual C++ edited resources  
#include "second.rc"  // THE SECOND .RC FILE  
  
#include "afxres.rc"  // Standard components  
#include "afxprint.rc"  // printing/print preview resources  
```  
  
 Sonuç Aşağıdaki diyagramda gösterilmiştir:  
  
```  
RESOURCE.H     AFXRES.H      
 \       /                
 \     /  
    MYAPP.RC 
 |  
 |                
    RES\MYAPP.RC2 
    SECOND.RC 
    AFXRES.RC 
    AFXPRINT.RC 
```  
  
 Derleme zamanı yönergeleri kullanarak, birden çok Visual C++ düzenlenebilir ve düzenlenemeyen kaynaklarınızı düzenleyebilirsiniz. RC dosyaları, burada "ana" UYGULAMAM. RC hiçbir şey yapmaz ancak # diğer include. RC dosyaları. Visual C++ projesi kullanıyorsanız. MAK dosya, ardından "ana" içermesi gerekir. RC dosya projede bu nedenle, tüm #include'd kaynaklar ile uygulamanızı derlenir.  
  
 **Yapılamayan Visual C++ dosyalarının zorlama**  
  
 AppWizard oluşturulan RES\MYAPP. RC2 dosyasıdır bunu kaynakları içeren bir dosyayı örneği *değil* yanlışlıkla Visual C++ okur ve bunlara Yazar istediğiniz bilgileri biçimlendirme kaybı ile geri. Buna karşı korunmak için aşağıdaki satırları RES\MYAPP başına içinde yerleştirin. RC2 dosyası:  
  
```  
#ifdef APSTUDIO_INVOKED  
 #error this file is not editable by Visual C++  
#endif //APSTUDIO_INVOKED  
```  
  
 Visual C++ zaman derler. RC dosya tanımladığı `APSTUDIO_INVOKED` yanı `RC_INVOKED`. AppWizard oluşturulan dosya yapısı bozuk ve Visual C++ #error satırla okur, önemli bir hata raporları ve okunması durdurulacak. RC dosyası.  
  
 **Birden çok Visual tarafından C++ düzenlenebilir paylaşılan semboller yönetme. RC dosyaları**  
  
 Kaynaklarınızın birden çok içine yukarı böldüğünüzde iki sorunları ortaya çıkar. Visual c++'ta ayrı ayrı düzenlemek istediğiniz RC dosyaları:  
  
-   Birden çok aynı sembolleri paylaşın isteyebilirsiniz. RC dosyaları.  
  
-   Visual C++ ayrı kaynakları (simgeler) aynı kimliği sayısal değerleri atamaktan kaçının yardımcı olmak gerekir.  
  
 Aşağıdaki diyagramda, bir kuruluşu göstermektedir. RC ve. İlk sorun ilgilenir H dosyalar:  
  
```  
    MYAPP.RC */         \ */           \  
MYSTRS.H   / MYSHARED.H  \  MYMENUS.H  
 \    /    /      \   \    \  
 \  /    /        \   \    \  
    MYSTRS.RC MYMENUS.RC  
```  
  
 Bu örnekte, dize kaynakları bir kaynak dosyasında MYSTRS tutulur. RC ve menüleri başka bir programda, MYMENUS tutulur. RC. Bazı semboller, ayarlamayı komutları, iki dosya arasında paylaşılan gerekebilir. Örneğin, bir ID_TOOLS_SPELL Araçlar menüsünde yazım öğesi için menü komut kimliği olabilir; ve uygulamanın ana penceresi durum çubuğunda framework tarafından görüntülenen komut istemi dize kimliği olabilir.  
  
 ID_TOOLS_SPELL simgenin paylaşılan üstbilgi dosyası, MYSHARED tutulur. H. Bu paylaşılan üstbilgi dosyası bakımını el ile bir metin düzenleyicisiyle; Visual C++ doğrudan düzenlemek değil. İki kaynak MYSTRS dosyaları. RC ve MYMENUS. Belirttiğiniz RC, # MYSHARED include. UYGULAMAM için salt okunur yönergeleri H. RC, kullanarak **kaynağını içeren** , daha önce açıklandığı gibi komutu.  
  
 Paylaşır kullanım çalışmadan önce bir simge tahmin için en uygun herhangi bir kaynağa tanımlamak için. Simgenin paylaşılan üstbilgi dosyasına ekleyin ve henüz yapmadıysanız # paylaşılan üstbilgi dosyası salt okunur yönergeleri için include'd. RC dosya, bunu simgenin kullanmadan önce yapın. Simgenin bu şekilde paylaşımı öngörememiştir sonra el ile gerekir (bir metin düzenleyicisi kullanarak) taşımak # simgesini, söyleyin, MYMENUS için define. H MYSHARED '. İçinde MYSTRS kullanmadan önce H. RC.  
  
 Birden çok sembolleri yönettiğinizde. RC dosyaları, ayrı kaynakları (simgeler) aynı kimliği sayısal değerleri atamaktan kaçının Visual C++ yardımcı olmanız gerekir. İçin verilir. RC dosya, Visual C++ kimlikleri dört kimliği alanlarındaki artımlı olarak atar. Düzenleme oturumları arasında Visual C++ atanan her bir etki alanında sembol üstbilgi dosyası için son kimliği izler. RC dosyası. İşte ne APS_NEXT (yeni) boş için değerlerdir. RC dosyası:  
  
```  
#define _APS_NEXT_RESOURCE_VALUE  101  
#define _APS_NEXT_COMMAND_VALUE   40001  
#define _APS_NEXT_CONTROL_VALUE   1000  
#define _APS_NEXT_SYMED_VALUE     101  
```  
  
 `_APS_NEXT_RESOURCE_VALUE` iletişim kutusu kaynağı, menü kaynağı ve benzeri için kullanılacak sonraki simge değerdir. Kaynak sembol değerleri için geçerli aralık 1 için 0x6FFF ' dir.  
  
 `_APS_NEXT_COMMAND_VALUE` bir komut kimliği için kullanılacak sonraki simge değerdir. Geçerli komut sembol değerleri için 0x8000 0xDFFF arasındadır.  
  
 `_APS_NEXT_CONTROL_VALUE` bir iletişim kutusu denetim için kullanılacak sonraki simge değerdir. Geçerli iletişim denetim sembol değerleri için 8 0xDFFF arasındadır.  
  
 `_APS_NEXT_SYMED_VALUE` Sembol değeri el ile atamanız verilecek sonraki simge değer simge tarayıcıda yeni komutu kullanıyor.  
  
 Visual C++ başlatır biraz daha yüksek değerleri düşük hukuk ne zaman değeri ile yeni bir oluşturuluyor. RC dosyası. AppWizard de bu değerleri MFC uygulamaları için daha uygun bir şey başlatacak. ID değeri aralıkları hakkında daha fazla bilgi için bkz: [Teknik Not 20](../mfc/tn020-id-naming-and-numbering-conventions.md).  
  
 Her zaman bile aynı projede yeni bir kaynak dosyası oluşturun, Visual C++ aynı tanımlar artık `_APS_NEXT_` değerleri. Bu, söyleyin, eklerseniz, birden çok farklı iki iletişim kutuları, anlamına gelir. RC dosyaları, yüksek oranda büyük olasılıkla, aynı #define değeri farklı iletişim kutuları için atanacaktır. Örneğin, ilk IDD_MY_DLG1. RC dosya atanabilir aynı numarası, 101, ikinci bir IDD_MY_DLG2 olarak. RC dosyası.  
  
 Bu durumu önlemek için her dört etki alanlarının kimlikleri ilgili için ayrı bir sayısal aralık ayırmak. RC dosyaları. El ile güncelleştirerek bunu `_APS_NEXT` her birinde değerleri. RC dosyaları **önce** kaynakları eklemeye başlayın. Örneğin, ilk. RC dosyasını kullanan varsayılan `_APS_NEXT` değerleri aşağıdaki atamak isteyebilirsiniz sonra `_APS_NEXT` ikinci değerleri. RC dosyası:  
  
```  
#define _APS_NEXT_RESOURCE_VALUE  2000  
#define _APS_NEXT_COMMAND_VALUE   42000  
#define _APS_NEXT_CONTROL_VALUE   2000  
#define _APS_NEXT_SYMED_VALUE     2000  
```  
  
 Elbette, Visual C++ ilk çok fazla sayıda kimlikleri atayacaktır hala mümkündür. Bu ikinci için ayrılmış çakışmasına sayısal değerleri Başlat RC dosyası. RC dosyası. Böylece bu gerçekleşmez yeterli büyüklükte aralıkları yedek.  
  
 **Arasındaki bağımlılıkları yönetme. RC. CPP, ve. H dosyaları**  
  
 Visual C++ zaman kaydeder bir. RC dosyası, ayrıca karşılık gelen kaynak simgesi değişiklikleri kaydeder. H dosyası. Herhangi biri. Kaynaklara başvuran CPP dosyaları. RC dosya # kaynak include. Genellikle içinden H dosya projenizin ana üstbilgi dosyası. Bu işlem için istenmeyen bir yan etkisi nedeniyle üstbilgi bağımlılıkları için kaynak dosyaları tarayan geliştirme ortamı iç proje yönetimi sağlar. Visual C++'da yeni bir sembol eklediğiniz her zaman tüm. CPP dosya # kaynak include. H derlenmesi gerekir.  
  
 Visual C++, Kaynak bağımlılığı bozar. Kaynak ilk satır aşağıdaki açıklama ekleyerek H. H dosyası:  
  
```  
//{{NO_DEPENDENCIES}}  
```  
  
 Geliştirme ortamı kaynağa değişiklikleri iptal ederek bu açıklama yorumlar. Bu nedenle bağımlı H. CPP dosyaları derlenmesi gerekmez.  
  
 Visual C++ her zaman ekler //{{NO_DEPENDENCIES}} açıklama satırı için bir. Dosya kaydettiğinde RC dosyası. Bazı durumlarda, kaynakta yapı bağımlılığın atlamak. H bağlantı zaman algılanamadı çalışma zamanı hataları neden olabilir. Örneğin, bir kaynak için bir simge atanan sayısal değerini değiştirmek için simge tarayıcısı kullanıyorsanız, kaynak değil doğru bulundu ve olması uygulama çalışma zamanı IF sırasında yüklenir. Kaynağa başvuran CPP dosya yeniden derlenmesi değil. Böyle durumlarda, açıkça herhangi yeniden derleyin. Bildiğiniz CPP dosyaları kaynak sembol yapılan değişiklikler etkilenir. Seçin veya H **yeniden tüm**. Sık kaynakların belirli bir grup için simge değerlerini değiştirmek için gereksiniminiz varsa, büyük olasılıkla bunu daha kolay ve güvenli bu simgeleri ayrı bir salt okunur üstbilgi dosyasına dışarı ayırmak yukarıdaki bölümde açıklandığı gibi bulacaksınız [dahil olmak üzere Ek üstbilgi dosyaları](#_mfcnotes_tn035_including).  
  
## <a name="_mfcnotes_tn035_set_includes"></a> Visual C++ yönetir nasıl bilgi ** içerir  
  
 Yukarıda açıklandığı gibi dosya menüsü Ayarla içerir komutu üç türde bilgileri belirtmenize olanak sağlar:  
  
-   Sembol üstbilgi dosyası  
  
-   Salt okunur sembol yönergeleri  
  
-   Derleme zamanı yönergeleri  
  
 Visual C++ bu bilgileri nasıl korur açıklanmıştır bir. RC dosyası. Visual C++ kullanmak üzere bu bilgileri gerekmez, ancak daha güvenle kümesi içeren özellik kullanabilmeleri anlama geliştirmek.  
  
 Kümesi içeren bilgileri yukarıdaki üç türlerinin her biri depolanır. İki tür RC dosyasında: (1) olarak #include veya diğer yönergeleri yorumlanabilir kaynak derleyicisi tarafından ve (2) özel TEXTINCLUDE tarafından kaynağı olarak yorumlanabilir yalnızca Visual C++.  
  
 Visual C++'ın taşımalarına presentable bir biçimde güvenli bir şekilde ayarlamak dahil bilgileri depolamak için TEXTINCLUDE kaynak amacı **kümesi içeren** iletişim kutusu. TEXTINCLUDE olan bir *kaynak türü* Visual C++ tarafından tanımlanan. Visual C++ kimlik numaraları 1, 2 ve 3 kaynağa sahip üç belirli TEXTINCLUDE kaynakları tanır:  
  
|TEXTINCLUDE kaynak kimliği|Tür bilgileri kümesi içerir|  
|-----------------------------|--------------------------------------|  
|1.|Sembol üstbilgi dosyası|  
|2|Salt okunur sembol yönergeleri|  
|3|Derleme zamanı yönergeleri|  
  
 Her üç tür kümesi içeren bilgi UYGULAMAM varsayılan olarak gösterilmiştir. RC ve kaynak. Aşağıda açıklandığı gibi AppWizard tarafından oluşturulan H dosyaları. Ek \0 ve "" belirteç başlangıç ve bitiş blokları arasında RC sözdizimi tarafından sıfır sonlandırılmış dizeler ve çift tırnak karakteri sırasıyla belirtmek için gereklidir.  
  
## <a name="symbol-header-file"></a>Sembol üstbilgi dosyası  
 Kaynak derleyicisi tarafından yorumlanan sembol üstbilgi dosyası bilgileri yalnızca formdur bir # deyimi include:  
  
```  
#include "resource.h"  
```  
  
 Karşılık gelen TEXTINCLUDE kaynaktır:  
  
```  
1 TEXTINCLUDE DISCARDABLE  
BEGIN  
 "resource.h\0"  
END  
```  
  
## <a name="read-only-symbol-directives"></a>Salt okunur sembol yönergeleri  
 Salt okunur sembol yönergeleri UYGULAMAM üstünde dahil edilir. Kaynak derleyicisi tarafından yorumlanabilir aşağıdaki biçimde RC:  
  
```  
#include "afxres.h"  
```  
  
 Karşılık gelen TEXTINCLUDE kaynaktır:  
  
```  
2 TEXTINCLUDE DISCARDABLE  
BEGIN  
   "#include ""afxres.h""\r\n"  
   "\0"  
END  
```  
  
## <a name="compile-time-directives"></a>Derleme zamanı yönergeleri  
 Derleme zamanı yönergeleri UYGULAMAM sonunda dahil edilir. Kaynak derleyicisi tarafından yorumlanabilir aşağıdaki biçimde RC:  
  
```  
#ifndef APSTUDIO_INVOKED  
///////////////////////  
//  
// From TEXTINCLUDE 3  
//  
#include "res\myapp.rc2"  // non-Visual C++ edited resources  
  
#include "afxres.rc"  // Standard components  
#include "afxprint.rc"  // printing/print preview resources  
#endif  // not APSTUDIO_INVOKED  
```  
  
 #İfndef APSTUDIO_INVOKED yönergesi derleme zamanı yönergeleri geçmek için Visual C++ bildirir.  
  
 Karşılık gelen TEXTINCLUDE kaynaktır:  
  
```  
3 TEXTINCLUDE DISCARDABLE  
BEGIN  
"#include ""res\myapp.rc2""  // non-Visual C++ edited resources\r\n"  
"\r\n"  
"#include ""afxres.rc""  // Standard components\r\n"  
"#include ""afxprint.rc""  // printing/print preview resources\r\n"  
"\0"  
END  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

