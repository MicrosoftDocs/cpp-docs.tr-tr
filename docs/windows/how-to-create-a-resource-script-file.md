---
title: 'Nasıl yapılır: Bir kaynak betik dosyası (C++) oluştur'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
- vc.resvw.add.MFC
helpviewer_keywords:
- rc files [C++], creating
- .rc files [C++], creating
- resource script files [C++], creating
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
- resource script files [C++], opening in text format
- .rc files [C++], opening in text format
- rc files [C++], opening in text format
- rc files [C++], adding MFC support
- .rc files [C++], adding MFC support
- MFC, adding support to resource scripts files
- resource script files [C++], adding MFC support
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
ms.openlocfilehash: 9055e0f787c238276d3134c2fa6a8afae0102433
ms.sourcegitcommit: 5a7dbd640376e13379f5d5b2cf66c4842e5e737b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55905686"
---
# <a name="how-to-create-a-resource-script-file-c"></a>Nasıl yapılır: Bir kaynak betik dosyası (C++) oluştur

> [!NOTE]
> **Kaynak Düzenleyicisi** Express sürümlerinde kullanılamaz.
>
> Bu yazıda, Windows Masaüstü uygulamaları için geçerlidir. .NET dilleri projelerde kaynak betik dosyalarına kullanmayın. Daha fazla bilgi için [kaynak dosyaları](../windows/resource-files-visual-studio.md).

## <a name="to-create-a-new-resource-script-rc-file"></a>Yeni bir kaynak betiği (.rc) dosyası oluşturmak için

1. Mevcut proje klasörünüzde odak yerleştirin **Çözüm Gezgini**, örneğin, `MyProject`.

   > [!NOTE]
   > Proje klasörü çözüm klasöründe ile karıştırmayın **Çözüm Gezgini**. Odak moduna geçirirseniz **çözüm** klasörü, seçimlerinize **Yeni Öğe Ekle** iletişim kutusunda (3. adım) farklı olacaktır.

1. Üzerinde **proje** menüsünde **Yeni Öğe Ekle**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **Visual C++** klasörü seçin **kaynak dosyası (.rc)** sağ bölmede.

1. Kaynak kod dosyanız için bir ad sağlayın **adı** metin kutusuna ve ardından **açık**.

Artık [oluşturma](../windows/how-to-create-a-resource.md) ve yeni kaynaklar, .rc dosyasına ekleyin.

> [!NOTE]
> Kaynak betiği (.rc dosyası) yalnızca Visual Studio IDE'ye yüklenir, varolan bir projeye de ekleyebilirsiniz. Bir tek başına .rc dosyasını (projenin dışında bir tane) oluşturulamıyor. [Kaynak şablonları](../windows/how-to-use-resource-templates.md) (.rct dosyaları) dilediğiniz zaman oluşturulabilir.

## <a name="to-open-a-resource-script-file-outside-of-a-c-project-standalone"></a>(Tek başına) C++ proje dışındaki kaynak betik dosyasını açmak için

Bir proje açmak zorunda kalmadan bir .rc dosyasındaki kaynakları görüntüleyebilirsiniz. .Rc dosyasının'te açılmasını aksine bir belge penceresi açılır [kaynak görünümü](../windows/resource-view-window.md) penceresi (dosya içinde bir proje açıkken çalıştığı gibi).

> [!NOTE]
> Bazı komutlar yalnızca dosya açılan tek başına (proje dışında) olduğunda kullanılabilir olmadığından önemli bir fark budur. Dosyanın dışında bir proje açıldığında, örneğin, yalnızca bir dosyayı farklı bir biçimde veya farklı bir dosya adı olarak kaydedebilirsiniz ( **Kaydet** komutu, bir dosya içinde bir proje açıldığında kullanılamaz).

### <a name="to-open-an-rc-file-outside-a-project"></a>Bir proje dışında bir .rc dosyasını açmak için

1. Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.

1. İçinde **açık dosya** iletişim kutusunda, istediğiniz görüntülemek için dosyayı vurgulayın ve seçmek için kaynak betik dosyasına gidin **açık**.

   > [!NOTE]
   > İlk proje açarsanız (**dosya**, **açın**, **proje**), bazı komutlar için kullanılabilir olmayacak. "Tek başına" dosyasını açıp, proje yüklemeden açmadan anlamına gelir.

### <a name="to-open-multiple-rc-files-outside-a-project"></a>Birden çok .rc dosyası bir proje dışında açmak için

1. Tek başına hem de kaynak dosyalarını açın. Örneğin, açmak `Source1.rc` ve `Source2.rc`.

   1. Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.

   1. İçinde **Dosya Aç** iletişim kutusunda, açmak istediğiniz ilk kaynak betik dosyasına gidin (`Source1.rc`), dosyayı vurgulayın ve seçme **açın**.

   1. İkinci .rc dosyasını açmak için önceki adımı yineleyin (`Source2.rc`).

       .Rc dosyaları artık ayrı bir belge pencerelerinde açıktır.

1. Her iki .rc dosyası açıkken, aynı anda görebilecek şekilde pencereleri döşe:

   - Gelen **penceresi** menüsünde seçin **yeni yatay sekme grubu** veya **yeni bir dikey sekme grubu**.

       \- veya -

   - .Rc dosyaları birine sağ tıklayın ve seçin **yeni yatay sekme grubu** veya **yeni bir dikey sekme grubu** kısayol menüsünden.

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

## <a name="to-open-a-resource-script-file-in-text-format"></a>Kaynak betik dosyasını metin biçiminde açmak için

Belirli kaynak düzenleyicisinin içinde bir iletişim kutusu gibi bir kaynak açmaya gerek kalmadan proje kaynak betiği (.rc) dosyasının içeriğini görüntülemek istediğinizde zamanlar olabilir. Örneğin, her biri ayrı olarak açmak zorunda kalmadan kaynak dosyasındaki tüm iletişim kutuları arasında bir dize aramak isteyebilirsiniz.

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

Kaynak dosya, içerdiği tüm kaynakları görüntülemek ve metin düzenleyicisi tarafından desteklenen genel işlemleri tamamlamak için metin biçiminde kolayca açabilirsiniz.

> [!NOTE]
> Kaynak düzenleyicileri .rc doğrudan okunmaz veya `resource.h` dosyaları. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derlenir. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar. (Örneğin, açıklamalar) sembolik değil bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir. .Rc dosyasıyla .aps dosyası zaman uyumsuz olarak alır her .rc dosyası yeniden oluşturuldu (kaydettiğinizde, örneğin, kaynak düzenleyicisini .rc dosyasını ve resource.h dosyasını geçersiz kılar). Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamalar her zaman kaybolacak. Açıklamaları koruma hakkında daha fazla bilgi için bkz: [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).

### <a name="to-open-a-resource-script-file-as-text"></a>Kaynak betik dosyasını metin olarak açmak için

1. Gelen **dosya** menüsünde **açık**, ardından **dosya**.

1. İçinde **açık dosya** iletişim kutusunda, metin biçiminde görüntülemek istediğiniz kaynak betik dosyasına gidin.

1. Dosyayı vurgulayın ve ardından açılan liste okunu seçin **açık** düğme (düğme sağ tarafında bulunur).

1. Seçin **birlikte Aç** aşağı açılan menüden.

1. İçinde **birlikte Aç** iletişim kutusunda **kaynak kodu (metin) Düzenleyicisi**.

1. Gelen **açık olarak** aşağı açılan listesinden **metin**.

   Kaynak açılır **kaynak kodu** Düzenleyici.

\- veya -

1. İçinde **Çözüm Gezgini**, .rc dosyasına sağ tıklayın.

1. Kısayol menüsünden **birlikte Aç...** , ardından **kaynak kodu (metin) Düzenleyicisi**.

## <a name="to-add-mfc-support-to-resource-script-files"></a>Kaynak betik dosyalarına MFC desteği eklemek için

Normalde, Windows kullanmaya yönelik bir MFC uygulaması oluşturduğunuzda [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md), Microsoft Foundation'ın temel özelliklerini içeren temel bir kümesi (kaynak betiği (.rc) dosyası da dahil olmak üzere) dosyaları sihirbaz oluşturur sınıfları (MFC). Ancak, MFC'ye dayalı olmayan bir Windows uygulaması için bir .rc dosyasını düzenliyorsanız MFC çerçevesine özgü aşağıdaki özellikler kullanılamaz:

- MFC kodu sihirbazları

- Menü komut istemi dizeleri

- Birleşik giriş kutusu denetimleri için Liste içeriği

- ActiveX denetimi barındırma

Ancak sahip olmayan var olan .rc dosyalarına MFC desteği ekleyebilirsiniz.

> [!NOTE]
> MFC adımları gerektirir.

### <a name="to-add-mfc-support-to-rc-files"></a>.Rc dosyalarına MFC desteği eklemek için

1. Kaynak betik dosyasını açın.

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), (örneğin, MFC.rc) kaynaklar klasörünü vurgulayın.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)ayarlayın **MFC modu** özelliğini **True**.

   > [!NOTE]
   > Bu bayrağı ayarlamanın yanı sıra .rc dosyası bir MFC projesinin bir parçası olmalıdır. Örneğin, yalnızca ayarlamak **MFC modu** için **True** bir .rc dosyasının bir Win32 Proje MFC özelliklerinden hiçbirini size olmaz.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)