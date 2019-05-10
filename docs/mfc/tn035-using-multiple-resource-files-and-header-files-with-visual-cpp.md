---
title: 'TN035: Visual C++ birden çok kaynak dosya ve üstbilgi dosyası kullanma'
ms.date: 11/04/2016
f1_keywords:
- vc.resources
helpviewer_keywords:
- resource files, multiple
- TN035
ms.assetid: 1f08ce5e-a912-44cc-ac56-7dd93ad73fb6
ms.openlocfilehash: 8ce38c2f3f4effa993dfa32221d82bece65096dd
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448542"
---
# <a name="tn035-using-multiple-resource-files-and-header-files-with-visual-c"></a>TN035: Visual C++ birden çok kaynak dosya ve üstbilgi dosyası kullanma

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, Visual C++ kaynak düzenleyicisinin birden çok kaynak dosyasını nasıl desteklediğini açıklar ve üst bilgi dosyaları tek bir paylaşılan proje veya paylaşılan arasında birden çok proje ve nasıl bu destekten yararlanabilirsiniz. Bu Not, şu soruları yanıtlamaktadır:

- Ne zaman birden çok kaynak dosyaları ve/veya üst bilgi dosyaları projeye ve bunu nasıl bölmek isteyebilirsiniz

- Ortak bir üst bilgi nasıl paylaştığınız. İki y dosyası. RC dosyaları

- Nasıl proje kaynaklarını birden çok bölün. RC dosyaları

- Nasıl siz (ve araçlar) arasındaki yapı bağımlılıklarını yönetebilirsiniz. RC. CPP ve. H dosyaları

Projenize ek bir kaynak dosyası eklerseniz, ClassWizard eklenen dosyadaki kaynakları tanımaz bilmeniz gerekir.

Bu Not, yukarıdaki soruları şu şekilde yanıtlamak üzere yapılandırılmıştır:

- **Nasıl Visual C++ yöneten kaynak dosyaları ve üstbilgi dosyaları'na genel bakış** kaynak dahil edilenleri Ayarla komutunun Visual C++ kaynak dosyaları ve üstbilgi dosyaları aynı projede birden çok'nı kullanmanıza izin nasıl genel bir bakış sağlar.

- **AppWizard ile oluşturulan analizi. RC ve. H dosyaları** AppWizard ile oluşturulan bir uygulama tarafından kullanılan birden fazla kaynak ve üstbilgi dosyasına bakar. Bu dosyalar, ek kaynak dosyaları ve üstbilgi dosyaları projenize eklemek isteyebileceğiniz için iyi bir model görevi görür.

- **Ek üstbilgi dosyalarını dahil olmak üzere** , birden çok üstbilgi dosyalarını eklemek isteyebilirsiniz ve bunun nasıl yapılacağını gösteren Ayrıntılar sağlar açıklar.

- **Bir üstbilgi dosyasını iki arasında paylaştırma. RC dosyaları** bir üstbilgi dosyası birden çok arasında nasıl paylaştırabileceğinizi göstermektedir. RC dosyaları farklı projelerde veya belki aynı projedeki.

- **Aynı projede birden çok kaynak dosyaları kullanarak** , projenizi birden çok ayırmak isteyebileceğiniz açıklar. RC dosyaları ve bunun nasıl yapılacağını gösteren Ayrıntılar sağlar.

- **Düzenlenemez Visual C++ dosyalarının zorlama** nasıl Visual C++ almayan düzenleyin ve istemeden özel bir kaynak yeniden biçimlendirme emin olursunuz açıklar.

- **Birden çok görsel tarafından C++ ile düzenlenmiş paylaşılan semboller yönetme. RC dosyaları** aynı sembolü birden çok paylaşmayı açıklar. RC dosyaları ve tekrarlayan ID sayısal değerlerini atamanın nasıl önleneceğini.

- **Arasındaki bağımlılıkları yönetme. RC. CPP ve. H dosyaları** gereksiz yeniden derlemeden Visual C++ nasıl önler açıklar. Kaynak sembolü dosyalarına bağımlı olan dosyaların CPP.

- **Visual C++ yönetir kümesi içeren bilgilerini** nasıl Visual C++ (iç içe) birden çok izler hakkında teknik ayrıntılar sağlar. RC dosyaları ve birden çok üst bilgi dosyaları # tarafından #include ile eklenen bir. RC dosyası.

**Genel Visual C++ kaynak dosyaları ve üstbilgi dosyaları yönetir**

Visual C++ tek bir yönetir. RC kaynak dosyası ve karşılık gelen. Sıkı eşleşmiş bir çift dosya olarak H üst bilgi dosyası. Ne zaman düzenleme ve kaynakları kaydetme bir. RC dosyası, dolaylı olarak düzenleyip sembolleri ilgili kaydedin. H dosyası. Açın ve birden çok Düzenle rağmen. RC dosyaları (Visual C++'ın MDI kullanıcı arabirimini kullanarak), verilen herhangi bir zaman. RC dosyası dolaylı olarak karşılık gelen tam olarak bir üst bilgi dosyasını düzenleyin.

**Sembol başlık dosyası**

Varsayılan olarak, Visual C++, her zaman ilgili başlık dosyası kaynak adları. Kaynak dosyası (örneğin, MYAPP adından bağımsız olarak H. RC). Kullanarak **kaynak içerikleri** komutunu **görünümü** menüsünde Visual C++'ta, sembol üst bilgi dosyasını güncelleştirerek bu başlık dosyasının adını değiştirebilirsiniz **edilenleriAyarla**iletişim kutusu.

**Salt okunur sembol yönergeleri**

Visual C++ yalnızca bir üst bilgi dosyası için verilen herhangi düzenlemesine rağmen. RC dosyası, Visual C++ ek salt okunur üstbilgi dosyalarındaki sembollere başvuruları destekler. Kullanarak **kaynak içerikleri** komutunu **görünümü** menü Visual C++'da, herhangi bir sayıda ek salt okunur başlık dosyaları salt okunur sembol yönergeleri belirtebilirsiniz. İçinde yeni bir kaynak eklediğinizde, "salt okunur" kısıtlaması anlamına gelir. RC dosyası salt okunur başlık dosyasında tanımlı bir sembolü kullanabileceğiniz; ancak kaynağı silerseniz, sembolün salt okunur başlık dosyasında tanımlı kalıyor. Salt okunur bir sembole atanmış sayısal bir değeri değiştiremezsiniz.

**Derleme zamanı yönergeleri**

Visual C++ kaynak dosyaları, iç içe geçmiş bir yerde de destekler. RC dosyası # #include ile başka. Düzenlerken bir verilen. Visual C++, hesaptaki kaynakları kullanarak RC dosyası # #include ile eklenen dosyaları görünür değildir. Ancak derleme yaptığınızda. RC dosyası # #include ile eklenen dosyalar da derlenir. Kullanarak **kaynak içerikleri** komutunu **görünümü** menüsünde Visual C++'da, herhangi bir sayıda belirtebilirsiniz # #include ile eklenen. RC dosyaları derleme zamanı yönergeleri olarak.

Ne olacağını unutmayın Visual C++'ta salt okunur bir. RC dosyası # başka bir kullanıcının include. RC dosyası *değil* bir derleme zamanı yönergesi olarak. Bu durumda, Visual C++'a getirdiğinizde ortaya çıkabilir bir. Daha önce el ile bir metin düzenleyiciyle bakımını RC dosyası. Visual C++ ne zaman okur # #include ile eklenen. RC dosyası, birleştirir # kaynakları üst öğeye #include ile eklenen. RC dosyası. Üst kaydettiğinizde. RC dosyası # deyimi, aslında include, ile değiştirilecek # kaynakları #include ile eklenen. Bu birleşimin olmasını istemiyorsanız kaldırmalısınız # üst deyiminden include. RC dosyası *önceki* Visual C++'ta; okuma için Visual C++'ı kullanarak Ekle tekrar aynı # deyimi bir derleme zamanı yönergesi olarak include.

Visual C++ kaydeder bir. RC dosyası üç tür yukarıdaki dahil edilenleri Ayarla bilgilerini (sembol başlık dosyası, salt okunur sembol yönergeleri ve derleme zamanı yönergeleri) #include *ve* TEXTINCLUDE kaynakları. Normalde uğraşmanız gerekmeyen bir uygulama ayrıntısı olan TEXTINCLUDE kaynakların açıklandığı [nasıl Visual C++ yönetir edilenleri ayarlama bilgilerini](#_mfcnotes_tn035_set_includes).

**AppWizard ile oluşturulan analizi. RC ve. H dosyaları**

AppWizard tarafından üretilen uygulama kodunun incelenmesi, Visual C++ birden çok kaynak dosyaları ve üstbilgi dosyaları nasıl yönettiği konusunda fikir sağlar. Aşağıda incelenen kod alıntıları, varsayılan seçenekleri kullanarak AppWizard tarafından üretilen bir UYGULAMAM uygulama arasındadır.

AppWizard ile oluşturulan bir uygulama birden çok kaynak dosyasını ve birden çok üst bilgi dosyaları, aşağıdaki diyagramda özetlendiği gibi kullanır:

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

Bu çok dosyalı ilişkileri Visual C++ dosya/dahil edilenleri Ayarla komutunu kullanarak görüntüleyebilirsiniz.

UYGULAMAM. RC, Visual C++'ı kullanarak düzenlediğiniz uygulama kaynak dosyası.

KAYNAK. H uygulamaya özel bir üstbilgi dosyasıdır. Her zaman kaynak adı verilir. Visual C++'ın varsayılan tutarlı AppWizard tarafından H üst bilgi dosyası adlandırmasıyla. # Bu başlık dosyasının (UYGULAMAM. kaynak dosyasındaki ilk deyim için include RC):

```
//Microsoft Visual C++ generated resource script
//
#include "resource.h"
```

RES\MYAPP. Visual C++ tarafından düzenlenmeyecek ancak derlenmiş en son içinde dahil edilecek RC2 içeren kaynaklar. EXE dosyası. Visual C++ sürüm kaynağı (Bu sürümde yeni bir özellik) dahil olmak üzere tüm standart kaynakları düzenleyebilir AppWizard varsayılan olarak böyle kaynaklar oluşturur. Kendi özel biçimlendirilmiş kaynağınızı bu dosyaya eklemek istediğiniz durumlarda AppWizard tarafından boş bir dosya oluşturulur.

Özel biçimlendirilmiş kaynaklar kullanıyorsanız, bunları RES\MYAPP için ekleyebilirsiniz. RC2 ve Visual C++ metin düzenleyicisi kullanarak bunları düzenleyebilirsiniz.

AFXRES. RC ve AFXPRINT. RC tarafından framework'ün belirli özellikleri için gereken standart kaynakları içerir. RES\MYAPP gibi. RC2'de, bu iki framework tarafından sağlanan kaynak dosyalar olan # MYAPP sonunda #include ile eklenen. RC ve bunlar dahil edilenleri Ayarla iletişim kutusunda derleme zamanı yönergeleri'nde belirtilir. Bu nedenle, doğrudan görüntülerken veya MYAPP düzenlerken bu çerçeve kaynaklarını. Visual C++ ' ta RC ancak uygulamanın ikili olarak derlenmiş. RES dosyası ve son. EXE dosyası. Standart framework kaynakları ve bunları değiştirme yordamları hakkında daha fazla bilgi için bkz. [Teknik Not 23](../mfc/tn023-standard-mfc-resources.md).

AFXRES. H standart sembolleri gibi tanımlar `ID_FILE_NEW`framework tarafından kullanılan ve özellikle AFXRES kullanılır. RC. AFXRES. H ayrıca #include WINRES. H WINDOWS kümesini içerir. Visual C++ tarafından oluşturulan gerekli H. RC dosyaları yanı sıra AFXRES. RC. AFXRES içinde tanımlanan simgeleri. H, uygulama kaynak dosyası (UYGULAMAM. düzenlerken kullanılabilir RC). Örneğin, `ID_FILE_NEW` MYAPP dosya yeni menü öğesi için kullanılır. RC'ın menü kaynağı. Değiştiremez veya çerçeve tarafından tanımlanmış bu sembolleri Sil.

## <a name="_mfcnotes_tn035_including"></a> Ek üstbilgi dosyaları dahil

AppWizard ile oluşturulan uygulama yalnızca iki başlık dosyası içerir: KAYNAK. H ve AFXRES. H Yalnızca kaynak. Uygulamaya özgü S. Aşağıdaki durumlarda ek salt okunur başlık dosyaları dahil gerekebilir:

Üst bilgi dosyası bir dış kaynak tarafından sağlanıyor veya başlık dosyasını birden çok proje veya aynı projenin birden fazla bölümü arasında paylaşmak istiyorsunuz.

Üstbilgi dosyası, biçimlendirme ve açıklamaları değiştirin veya dosyayı kaydederken filtrelemek için Visual C++ istemediğiniz sahiptir. Örneğin, belki de korumak istediğiniz #define gibi sembolik aritmetiği kullanın:

```
#define RED 0
#define BLUE 1
#define GREEN 2
#define ID_COLOR_BUTTON 1001
#define ID_RED_BUTTON (ID_COLOR_BUTTON + RED)
#define ID_BLUE_BUTTON (ID_COLOR_BUTTON + BLUE)
#define ID_GREEN_BUTTON (ID_COLOR_BUTTON + GREEN)
```

Kullanarak ek salt okunur başlık dosyaları dahil edebilirsiniz **kaynak içerikleri** belirtmek için komut # deyimi olarak ikinci bir salt okunur sembol yönergesi olarak include:

```
#include "afxres.h"
#include "second.h"
```

Yeni dosya ilişkisi şeması artık şöyledir:

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

**Bir üstbilgi dosyasını iki arasında paylaştırma. RC dosyaları**

Bir üstbilgi dosyasını iki arasında paylaşmak isteyebilirsiniz. Farklı projelerde veya aynı projenin büyük olasılıkla olan RC dosyaları. Bunu yapmak için yalnızca yukarıda hem de anlatılan salt okunur yönergeler tekniğini uygulamak. RC dosyaları. Bu durumda burada iki. RC dosyaları olan farklı uygulamalar için (farklı projeler), sonuç Aşağıdaki diyagramda gösterilmiştir:

```
    RESOURCE.H AFXRES.H   RESOURCE.H
(for MYAPP1) SECOND.H   (for MYAPP2)
\       /     \       /
\     /       \     /
    MYAPP1.RC MYAPP2.RC */    \        /     \ */      \      /       \
RES\MYAPP1.RC2  AFXRES.RC     RES\MYAPP2.RC2
    AFXPRINT.RC
```

İkinci başlık dosyasının iki tarafından paylaşıldığı durum. RC dosyaları aynı uygulamada (Proje) aşağıda ele alınmıştır.

**Aynı projede birden çok kaynak dosyalarını kullanma**

Visual C++ ve kaynak derleyicisi birden çok destekler. RC dosyaları ile aynı projede #include biri. RC dosyası içindeki başka. Çoklu yuvalanmaya izin verilir. Projenizin kaynaklarını birden çok ayırmanın çeşitli nedenleri vardır. RC dosyaları:

- Kaynaklar içinde birden fazla bölme kaynakları birden çok proje ekibi üyesi arasında çok sayıda yönetmek kolaydır. RC dosyaları. Kaynak denetimi Yönetim Paketi dosyalar kullanıma alınıyor ve değişiklikleri denetlemek için kullanabileceğiniz kaynakları birden fazla bölme kullanıyorsanız. RC dosyaları kaynaklarına yapılan değişiklikleri yönetme üzerinde daha hassas denetim sağlayacak.

- #İfdef, #endif gibi önişlemci yönergelerini kullanmak istiyorsanız ve #define, kaynaklarınızın bölümleri için bunları kaynak derleyicisi tarafından derlenecek salt okunur kaynakları yalıtmanıza gerekir.

- Bileşeni. RC dosyaları yüklemek ve Visual C++'ta daha hızlı bir bileşik kaydedin. RC dosyası.

- İnsan tarafından okunabilir formda bir metin düzenleyicisi ile bir kaynak sürdürmek istiyorsanız, bir ad seçmelisiniz bir. RC dosyası bir Visual C++'dan ayrı düzenler.

- Daha sonra başka bir özelleştirilmiş veri Düzenleyicisi tarafından yorumlanabilen bir ikili ya da metin biçiminde kullanıcı tanımlı bir kaynağı tutmanız gerekiyorsa, bunu ayrı bir tutmalısınız. RC dosyası için Visual C++ biçimi onaltılık veri olarak değiştirmez. . MFC Gelişmiş kavramlar örneği WAV (ses) dosyası kaynakları [SPEAKN](../overview/visual-cpp-samples.md) güzel bir örnektir.

Yapabilecekleriniz # ikinci include. RC sürümünde dahil edilenleri Ayarla iletişim kutusunda derleme zamanı yönergeleri:

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

Derleme zamanı yönergeleri'ni kullanarak Visual C++'de düzenlenebilir ve düzenlenemez kaynaklarınızı birden çok düzenleyebilirsiniz. RC dosyaları burada "ana" MYAPP. RC hiçbir şey yapmaz ancak # diğer include. RC dosyaları. Visual Studio kullanıyorsanız C++ proje. MAK dosyasını ve ardından "ana" içermelidir. RC dosyası projede bu nedenle, tüm # #include ile eklenen kaynakları uygulamanızla derlenir.

**Düzenlenemez Visual C++ dosyalarının zorlama**

AppWizard ile oluşturulan RES\MYAPP. RC2 dosyası kaynakları içeren bir dosyayı örneğidir *değil* yanlışlıkla Visual C++'ta okuyun ve ardından yazmak istediğiniz biçimlendirme bilgileri kaybedilerek geriye. Buna karşı korunmak için aşağıdaki satırları RES\MYAPP başında yerleştirin. RC2 dosyası:

```
#ifdef APSTUDIO_INVOKED
#error this file is not editable by Visual C++
#endif //APSTUDIO_INVOKED
```

Visual C++ ne zaman derler. RC dosyası tanımladığı `APSTUDIO_INVOKED` yanı `RC_INVOKED`. AppWizard ile oluşturulan dosya yapısı bozuksa ve Visual C++ yukarıdaki #error satırını okur, önemli bir hata bildirir ve okunması iptal. RC dosyası.

**Birden çok görsel tarafından C++ ile düzenlenmiş paylaşılan semboller yönetme. RC dosyaları**

Kaynaklarınızı birden çok ayırdığınızda, iki sorun ortaya çıkar. Visual c++'ta ayrı ayrı düzenlemek istediğiniz RC dosyaları:

- Aynı sembolü birden çok arasında paylaşmak isteyebilirsiniz. RC dosyaları.

- Aynı sayısal kimlik değerlerini farklı kaynaklara (sembollere) atamaktan kaçının Visual C++ Yardım gerekiyor.

Aşağıdaki diyagram bir kuruluşa gösterir. RC ve. İlk sorunla ilgili dosyaları H:

```
    MYAPP.RC */         \ */           \
MYSTRS.H   / MYSHARED.H  \  MYMENUS.H
\    /    /      \   \    \
\  /    /        \   \    \
    MYSTRS.RC MYMENUS.RC
```

Bu örnekte dize kaynakları bir kaynak dosyasında MYSTRS tutulur. RC ve menüler başka birinde MYMENUS tutulur. RC. For komutları gibi bazı simgelerin iki dosya arasında paylaşılması gerekebilir. Örneğin bir ıd_tools_spell, bir Araçlar menüsünde yazım öğesi için menü komut kimliği olabilir. ve uygulamanın ana pencere durum çubuğunda framework tarafından gösterilen komut isteminin dize kimliği olabilir.

Id_tools_spell sembolü paylaşılan üstbilgi dosyasında MYSHARED tutulur. H Bu paylaşılan başlık dosyasının el ile bir metin düzenleyiciyle sürdürmek; Visual C++ doğrudan düzenlemez. İki kaynak MYSTRS dosyaları. RC ve MYMENUS. Belirttiğiniz RC, # MYSHARED include. UYGULAMAM için salt okunur yönergelerinde H. RC kullanılarak **kaynak içerikleri** , daha önce açıklandığı gibi komutu.

Paylaşmak kullanmadan önce paylaşacağınız bir sembolü tahmin etmektir en kullanışlı olanı, herhangi bir kaynağı tanımlamak için. Sembolü paylaşılan üstbilgi dosyasına ekleyin ve zaten #dahil etmediyseniz # için salt okunur yönergelerinde direktiflerindeki paylaşılan üstbilgi dosyasını. RC dosyası, sembolü kullanmadan önce bunu yapın. Sembolün bu şekilde paylaşımı tahmin değil sonra el ile gerekecektir (bir metin düzenleyicisi kullanarak) taşıma #define sembolünden örneğin MYMENUS için. H MYSHARED '. İçinde MYSTRS kullanmadan önce H. RC.

Birden çok sembolleri yönetirken. RC dosyaları, aynı sayısal kimlik değerlerini farklı kaynaklara (sembollere) atamaktan kaçının Visual C++ Yardım gerekir. İçin verilir. RC dosyası, Visual C++ kimlikleri her dört ID etki alanının içinde kademeli olarak atar. Düzenleme oturumları arasında Visual C++ için Sembol başlık dosyası etki alanlarının her atadığı son ID'nin izler. RC dosyası. (Yeni) bir boş APS_NEXT değerleri nelerdir aşağıda verilmiştir. RC dosyası:

```
#define _APS_NEXT_RESOURCE_VALUE  101
#define _APS_NEXT_COMMAND_VALUE   40001
#define _APS_NEXT_CONTROL_VALUE   1000
#define _APS_NEXT_SYMED_VALUE     101
```

`_APS_NEXT_RESOURCE_VALUE` bir iletişim kutusu kaynağı, menü kaynağı vb. için kullanılacak sonraki sembol değerdir. Kaynak sembol değerlerinin geçerli aralığı 1 ile 0x6FFF arasıdır.

`_APS_NEXT_COMMAND_VALUE` bir komut tanımlaması için kullanılacak sonraki sembol değerdir. Komut sembol değerlerinin geçerli aralığı 0x8000 ile 0xDFFF arasındadır.

`_APS_NEXT_CONTROL_VALUE` bir iletişim denetimi için kullanılacak sonraki sembol değerdir. İletişim kutusu denetiminin sembol değerlerinin geçerli aralığı 8 ile 0xDFFF arasıdır.

`_APS_NEXT_SYMED_VALUE` Sembol değeri el ile atama verilecek sonraki sembol değeri yeni bir komut sembol tarayıcısındaki kullanıyor.

En düşük yasal değerden biraz yüksek değerler ile Visual C++ başlayan yeni bir oluşturuluyor. RC dosyası. AppWizard Ayrıca bu değerleri MFC uygulamaları için daha uygun bir şey başlatılır. ID değer aralıkları hakkında daha fazla bilgi için bkz. [Teknik Not 20](../mfc/tn020-id-naming-and-numbering-conventions.md).

Şimdi, yeni bir kaynak dosyası aynı projede bile her oluşturduğunuzda, Visual C++ aynı tanımlar `_APS_NEXT_` değerleri. Bu, örneğin, eklerseniz birden çok farklı iki iletişim kutuları, anlamına gelir. RC dosyaları, büyük olasılıkla, aynı #define farklı iletişim kutularına atanacağı değeri atanır. Örneğin, ilk ıdd_my_dlg1'e. RC dosyası atanmış aynı numara olan 101 ıdd_my_dlg2 bir saniye içinde. RC dosyası.

Bunu önlemek için dört etki alanlarının kimliklerinin ilgili her biri için ayrı bir sayısal aralık ayırmanız gerekir. RC dosyaları. El ile güncelleştirerek bunu `_APS_NEXT` her birinde değerleri. RC dosyaları **önce** , kaynakları eklemeye başlamadan. Örneğin, ilk. RC dosyası kullanan varsayılan `_APS_NEXT` değerleri aşağıdaki atamak isteyebilirsiniz `_APS_NEXT` ikinci değer. RC dosyası:

```
#define _APS_NEXT_RESOURCE_VALUE  2000
#define _APS_NEXT_COMMAND_VALUE   42000
#define _APS_NEXT_CONTROL_VALUE   2000
#define _APS_NEXT_SYMED_VALUE     2000
```

Elbette, Visual C++ ilk çok sayıda kimlikler atar yine de mümkündür. Sayısal değerlerin olanlar için saniyeyi rezerve çakışma başlamak RC dosyası. RC dosyası. Böylece bu gerçekleşmez yeterince büyük aralıklar ayırmalısınız.

**Arasındaki bağımlılıkları yönetme. RC. CPP ve. H dosyaları**

Visual C++ ne zaman kaydeder bir. RC dosyası, ayrıca ilgili kaynak için Sembol değişiklikleri kaydeder. H dosyası. Herhangi biri. Kaynaklara başvuran CPP dosyalarına. RC dosyası gerekir #include kaynak. Genellikle içinden H dosya projenizin ana üstbilgi dosyası. Bu işlem için istenmeyen bir yan etkisi geliştirme ortamının başlık dosyası bağımlılıkları için kaynak dosyaları tarayan dahili proje yönetimi nedeniyle doğurur. Visual C++'da yeni bir sembolü eklediğiniz her zaman tüm. CPP dosyasına #include kaynak. H derlenmesi gerekir.

Visual C++ kaynak bağımlılığı önler. Aşağıdaki açıklamayı kaynak ilk satırı ekleyerek H. H dosyası:

```
//{{NO_DEPENDENCIES}}
```

Geliştirme ortamı bu yorumu, kaynak değişiklikleri yoksayma şeklinde yorumlar. Bu nedenle bağımlı H. CPP dosyalarına derlenmesi gerekli değildir.

Görsel C++ her zaman //{{NO_DEPENDENCIES ekler}} yorum satırını ekler bir. In dosyayı kaydederken RC dosyası. Bazı durumlarda, kaynak derleme bağımlılığını atlamak. H bağlantı zamanında algılanamayan çalışma zamanı hatalarına neden olabilir. Örneğin, bir kaynak için bir sembole atanmış sayısal değerleri değiştirmek için Sembol tarayıcısını kullanırsanız, kaynak doğru bulunamayan ve uygulama çalışma zamanı Eğer sırasında yüklenir. Kaynağa başvuran CPP dosyasına derlenir değil. Böyle durumlarda, açıkça herhangi derlemeniz. Bildiğiniz CPP dosyalarına kaynak içindeki sembol değişikliklerinden etkilenir. H veya select **Rebuild All**. Sık kaynakların belirli bir grup için Sembol değerlerini değiştirmek için gereken varsa, büyük olasılıkla, daha kullanışlı ve güvenli bu sembolleri ayrı salt okunur başlık dosyası, ayırmak yukarıdaki bölümde açıklandığı gibi bulursunuz [dahil Ek üstbilgi dosyaları](#_mfcnotes_tn035_including).

## <a name="_mfcnotes_tn035_set_includes"></a> Visual C++ yönetir nasıl bilgi ** dahil edilenleri Ayarla

Yukarıda açıklandığı gibi dosya menüsü dahil edilenleri Ayarla komutunun üç bilgi türünü belirlemenizi sağlar:

- Sembol başlık dosyası

- Salt okunur sembol yönergeleri

- Derleme zamanı yönergeleri

Aşağıdaki Visual C++'ın bu bilgileri nasıl tuttuğu açıklanmaktadır bir. RC dosyası. Visual C++ kullanmak üzere bu bilgileri gerekmez, ancak dahil edilenleri Ayarla özelliğini daha güvenle kullanabilmeniz Anlayışınızı geliştirmek.

Yukarıdaki üç dahil edilenleri Ayarla bilgisi türlerinin her biri depolanır. RC dosyasında iki biçimde: (1) olarak #include veya diğer yönergeleri yorumlanabilirinde kaynak derleyicisi tarafından ve (2) gibi yorumlanabilen TEXTINCLUDE kaynakları yalnızca Visual C++ tarafından.

Güvenli bir biçimde kolayca Visual C++'ın edileni ayarlama dahil bilgileri depolamak için TEXTINCLUDE kaynağının amacı olan **dahil edilenleri Ayarla** iletişim kutusu. Textınclude bir *kaynak türü* Visual C++ tarafından tanımlanır. Visual C++ kaynak kimlik numarası 1, 2 ve 3 olan üç özgül TEXTINCLUDE kaynağını tanır:

|TEXTINCLUDE kaynak kimliği|Dahil edilecekleri Ayarla bilgilerinin türü|
|-----------------------------|--------------------------------------|
|1.|Sembol başlık dosyası|
|2|Salt okunur sembol yönergeleri|
|3|Derleme zamanı yönergeleri|

Her üç tür dahil edilecekleri Ayarla bilgilerinin MYAPP varsayılan olarak gösterilmiştir. RC ve kaynak. Aşağıda açıklanan şekilde AppWizard tarafından oluşturulan H dosyaları. Fazladan \0 ve "" belirteçleri BEGIN ve END blokları arasındaki sırasıyla sıfır ile sonlandırılmış dize ve çift tırnak karakteri belirtmek için RC sözdizimi gereklidir.

## <a name="symbol-header-file"></a>Sembol başlık dosyası

Kaynak Derleyici tarafından yorumlanan sembol başlık dosyası bilgilerinin biçimi teknolojidir bir # deyimi include:

```
#include "resource.h"
```

Karşılık gelen TEXTINCLUDE kaynağı şudur:

```
1 TEXTINCLUDE DISCARDABLE
BEGIN
"resource.h\0"
END
```

## <a name="read-only-symbol-directives"></a>Salt okunur sembol yönergeleri

Salt okunur sembol yönergeleri MYAPP üstüne dahil edilir. RC sürümünde aşağıdaki form yorumlanabilirinde kaynak derleyicisi tarafından:

```
#include "afxres.h"
```

Karşılık gelen TEXTINCLUDE kaynağı şudur:

```
2 TEXTINCLUDE DISCARDABLE
BEGIN
   "#include ""afxres.h""\r\n"
   "\0"
END
```

## <a name="compile-time-directives"></a>Derleme zamanı yönergeleri

Derleme zamanı yönergeleri MYAPP sonunda dahil edilir. RC sürümünde aşağıdaki form yorumlanabilirinde kaynak derleyicisi tarafından:

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

#İfndef apstudıo_ınvoked yönergesi Visual bildirir C++ derleme zamanı yönergeleri atlanacak.

Karşılık gelen TEXTINCLUDE kaynağı şudur:

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

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
