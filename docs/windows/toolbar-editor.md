---
title: Araç Çubuğu Düzenleyicisi (C++)
description: Araç çubuğu kaynakları oluşturmak ve bit eşlemleri araç çubuğu kaynaklarına dönüştürmek için Visual Studio araç çubuğu düzenleyicisini kullanın.
ms.date: 09/26/2020
f1_keywords:
- vc.editors.toolbar.F1
- vc.editors.toolbar
- vc.editors.newtoolbarresource
helpviewer_keywords:
- resource editors [C++], Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
- toolbars [C++], creating
- Toolbar editor [C++], creating new toolbars
- Insert Resource
- bitmaps [C++], converting to toolbars
- Toolbar editor [C++], converting bitmaps
- toolbars [C++], converting bitmaps
- New Toolbar Resource dialog box [C++]
- buttons [C++], custom toolbars
- toolbar buttons [C++], editing
- buttons
- toolbar buttons [C++], creating
- Toolbar editor [C++], creating buttons
- toolbar buttons [C++], button image
- toolbar buttons [C++], creating
- toolbar buttons (in Toolbar editor)
- toolbar buttons [C++], moving
- Toolbar editor [C++], moving buttons
- Toolbar editor [C++], copying buttons
- toolbars [C++], copying buttons
- toolbar buttons [C++], copying
- toolbar buttons [C++], deleting
- Toolbar editor [C++], deleting buttons
- Toolbar editor [C++], spacing toolbar buttons
- toolbar buttons [C++], space between buttons
- toolbar controls [MFC], command ID
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- command IDs, toolbar buttons
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
- tool tips [C++], adding to toolbar buttons
- "\n in tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor [C++], creating tool tips
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
ms.openlocfilehash: 042bfafb1e55d45145306a8c388e1e3559fa9a33
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413807"
---
# <a name="toolbar-editor-c"></a>Araç Çubuğu Düzenleyicisi (C++)

**Araç Çubuğu Düzenleyicisi** , araç çubuğu kaynakları oluşturmanızı ve bit eşlemleri araç çubuğu kaynaklarına dönüştürmenizi sağlar. **Araç Çubuğu Düzenleyicisi** bir grafik görüntü kullanır. Tamamlanmış bir uygulamada nasıl göründükleri yakından benzeyen bir araç çubuğu ve düğmeler gösterir.

**Araç Çubuğu Düzenleyicisi** penceresi, **resim Düzenleyicisi** penceresiyle aynı olan bir düğme resminin iki görünümünü gösterir. Bölünmüş çubuk iki bölmeyi ayırır. Bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu yan yana sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir ve görüntünün iki görünümünün üzerinde konu araç çubuğu bulunur.

![Araç Çubuğu Düzenleyicisi](../mfc/media/vctoolbareditor.gif "vcToolbarEditor")<br/>
**Araç Çubuğu Düzenleyicisi**

**Araç Çubuğu Düzenleyicisi** , Işlevselliğindeki **Görüntü Düzenleyicisi** ile benzerdir. Menü öğeleri, grafik araçları ve ikisi arasındaki bit eşlem Kılavuzu aynıdır. **Araç Çubuğu Düzenleyicisi** ve **Görüntü Düzenleyicisi**arasında geçiş yapmak için **görüntü** menüsünde bir menü komutu vardır. **Grafik** araç çubuğunu, **renkler** paletini veya **görüntü** menüsünü kullanma hakkında daha fazla bilgi için bkz. [görüntü düzenleyici](../windows/image-editor-for-icons.md).

Bir bit eşlem dönüştürerek C++ projesinde yeni bir araç çubuğu oluşturabilirsiniz. Bit eşlemdeki grafik, bir araç çubuğunun düğme görüntülerine dönüştürür. Genellikle bit eşlem, her düğme için bir görüntüyle tek bir bit eşlem üzerinde birkaç düğme görüntüsü içerir. Varsayılan değer 16 piksel genişliğinde ve görüntünün yüksekliği olacak şekilde görüntüler herhangi bir boyutta olabilir. Düğme görüntülerinin boyutunu **Yeni araç çubuğu kaynağı** iletişim kutusunda belirtebilirsiniz. Boyutları belirtmek için görüntü **Düzenleyicinizde** **görüntü** menüsünden **Araç Çubuğu Düzenleyicisi** ' ni seçin.

**Yeni araç çubuğu kaynağı** iletişim kutusu, bir C++ projesindeki bir araç çubuğu kaynağına eklemekte olduğunuz düğmelerin genişliğini ve yüksekliğini belirtmenize olanak tanır. Varsayılan değer 16 × 15 pikseldir.

Bir araç çubuğu oluşturmak için kullanılan bir bit eşlem maksimum 2048 genişliğine sahiptir. **Düğme genişliğini** *512*olarak ayarlarsanız yalnızca dört düğme olabilir. Genişliği *513*olarak ayarlarsanız yalnızca üç düğme olabilir.

**Yeni araç çubuğu kaynağı** iletişim kutusu aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---------------|
|**Düğme genişliği**|Bir bit eşlem kaynağından bir araç çubuğu kaynağına dönüştürdüğünüz araç çubuğu düğmelerinin genişliğini girebileceğiniz bir alan sağlar.|
|**Düğme yüksekliği**|Bir bit eşlem kaynağından bir araç çubuğu kaynağına dönüştürdüğünüz araç çubuğu düğmelerinin yüksekliğini girmeniz için bir alan sağlar.|

> [!NOTE]
> Görüntüler, belirtilen genişlik ve yüksekliğe kırpılır ve renkler standart araç çubuğu renklerini (16 renk) kullanacak şekilde ayarlanır.

Varsayılan olarak, araç çubuğu, araç çubuğunun sağ ucunda yeni veya boş bir düğme görüntüler. Düzenlemeden önce bu düğmeyi taşıyabilirsiniz. Yeni bir düğme oluşturduğunuzda, düzenlenen düğmesinin sağında başka bir boş düğme belirir. Bir araç çubuğunu kaydettiğinizde boş düğme kaydedilmez.

Bir araç çubuğu düğmesi aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|--------------|-----------------|
|**NUMARASıNı**|Düğme için KIMLIĞI tanımlar. Açılan liste, ortak **kimlik** adları sağlar.|
|**Genişlik**|Düğmenin genişliğini ayarlar. 16 piksel önerilir.|
|**Yükseklik**|Düğmenin yüksekliğini ayarlar. Bir düğmenin yüksekliği, araç çubuğundaki tüm düğmelerin yüksekliğini değiştirir. 15 piksel önerilir.|
|**İsteme**|Durum çubuğunda görünen iletiyi tanımlar. *\N* ve bir adı eklemek, bu araç çubuğu düğmesine bir araç **İpucu** ekler. Daha fazla bilgi için bkz. [araç çubuğu düğmesi için araç ipucu oluşturmak için](#to-create-a-tool-tip-for-a-toolbar-button).|

**Genişlik** ve **Yükseklik** tüm düğmelere uygulanır. Bir araç çubuğu oluşturmak için kullanılan bir bit eşlem en fazla 2048 genişliğine sahiptir. Düğme genişliğini *512*olarak ayarlarsanız yalnızca dört düğme olabilir. Genişliği *513*olarak ayarlarsanız yalnızca üç düğme olabilir.

## <a name="how-to"></a>Nasıl yapılır

**Araç Çubuğu Düzenleyicisi** şunları yapmanızı mümkün:

### <a name="to-create-new-toolbars"></a>Yeni araç çubukları oluşturmak için

1. **Kaynak görünümü**, *. RC* dosyanıza sağ tıklayıp **Kaynak Ekle**' yi seçin. *. RC* dosyanızda mevcut bir araç çubuğağınız varsa, **araç** çubuğu klasörüne sağ tıklayıp **Ekle araç çubuğu**' nu seçebilirsiniz.

1. **Kaynak Ekle** Iletişim kutusunda **kaynak türü** listesinden **araç çubuğu** ' nu seçin ve ardından **Yeni**' yi seçin.

   **+** **Araç çubuğu** kaynak türünün yanında bir artı işareti () görünürse, araç çubuğu şablonlarının kullanılabildiği anlamına gelir. Şablon listesini genişletmek için artı işaretini seçin, bir şablon seçin ve **Yeni**' yi seçin.

### <a name="to-convert-bitmaps-to-toolbar-resources"></a>Bit eşlemleri araç çubuğu kaynaklarına dönüştürmek için

1. [Görüntü düzenleyicisinde](../windows/image-editor-for-icons.md)varolan bir bit eşlem kaynağını açın. Bit eşlem zaten *. RC* dosyanızda yoksa, *. RC* dosyasına sağ tıklayın ve **içeri aktar**' ı seçin. Ardından, *. RC* dosyanıza eklemek istediğiniz bit eşlem 'e gidin ve **Aç**' ı seçin.

1. Menü **resmi**  >  **Araç Çubuğu Düzenleyicisi**' ne gidin.

   **Yeni araç çubuğu kaynağı** iletişim kutusu görüntülenir. Simge görüntülerinin genişliğini ve yüksekliğini bit eşlemle eşleşecek şekilde değiştirebilirsiniz. Araç çubuğu görüntüsü daha sonra **araç çubuğu düzenleyicisinde**görüntülenir.

1. Dönüştürme işleminin tamamlanabilmesi için, [Özellikler penceresi](/visualstudio/ide/reference/properties-window)kullanarak düğmenin komut **kimliğini** değiştirin. Yeni *kimliği* yazın veya açılan listeden bir **kimlik** seçin.

   > [!TIP]
   > **Özellikler** penceresi, başlık çubuğunda bir raptiye düğmesi içerir ve bu pencere Için **Otomatik gizlemeyi** etkinleştirilir veya devre dışı bırakır. Tek bir özellik pencerelerini yeniden açmak zorunda kalmadan tüm araç çubuğu düğmesi özellikleri arasında geçiş yapmak için, **Özellikler** penceresinin sabit kalmasını sağlamak üzere **otomatik gizleme** ' yi kapatın.

   Ayrıca, yeni araç çubuğundaki düğmelerin komut kimliklerini [Özellikler penceresi](/visualstudio/ide/reference/properties-window)kullanarak değiştirebilirsiniz.

### <a name="to-manage-toolbar-buttons"></a>Araç çubuğu düğmelerini yönetmek için

#### <a name="to-create-a-new-toolbar-button"></a>Yeni bir araç çubuğu düğmesi oluşturmak için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) kaynak klasörünü genişletin (örneğin, *Project1. RC*).

1. **Araç çubuğu** klasörünü genişletin ve düzenlemek için bir araç çubuğu seçin, sonra aşağıdakilerden birini yapın:

   - Araç çubuğunun sağ ucundaki boş düğmeye bir KIMLIK atayın. Bunu, [Özellikler penceresinde](/visualstudio/ide/reference/properties-window) **ID** özelliğini düzenleyerek yapabilirsiniz. Örneğin, bir menü seçeneği olarak aynı KIMLIĞE bir araç çubuğu düğmesi vermek isteyebilirsiniz. Bu durumda, menü seçeneğinin **kimliğini** seçmek için açılan liste kutusunu kullanın.

   - **Araç çubuğu görünüm** bölmesinde araç çubuğunun sağ ucundaki boş düğmesini seçin ve çizim ' i başlatın. Varsayılan düğme komut KIMLIĞI atanır (ID_BUTTON \<n> ).

#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>Bir araç çubuğuna düğme olarak görüntü eklemek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' de, araç çubuğunu çift tıklayarak açın.

1. Ardından, araç çubuğuna eklemek istediğiniz görüntüyü açın.

   > [!NOTE]
   > Görüntüyü Visual Studio 'da açarsanız, **görüntü düzenleyicide**açılır. Görüntüyü diğer grafik programlarında da açabilirsiniz.

1. Menü kopyasını **Düzenle**' ye gidin  >  **Copy**.

1. Kaynak pencerenin üst kısmındaki sekmesini seçerek araç çubuğa geçiş yapın.

1. Menü **Düzenle**  >  **Yapıştır**'a gidin.

   Görüntü, araç çubuğunda yeni bir düğme olarak görünür.

#### <a name="to-move-a-toolbar-button"></a>Bir araç çubuğu düğmesini taşımak için

**Araç çubuğu görünüm** bölmesinde, taşımak istediğiniz düğmeyi araç çubuğunda yeni konumuna sürükleyin.

- Araç çubuğundan düğme kopyalamak için **CTRL** tuşunu basılı tutun. **Araç çubuğu görünüm** bölmesinde, düğmeyi araç çubuğundaki yeni konumuna sürükleyin. Ya da başka bir araç çubuğundaki bir konuma sürükleyin.

- Bir araç çubuğu düğmesini silmek için araç çubuğu düğmesini seçin ve araç çubuğundan sürükleyin.

- Bir araç çubuğundaki düğmeler arasına boşluk eklemek veya kaldırmak için, araç çubuğundaki ya da birbirlerine doğru sürükleyin.

|Eylem|Adım|
|------|------|
|Arkasından bir boşluk gelen bir düğmeden önce boşluk eklemek için|Alt yarısında ilgili sonraki düğmeyle örtüşene kadar düğmeyi sağa veya aşağı sürükleyin.|
|Bir düğmeden önce bir boşluk gelen ve sondaki boşluğu tutan bir düğmeden önce boşluk eklemek için|Sağ veya alt kenar, ileri düğmesine dokunana kadar veya yalnızca onunla örtüşene kadar düğmeyi sürükleyin.|
|Bir düğmeden önce bir boşluk gelen bir boşluk eklemek ve aşağıdaki alanı kapatmak için|Alt yarısında ilgili sonraki düğmeyle örtüşene kadar düğmeyi sağa veya aşağı sürükleyin.|
|Araç çubuğundaki düğmeler arasındaki boşluğu kaldırmak için|Alanın bir tarafındaki düğmeyi seçin. Üst yarısında ilgili sonraki düğmeyle çıkana kadar alanın diğer tarafındaki düğmeye doğru sürükleyin.|

> [!NOTE]
> Düğmenin üzerine sürüklediğiniz bir boşluk yoksa ve düğmeyi bitişik düğmeden daha uzun bir yere sürüklerseniz **Araç Çubuğu Düzenleyicisi** , sürüklediğiniz düğmenin zıt tarafına bir boşluk ekler...

#### <a name="to-change-the-properties-of-a-toolbar-button"></a>Bir araç çubuğu düğmesinin özelliklerini değiştirmek için

1. Bir C++ projesinde araç çubuğu düğmesini seçin.

1. Yeni kimliği [Özellikler penceresinde](/visualstudio/ide/reference/properties-window) **kimlik** özelliğine yazın veya açılan listeyi kullanarak yeni bir **kimlik**seçin.

#### <a name="to-create-a-tool-tip-for-a-toolbar-button"></a>Bir araç çubuğu düğmesi için araç ipucu oluşturmak için

1. Araç çubuğu düğmesini seçin.

1. [Özellikler penceresinde](/visualstudio/ide/reference/properties-window), **istem** alanına, durum çubuğu için bir açıklama ve iletiden sonra `\n` Araç İpucu adı ekleyin.

Örneğin, **WordPad**'de **Yazdır** düğmesine ait araç ipucunu görmek için:

1. **WordPad 'i**açın.

1. Fare işaretçinizi **Yazdır** araç çubuğu düğmesinin üzerine getirin ve Word 'ün `Print` artık fare işaretçiniz altında olduğuna dikkat edin.

1. **WordPad** penceresinin alt kısmındaki durum çubuğuna bakın ve şimdi metni gösterir `Prints the active document` .

`Print` araç ipucu adıdır ve `Prints the active document` durum çubuğu düğmesinin açıklamasıdır.

Bu etkiyi **araç çubuğu düzenleyicisini**kullanarak Istiyorsanız, **Prompt** özelliğini olarak ayarlayın `Prints the active document\nPrint` .

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak düzenleyicileri](../windows/resource-editors.md)\
[Menüler ve diğer kaynaklar](/windows/win32/menurc/resources)
