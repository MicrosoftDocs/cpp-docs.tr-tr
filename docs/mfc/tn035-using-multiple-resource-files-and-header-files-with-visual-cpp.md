---
description: 'Hakkında daha fazla bilgi edinin: TN035: Visual C++ ile birden fazla kaynak dosyası ve üstbilgi dosyası kullanma'
title: "TN035: Visual C++'da Birden Fazla Kaynak Dosya ve Üstbilgi Dosyası Kullanma"
ms.date: 11/04/2016
f1_keywords:
- vc.resources
helpviewer_keywords:
- resource files, multiple
- TN035
ms.assetid: 1f08ce5e-a912-44cc-ac56-7dd93ad73fb6
ms.openlocfilehash: 347c816040d6e20cd9b7ee01f07662066981b8aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215475"
---
# <a name="tn035-using-multiple-resource-files-and-header-files-with-visual-c"></a>TN035: Visual C++'da Birden Fazla Kaynak Dosya ve Üstbilgi Dosyası Kullanma

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta Visual C++ kaynak Düzenleyicisi 'nin tek bir projede paylaşılan veya birden fazla proje arasında paylaşılan ve bu destekten nasıl yararlanabildiğine ilişkin birden çok kaynak dosyasını ve üst bilgi dosyalarını nasıl desteklediği açıklanmaktadır. Bu notta bu sorulara yanıt verir:

- Bir projeyi birden çok kaynak dosyasına ve/veya üstbilgi dosyasına bölmek ve bunu yapmak isteyebileceğiniz durumlarda

- Ortak üstbilgiyi nasıl paylaşabilirsiniz. İki arasında H dosyası. RC dosyaları

- Proje kaynaklarını birden çok olarak nasıl böleirsiniz. RC dosyaları

- Nasıl yapılır (ve araçları) arasında derleme bağımlılıklarını yönetme. RC,. CPP ve. H dosyaları

Projenize ek bir kaynak dosyası eklerseniz, ClassWizard 'ın eklenen dosyadaki kaynakları tanıyamayacağı farkında olmalısınız.

Bu notta Yukarıdaki sorulara yanıt vermek için aşağıdaki şekilde yapılandırılmıştır:

- **Visual C++ kaynak dosyalarını ve üst bilgi dosyalarını nasıl yönettiğini genel bakış** , aynı projede birden fazla kaynak dosyası ve üstbilgi dosyası kullanmanıza imkan sağlar Visual C++ ' de kaynak kümesi içerme komutu hakkında genel bakış sağlar.

- **AppWizard Analizi-oluşturuldu. RC ve. H dosyaları** , AppWizard tarafından oluşturulan bir uygulama tarafından kullanılan birden çok kaynak ve üstbilgi dosyasına bakar. Bu dosyalar, projenize eklemek isteyebileceğiniz ek kaynak dosyaları ve üstbilgi dosyaları için iyi bir model işlevi sunar.

- **Ek üstbilgi dosyaları dahil olmak üzere** , birden çok başlık dosyasını eklemek isteyebileceğiniz yerleri açıklar ve bunun nasıl yapılacağını açıklar.

- **Üst bilgi dosyasını Iki arasında paylaşma. RC dosyaları** , bir üst bilgi dosyasını birden çok arasında nasıl paylaşılacağını gösterir. RC dosyalarını farklı projelerde veya belki de aynı projede.

- **Aynı projede birden fazla kaynak dosyası kullanmak,** projenizi birden çok yere nasıl bölmek istediğinizi açıklar. RC dosyaları ve bunun nasıl yapılacağını açıklar.

- **Düzenlenemeyen Visual C++ dosyalarının zorlanması** , Visual C++ özel bir kaynağı düzenlememe ve istemeyerek yeniden biçimlendirmesiz şekilde nasıl emin olmanızı istediğinizi açıklar.

- **Birden çok Visual C++ tarafından paylaşılan sembolleri yönetme. RC dosyaları** , aynı sembollerin birden çok üzerinde nasıl paylaşılacağını açıklar. RC dosyaları ve yinelenen KIMLIK sayısal değerlerini atamanın nasıl önleneceğini öğrenin.

- **Arasındaki bağımlılıkları yönetme. RC,. CPP ve. H dosyaları** Visual C++, gereksiz yeniden derlemeden nasıl önleneceğini açıklar. Kaynak sembol dosyalarına bağımlı olan CPP dosyaları.

- **Visual C++ nasıl yönettiği belirleme bilgileri** , Visual C++ birden çok (iç içe geçmiş) nasıl izletiğine ilişkin teknik ayrıntılar sağlar. RC dosyaları ve #include birden çok üstbilgi dosyası. RC dosyası.

## <a name="overview-of-how-visual-c-manages-resource-files-and-header-files"></a>Visual C++ kaynak dosyalarını ve üst bilgi dosyalarını nasıl yönettiğini genel bakış

Visual C++ tek bir yönetir. RC kaynak dosyası ve buna karşılık gelen. Daha sıkı bir şekilde bağlanmış dosya çifti olarak H üstbilgi dosyası. Kaynakları bir içinde düzenleyip kaydettiğinizde. RC dosyası, bunlara karşılık gelen simgeleri dolaylı olarak düzenleyip kaydedersiniz. H dosyası. Birden çok çoklu açıp düzenleyebilseniz de. Belirli bir zamanda RC dosyaları (Visual C++ MDI Kullanıcı arabirimini kullanarak). RC dosyası tam olarak bir karşılık gelen üst bilgi dosyasını düzenleyebilirsiniz.

### <a name="symbol-header-file"></a>Sembol üst bilgi dosyası

Varsayılan olarak, Visual C++ her zaman karşılık gelen üstbilgi dosyası KAYNAĞıNı adlandırır. H, kaynak dosyasının adından bağımsız olarak (ör., MYAPP. RC). Visual C++ ' deki **Görünüm** menüsünden **kaynak içerme** komutunu kullanarak, bu üstbilgi dosyasının adını, **eklemeleri ayarla** iletişim kutusundaki sembol üstbilgi dosyası dosyasını güncelleştirerek değiştirebilirsiniz.

### <a name="read-only-symbol-directives"></a>Read-Only sembol yönergeleri

Visual C++, yalnızca bir üst bilgi dosyasını belirli bir tane için düzenler. RC dosyası Visual C++, ek salt okuma üst bilgi dosyalarında tanımlanan simgelere yönelik başvuruları destekler. Visual C++ ' deki **Görünüm** menüsünden **kaynak içerme** komutunu kullanarak, herhangi bir sayıda ek salt okuma üst bilgi dosyasını Read-Only sembol yönergeleri olarak belirtebilirsiniz. "Salt okunurdur" kısıtlaması, içinde yeni bir kaynak eklediğinizde anlamına gelir. RC dosyası, salt okuma üst bilgi dosyasında tanımlanan bir simge kullanabilirsiniz; Ancak, kaynağı silerseniz, simge salt okunurdur. Salt bir salt okuma simgesine atanan sayısal değeri değiştiremezsiniz.

### <a name="compile-time-directives"></a>Compile-Time yönergeleri

Visual C++, kaynak dosyalarının iç içe geçirilmesi da destekler. RC dosyası başka bir #include. Belirli bir düzenleme yaptığınızda. RC dosyası Visual C++ kullanarak #include ve dosyalardaki tüm kaynaklar görünür değildir. Ancak öğesini derlerken. RC dosyası, #include i dosyaları da derlenir. Visual C++ ' deki **Görünüm** menüsünden **kaynak içerme** komutunu kullanarak istediğiniz sayıda #include belirtebilirsiniz. Compile-Time yönergeler olarak RC dosyaları.

Visual C++ ' a okuduğunuzda ne olacağını aklınızda edin. #İnclude başka bir tane olan RC dosyası. Compile-Time yönergesi *olarak BELIRTILMEYEN RC* dosyası. Visual C++ bir ' a getirdiğinizde bu durum oluşabilir. Daha önce bir metin düzenleyicisiyle el ile dağıttığınız RC dosyası. Visual C++ #include ' i okuduğunda. RC dosyası, #include i kaynaklarını üst ile birleştirir. RC dosyası. Üst öğeyi kaydettiğinizde. RC dosyası, etkin olan #include deyimin #include ve kaynakları tarafından değiştirilmeyecektir. Bu birleştirmenin gerçekleşmesini istemiyorsanız, üst öğeden #include ifadesini kaldırmalısınız. RC dosyası Visual C++ ' ye okumadan *önce* ; Visual C++ kullanarak, Compile-Time yönergesi olarak aynı #include ifadesini geri ekleyin.

Visual C++ ' a kaydedilir. RC dosyası Yukarıdaki üç tür, #include yönergelerinden *ve* TEXTINCLUDE kaynaklarında bilgi (sembol üstbilgi dosyası, Read-Only sembol yönergeleri ve Compile-Time yönergeleri) içerir. Normalde uğraşmanız gerekmeyen bir uygulama ayrıntısı olan TEXTıNCLUDE kaynakları, [Visual C++ yönetme kümesinin bilgileri nasıl Içerdiği hakkında](#_mfcnotes_tn035_set_includes)açıklanmıştır.

## <a name="analysis-of-appwizard-created-rc-and-h-files"></a>AppWizard-Created analizi. RC ve. H dosyaları

AppWizard tarafından üretilen uygulama kodunu incelemek, Visual C++ birden çok kaynak dosyasını ve üstbilgi dosyasını nasıl yönettiğini açıklar. Aşağıda incelenen alıntıları kodu, varsayılan seçenekleri kullanarak AppWizard tarafından oluşturulan bir MyApp uygulamasından alınmıştır.

AppWizard tarafından oluşturulan bir uygulama, aşağıdaki diyagramda özetlenen birden çok kaynak dosyasını ve birden çok üstbilgi dosyasını kullanır:

```Diagram
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

Bu birden çok dosya ilişkisini Visual C++ File/Set Içerme komutunu kullanarak görüntüleyebilirsiniz.

MyApp. RC
Visual C++ kullanarak düzenlediğiniz uygulama kaynak dosyası.

Kaynak. H uygulamaya özgü üst bilgi dosyasıdır. Her zaman kaynak olarak adlandırılır. H by AppWizard, Visual C++ üst bilgi dosyasının varsayılan adlandırmasıyla tutarlıdır. Bu üstbilgi dosyası için #include, kaynak dosyasındaki (MYAPP) ilk ifadedir. RC):

```rc
//Microsoft Visual C++ generated resource script
//
#include "resource.h"
```

RES\MYAPP. RC2
Visual C++ tarafından düzenlenmeyecek ancak son derlenmiş koda dahil edilecek kaynakları içerir. EXE dosyası. Visual C++, sürüm kaynağı (Bu sürümdeki yeni bir özellik) dahil olmak üzere tüm standart kaynakları düzenleyebilmesi için, varsayılan olarak böyle bir kaynak oluşturur. Bu dosyaya kendi özel biçimli kaynaklarınızı eklemek istemeniz durumunda AppWizard tarafından boş bir dosya oluşturulur.

Özel biçimlendirilen kaynaklar kullanıyorsanız bunları RES\MYAPP' e ekleyebilirsiniz. RC2 Visual C++ metin düzenleyicisini kullanarak düzenleyin.

AFXRES. RC ve AFXPRINT. RC, Framework 'ün belirli özellikleri için gereken standart kaynakları içerir. RES\MYAPPGIBI. RC2, bu iki Framework tarafından sağlanmış kaynak dosyaları MYAPP 'in sonunda #include. RC ve bunlar, eklemeleri ayarla iletişim kutusunun Compile-Time yönergelerinde belirtilmiştir. Bu nedenle, MYAPP 'i düzenlerken bu Framework kaynaklarını doğrudan görüntüleyemez veya düzenleyemezsiniz. RC Visual C++, ancak uygulamanın ikilisinde derlenirler. RES dosyası ve son. EXE dosyası. Standart çerçeve kaynakları hakkında daha fazla bilgi için, bunları değiştirme yordamları da dahil olmak üzere bkz. [teknik notta 23](../mfc/tn023-standard-mfc-resources.md).

AFXRES. H, `ID_FILE_NEW` Framework tarafından kullanılan ve özel olarak AFXRES 'de kullanılan standart sembolleri tanımlar. RC. AFXRES. H Ayrıca #include. WINDOWS 'un bir alt kümesini içeren H. Visual C++ oluşturulması için gereken H. RC dosyalarının yanı sıra AFXRES. RC. AFXRES 'de tanımlanan semboller. H, uygulama kaynak dosyasını (MYAPP) düzenlerken kullanılabilir. RC). Örneğin, `ID_FILE_NEW` MyApp Içindeki dosya yeni menü öğesi için kullanılır. RC 'nin menü kaynağı. Bu çerçeve tanımlı sembolleri değiştiremez veya silemezsiniz.

## <a name="including-additional-header-files"></a><a name="_mfcnotes_tn035_including"></a> Ek üstbilgi dosyaları dahil

AppWizard tarafından oluşturulan uygulama yalnızca iki başlık dosyası içerir: kaynak. H ve AFXRES. H. Yalnızca kaynak. H uygulamaya özgüdür. Aşağıdaki durumlarda, ek salt okuma üst bilgi dosyalarını eklemeniz gerekebilir:

Üst bilgi dosyası bir dış kaynak tarafından sağlanır veya üst bilgi dosyasını birden çok proje veya aynı projenin birden fazla bölümü arasında paylaştırmak istiyorsunuz.

Üst bilgi dosyasında, dosyayı kaydettiğinde Visual C++ değiştirmesini veya filtrelemenizi istemediğiniz biçimlendirme ve açıklamalar vardır. Örneğin, şu gibi sembolik aritmetik kullanan #define korumak isteyebilirsiniz:

```h
#define RED 0
#define BLUE 1
#define GREEN 2
#define ID_COLOR_BUTTON 1001
#define ID_RED_BUTTON (ID_COLOR_BUTTON + RED)
#define ID_BLUE_BUTTON (ID_COLOR_BUTTON + BLUE)
#define ID_GREEN_BUTTON (ID_COLOR_BUTTON + GREEN)
```

#İnclude ekstresini ikinci bir Read-Only sembol yönergesi olarak belirtmek için **kaynak içerme** komutunu kullanarak ek salt okuma üst bilgi dosyalarını dahil edebilirsiniz:

```rc
#include "afxres.h"
#include "second.h"
```

Yeni dosya ilişkisi diyagramı şimdi şöyle görünür:

```Diagram
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

## <a name="sharing-a-header-file-between-two-rc-files"></a>Üst bilgi dosyasını Iki arasında paylaşma. RC dosyaları

Bir üst bilgi dosyasını iki arasında paylaşmak isteyebilirsiniz. Farklı projelerde veya muhtemelen aynı projede olan RC dosyaları. Bunu yapmak için yukarıda açıklanan Read-Only yönergeleri tekniğini her ikisine de uygulamanız yeterlidir. RC dosyaları. İki durumda. RC dosyaları farklı uygulamalar içindir (farklı projeler), sonuç aşağıdaki diyagramda gösterilmiştir:

```Diagram
     RESOURCE.H   AFXRES.H   RESOURCE.H  
    (for MYAPP1)  SECOND.H   (for MYAPP2)
          \       /     \       /
           \     /       \     /
          MYAPP1.RC      MYAPP2.RC
           /    \        /     \
          /      \      /       \
RES\MYAPP1.RC2  AFXRES.RC     RES\MYAPP2.RC2
                AFXPRINT.RC
```

İkinci üst bilgi dosyasının iki tarafından paylaşıldığı durum. Aynı uygulama (proje) içindeki RC dosyaları aşağıda ele alınmıştır.

## <a name="using-multiple-resource-files-in-the-same-project"></a>Aynı projede birden fazla kaynak dosyası kullanma

Visual C++ ve kaynak derleyicisi birden çok destekler. #İnclude bir projede aynı projedeki RC dosyaları. Başka bir dosya içinde RC dosyası. Çoklu iç içe geçmeye izin veriliyor. Projenizin kaynaklarını birden çok olarak bölmek için çeşitli nedenler vardır. RC dosyaları:

- Kaynakları birden çok olarak bölmek birden çok proje ekibi üyesi arasında çok sayıda kaynağı yönetmek daha kolaydır. RC dosyaları. Dosyaları kullanıma alma ve değişiklikleri iade etme için bir kaynak denetimi Yönetim Paketi kullanıyorsanız, kaynakları birden çok olarak böyor. RC dosyaları, kaynaklarda yapılan değişiklikleri yönetmeye yönelik daha ayrıntılı bir denetim sağlar.

- Kaynaklarınızın bölümleri için #ifdef, #endif ve #define gibi Önişlemci yönergeleri kullanmak istiyorsanız, bunları kaynak derleyicisi tarafından derlenecek salt okuma kaynaklarında yalıtmanız gerekir.

- Bileşeninde. RC dosyaları, bir bileşik Visual C++ daha hızlı yüklenip kaydedilir. RC dosyası.

- Bir kaynağı, insan tarafından okunabilen bir formda metin Düzenleyicisi ile korumak istiyorsanız, bir içinde saklamanız gerekir. RC dosyası Visual C++ düzenlemelerden ayrı.

- Kullanıcı tanımlı bir kaynağı başka bir özelleştirilmiş veri Düzenleyicisi tarafından yorumlanarak bir ikili veya metin biçiminde tutmanız gerekiyorsa, bunu ayrı tutmanız gerekir. RC dosyası Visual C++ biçimi onaltılık verilerle değiştirmez. İçin. MFC gelişmiş kavramlar örnek [Hoparlörkn](../overview/visual-cpp-samples.md) 'de WAV (ses) dosya kaynakları iyi bir örnektir.

IKINCI #include. RC, şunları ayarla iletişim kutusundaki Compile-Time yönergelerden:

```h
#include "res\myapp.rc2"  // non-Visual C++ edited resources
#include "second.rc"  // THE SECOND .RC FILE

#include "afxres.rc"  // Standard components
#include "afxprint.rc"  // printing/print preview resources
```

Sonuç aşağıdaki diyagramda gösterilmiştir:

```Diagram
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

Compile-Time yönergeleri kullanarak, Visual C++ düzenlenebilir ve düzenlenemeyen kaynakları birden çok farklı şekilde düzenleyebilirsiniz. RC dosyaları, burada "ana" MYAPP. RC hiçbir şey yapmaz, ancak diğerini #include. RC dosyaları. Eğer bir Visual Studio C++ projesi kullanıyorsanız. MAK dosyası, ardından "ana" eklemeniz gerekir. Tüm #include kaynakları uygulamanızla derlenmek üzere projedeki RC dosyası.

## <a name="enforcement-of-noneditable-visual-c-files"></a>Düzenlenemeyen Visual C++ dosyaları zorlaması

AppWizard-oluşturulan RES\MYAPP. RC2 dosyası, yanlışlıkla Visual C++ *okumak istemediğiniz kaynakları* içeren bir dosya örneğidir ve daha sonra biçimlendirme bilgileri kaybından geri yazılır. Buna karşı korunmak için, RES\MYAPP'IN başına aşağıdaki satırları yerleştirin. RC2 dosyası:

```rc2
#ifdef APSTUDIO_INVOKED
    #error this file is not editable by Visual C++
#endif //APSTUDIO_INVOKED
```

Visual C++ derlediğinde. RC dosyası, ve `APSTUDIO_INVOKED` de tanımlar `RC_INVOKED` . AppWizard tarafından oluşturulan dosya yapısı bozuksa ve Visual C++ yukarıdaki #error satırı okuduğunda, önemli bir hata bildiriyor ve ' ı okumayı iptal ediyor. RC dosyası.

## <a name="managing-symbols-shared-by-multiple-visual-c-edited-rc-files"></a>Birden çok Visual C++ tarafından paylaşılan sembolleri yönetme. RC dosyaları

Kaynaklarınızı birden çok olarak böldüğünüz zaman iki sorun oluşur. Visual C++ içinde ayrı olarak düzenlemek istediğiniz RC dosyaları:

- Aynı sembolleri birden çok üzerinde paylaşmak isteyebilirsiniz. RC dosyaları.

- Aynı KIMLIK sayısal değerlerinin ayrı kaynaklara (semboller) atanmaması Visual C++ yardım etmeniz gerekir.

Aşağıdaki diyagramda bir kuruluşu gösterilmektedir. RC ve. İlk sorunla ilgilenen H dosyaları:

```Diagram
              MYAPP.RC
             /         \
            /           \
MYSTRS.H   / MYSHARED.H  \  MYMENUS.H
     \    /    /      \   \    \
      \  /    /        \   \    \
      MYSTRS.RC         MYMENUS.RC
```

Bu örnekte, dize kaynakları bir kaynak dosyasında, MYSTRS olarak tutulur. RC ve menüler farklı, MYMENUS içinde tutulur. RC. Komutlar gibi bazı simgelerin iki Dosya arasında paylaşılması gerekebilir. Örneğin, bir ID_TOOLS_SPELL bir araç menüsündeki Yazım öğesi için menü komut KIMLIĞI olabilir; Ayrıca, uygulamanın ana pencere durum çubuğunda çerçeve tarafından görüntülenmiş komut isteminin dize KIMLIĞI de olabilir.

ID_TOOLS_SPELL sembol, MYSHARED. H paylaşılan üstbilgi dosyasında tutulur. Bu paylaşılan üstbilgi dosyasını bir metin düzenleyicisiyle el ile koruyun; Visual C++ doğrudan düzenleyemez. İki kaynak dosyasında MYSTRS. RC ve MYMENUS. RC, MYSHARED #include belirtirsiniz. & MYAPP için Read-Only yönergeler. RC, daha önce açıklandığı gibi, **kaynak içerme** komutunu kullanmaktır.

Herhangi bir kaynağı tanımlamak için kullanmayı denemeden önce, paylaştığınız bir sembolü tahmin etmek en iyi yöntemdir. Simgeyi paylaşılan üstbilgi dosyasına ekleyin ve Read-Only yönergelerinden paylaşılan üst bilgi dosyasını #include. RC dosyası, sembolü kullanmadan önce bunu yapın. Bu şekilde sembolün paylaşımını tahmin etmek için bu şekilde el ile (bir metin düzenleyicisi kullanarak), simgenin #define ifadesini, deyin, MYMENUS öğesinden taşıyın. H ile MYSHARED. MYSTRS 'de kullanmadan önce H. RC.

Sembolleri birden çok olarak yönettiğinizde. Ayrıca, aynı KIMLIK sayısal değerlerinin ayrı kaynaklara (semboller) atanmaması Visual C++ de yardımcı olmanız gerekir. Herhangi biri için. RC dosyası, Visual C++ dört KIMLIK alanındaki her birine artımlı olarak kimlik atar. Visual C++, Düzenle oturumları arasında, için sembol üstbilgi dosyasındaki her etki alanında atanan son KIMLIĞI izler. RC dosyası. APS_NEXT değerleri boş (yeni) için verilmiştir. RC dosyası:

```rc
#define _APS_NEXT_RESOURCE_VALUE  101
#define _APS_NEXT_COMMAND_VALUE   40001
#define _APS_NEXT_CONTROL_VALUE   1000
#define _APS_NEXT_SYMED_VALUE     101
```

`_APS_NEXT_RESOURCE_VALUE` , bir iletişim kaynağı, menü kaynağı vb. için kullanılacak sonraki sembol değeridir. Kaynak sembol değerleri için geçerli Aralık 1 ile 0x6FFF arasındadır.

`_APS_NEXT_COMMAND_VALUE` , bir komut kimliği için kullanılacak sonraki sembol değeridir. Komut sembol değerleri için geçerli Aralık 0x8000 ile 0xDFFF arasındadır.

`_APS_NEXT_CONTROL_VALUE` , bir iletişim kutusu denetimi için kullanılacak sonraki sembol değeridir. İletişim kutusu denetimi sembol değerleri için geçerli Aralık 8 ile 0xDFFF arasındadır.

`_APS_NEXT_SYMED_VALUE` , sembol tarayıcısında yeni komutu kullanarak bir sembol değerini el ile atadığınızda verilen bir sonraki sembol değeridir.

Visual C++, yeni bir oluşturma sırasında en düşük yasal değere göre biraz daha yüksek değerlerle başlar. RC dosyası. AppWizard Ayrıca bu değerleri MFC uygulamalarına daha uygun bir şeye başlatacak. KIMLIK değeri aralıkları hakkında daha fazla bilgi için bkz. [teknik notta 20](../mfc/tn020-id-naming-and-numbering-conventions.md).

Artık aynı projede bile her yeni kaynak dosyası oluşturduğunuzda, Visual C++ aynı `_APS_NEXT_` değerleri tanımlar. Diğer bir deyişle, iki farklı iletişim kutusu eklerseniz, söylerseniz. RC dosyaları, aynı #define değerinin farklı iletişim kutularına atanması büyük olasılıkla yüksektir. Örneğin, ilk ' de IDD_MY_DLG1. RC dosyasına, IDD_MY_DLG2 aynı sayı 101, ikincisi de atanmış olabilir. RC dosyası.

Bunu önlemek için, karşılık gelen her dört etki alanı için ayrı bir sayısal Aralık ayırmanız gerekir. RC dosyaları. Her birinin değerlerini el ile güncelleştirerek bunu yapın `_APS_NEXT` . Kaynak eklemeye **başlamadan önce** RC dosyaları. Örneğin, ilki. RC dosyası varsayılan değerleri kullanır `_APS_NEXT` , ardından aşağıdaki değerleri ikinci değere atamak isteyebilirsiniz `_APS_NEXT` . RC dosyası:

```rc
#define _APS_NEXT_RESOURCE_VALUE  2000
#define _APS_NEXT_COMMAND_VALUE   42000
#define _APS_NEXT_CONTROL_VALUE   2000
#define _APS_NEXT_SYMED_VALUE     2000
```

Kuşkusuz, Visual C++ ilk olarak çok sayıda kimliği atayacaktır. Bu, sayısal değerlerin ikincisi için ayrılmış olanlarla örtüşmeye başlayacağı RC dosyası. RC dosyası. Bunun gerçekleşmemesi için yeterince büyük aralıklar ayırmanız gerekir.

## <a name="managing-dependencies-between-rc-cpp-and-h-files"></a>Arasındaki bağımlılıkları yönetme. RC,. CPP ve. H dosyaları

Visual C++ bir kaydeder. RC dosyası, simge değişikliklerini karşılık gelen kaynağa de kaydeder. H dosyası. Herhangi biri. İçindeki kaynaklara başvuran CPP dosyaları. RC dosyasının kaynağı #include gerekir. H dosyasında, genellikle projenizin ana üstbilgi dosyası içinden. Bu, geliştirme ortamının, üst bilgi bağımlılıkları için kaynak dosyalarını tarayan iç proje yönetimi nedeniyle istenmeyen yan etkiye yol açar. Visual C++ ' a her yeni bir sembol eklediğiniz her seferinde, tüm. Kaynak #include olan CPP dosyaları. H 'nin yeniden derlenmesi gerekiyor.

Visual C++, kaynak bağımlılığı atlama. H, KAYNAĞıN ilk satırı olarak aşağıdaki yorumu ekleyerek. H dosyası:

```h
//{{NO_DEPENDENCIES}}
```

Geliştirme ortamı, kaynak değişikliklerini yoksayarak bu yorumu yorumlar. Bu şekilde değişir. CPP dosyalarının yeniden derlenmesi gerekmez.

Visual C++ her zaman//{{NO_DEPENDENCIES}} yorum satırını bir öğesine ekler. Dosyayı kaydettiğinde RC dosyası. Bazı durumlarda, kaynak üzerinde derleme bağımlılığı atlatıcılık. H bağlantı zamanında algılanmayan çalışma zamanı hatalarına neden olabilir. Örneğin, bir kaynak için bir simgeye atanan sayısal değeri değiştirmek üzere sembol tarayıcısını kullanırsanız, kaynak doğru şekilde bulunamacaktır ve. Kaynağa başvuran CPP dosyası yeniden derlenmedi. Böyle durumlarda, herhangi birini açıkça yeniden derlemeniz gerekir. Bildiğiniz CPP dosyaları KAYNAKTAKI sembol değişikliklerinden etkilendi. H veya **tümünü yeniden derle** seçeneğini belirleyin. Belirli bir kaynak grubu için simge değerlerini sık sık değiştirmeniz gerekiyorsa, bu sembolleri daha kolay ve daha güvenli bir şekilde, [diğer üst bilgi dosyaları da dahil olmak üzere](#_mfcnotes_tn035_including)yukarıdaki bölümde açıklandığı gibi ayrı bir salt okunurdur.

## <a name="how-visual-c-manages-set-includes-information"></a><a name="_mfcnotes_tn035_set_includes"></a> Visual C++ nasıl yönettiği belirleme bilgi Içerir

Yukarıda açıklandığı gibi, Dosya menü kümesi Içerir komutu, üç tür bilgi belirtmenizi sağlar:

- Sembol üst bilgi dosyası

- Read-Only sembol yönergeleri

- Compile-Time yönergeleri

Aşağıda Visual C++ bu bilgileri bir içinde nasıl koruduğu açıklanmaktadır. RC dosyası. Visual C++ kullanmak için bu bilgilere ihtiyacınız yoktur, ancak şunları anlamak için daha fazla bilgi kümesini Ayarla özelliğini kullanabilirsiniz.

Yukarıdaki üç küme türünün her biri bilgi Içerir ve içinde depolanır. İki formdaki RC dosyası: (1) kaynak derleyicisi tarafından #include veya diğer yönergeler yorumlayarak ve (2) özel TEXTıNCLUDE kaynakları yorumda yalnızca Visual C++.

TEXTıNCLUDE kaynağının amacı, Visual C++ **set** include Include iletişim kutusunda kolay bir biçimde tür bilgilerini güvenli bir şekilde depolayasağlamaktır. TEXTıNCLUDE, Visual C++ tarafından tanımlanan bir *kaynak türüdür* . Visual C++ kaynak kimlik numarası 1, 2 ve 3 olan üç özel TEXTıNCLUDE kaynağını tanır:

|TEXTıNCLUDE kaynak KIMLIĞI|Küme Içeren tür bilgileri|
|-----------------------------|--------------------------------------|
|1|Sembol üst bilgi dosyası|
|2|Read-Only sembol yönergeleri|
|3|Compile-Time yönergeleri|

Her bir küme türü bilgi Içerir, varsayılan MYAPP tarafından gösterilmiştir. RC ve kaynak. Aşağıda açıklandığı gibi AppWizard tarafından oluşturulan H dosyaları. BAŞLANGıÇ ve BITIŞ blokları arasındaki fazladan \ 0 ve "" belirteçleri, sırasıyla sıfır ile sonlandırılmış dizeler ve çift tırnak karakteri belirtmek için RC söz dizimiyle gereklidir.

### <a name="symbol-header-file"></a>Sembol üst bilgi dosyası

Kaynak derleyicisi tarafından yorumlanan sembol üstbilgi dosyası bilgilerinin biçimi yalnızca bir #include deyimidir:

```rc
#include "resource.h"
```

Karşılık gelen TEXTıNCLUDE kaynağı:

```rc
1 TEXTINCLUDE DISCARDABLE
BEGIN
    "resource.h\0"
END
```

### <a name="read-only-symbol-directives"></a>Read-Only sembol yönergeleri

Read-Only sembol yönergeleri MYAPP 'in üst kısmına dahildir. RC, kaynak derleyicisi tarafından aşağıdaki formda yorumda verilmiştir:

```rc
#include "afxres.h"
```

Karşılık gelen TEXTıNCLUDE kaynağı:

```rc
2 TEXTINCLUDE DISCARDABLE
BEGIN
   "#include ""afxres.h""\r\n"
   "\0"
END
```

### <a name="compile-time-directives"></a>Compile-Time yönergeleri

Compile-Time yönergeler MYAPP 'in sonuna eklenmiştir. RC, kaynak derleyicisi tarafından aşağıdaki formda yorumda verilmiştir:

```rc
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

#İfndef APSTUDIO_INVOKED yönergesi, Compile-Time yönergelerinin atlanmasını Visual C++ söyler.

Karşılık gelen TEXTıNCLUDE kaynağı:

```rc
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

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)\
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
