---
title: Oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.toolbar
helpviewer_keywords:
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
ms.assetid: d0f0c6c6-9d7e-42b5-a86a-7558127386e7
ms.openlocfilehash: 2a67123e444ad208eaae74a24b72288f2dbb3bdb
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742706"
---
# <a name="creating-moving-and-editing-toolbar-buttons-c"></a>Oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri (C++)

Kolayca oluşturun, taşıma kopyalayın ve araç çubuğu düğmeleri Düzenle.

Varsayılan olarak, araç çubuğunun sağ ucuna yeni ya da boş bir düğme görüntülenir. Bu düğme düzenlemeden önce taşıyabilirsiniz. Yeni bir düğme oluşturduğunuzda, başka bir boş düğme düzenlenen düğmesinin sağında görüntülenir. Araç çubuğu kaydettiğinizde, boş düğme kaydedilmez.

Araç çubuğu düğmesi özellikleri şunlardır:

|Özellik|Açıklama|
|--------------|-----------------|
|**ID**|Düğme için kimliği tanımlar. Açılır listede ortak sağlar **kimliği** adları.|
|**Genişlik**|Düğmesinin genişliğini belirler. 16 piksel önerilir.|
|**Yükseklik**|Düğmenin yüksekliğini belirler. Bir düğme yüksekliğini, araç çubuğundaki tüm düğmeler yüksekliğini değiştirir. 15 piksel önerilir.|
|**Sor**|Durum çubuğunda görüntülenen ileti tanımlar. Bir araç ipucu \n ve bir ad eklemek için bu araç çubuğu düğmesini ekler. Daha fazla bilgi için [bir araç ipucu oluşturmanın](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|

**Genişlik** ve **yükseklik** tüm düğmeler için geçerlidir. Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048 maksimum genişliği sahiptir. Bu nedenle düğme genişliği 512 ayarlarsanız, yalnızca dört düğme olabilir ve genişliği için 513 ayarlarsanız, yalnızca üç düğme olabilir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

Aşağıdaki eylemleri bakın:

## <a name="to-create-a-new-toolbar-button"></a>Yeni araç çubuğu düğmesi oluşturma

1. İçinde [kaynak görünümü](../windows/resource-view-window.md) kaynak klasörünü genişletin (örneğin, *Project1.rc*).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. Genişletin **araç** klasörü ve düzenlemek için bir araç çubuğunu seçin.

1. Boş düğme araç çubuğunun sağ ucunda bir kimliği atayın. Düzenleyerek bunu yapabilirsiniz **kimliği** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Örneğin, aynı menü seçeneği Kimliğine araç çubuğu düğmesi vermek isteyebilirsiniz. Bu durumda, seçmek için aşağı açılan liste kutusunu kullanın **kimliği** menü seçeneğinin.

   -veya-

   Araç çubuğunun sağ ucunda boş düğmeyi seçin (içinde **araç çubuğu görünümü** bölmesinde) ve çizim başlayın. Varsayılan düğme komut kimliği atanır (ID_BUTTON\<n >).

Ayrıca, kopyalayın ve bir görüntüyü yeni bir düğme olarak bir araç çubuğu üzerine yapıştırın.

## <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>Görüntüyü bir araç çubuğuna bir düğme olarak eklemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), araç çift tıklayarak açın.

1. Ardından, araç için eklemek istediğiniz görüntü açın.

   > [!NOTE]
   > Görüntüyü Visual Studio'da açın, içinde açılır **görüntü** Düzenleyici. Diğer grafik programında görüntü de açabilirsiniz.

1. Gelen **Düzenle** menüsünde seçin **kopyalama**.

1. Kaynak pencerenin üst kısmındaki sekmesini seçerek, araç çubuğu'na geçin.

1. Gelen **Düzenle** menüsünde seçin **Yapıştır**.

   Görüntü, araç çubuğunda yeni bir düğme olarak görünür.

## <a name="to-move-a-toolbar-button"></a>Araç çubuğu düğmesini taşıma

İçinde **araç çubuğu görünümü** bölmesinde, araç çubuğunda yeni konumuna taşımak istediğiniz düğme sürükleyin.

## <a name="to-copy-buttons-from-a-toolbar"></a>Araç çubuğundan düğme kopyalama

1. Basılı **Ctrl** anahtarı.

1. İçinde **araç çubuğu görünümü** bölmesi, düğmeyi ya da yeni konumuna araç çubuğunda veya bir konuma başka bir araç sürükleyin.

## <a name="to-delete-a-toolbar-button"></a>Araç çubuğu düğmesi silme

Araç çubuğu düğmesini seçin ve araç çubuğundan sürükleyin.

## <a name="to-insert-or-remove-space-between-buttons-on-a-toolbar"></a>Ekleme veya araç çubuğundaki düğmeler arasındaki boşluğu kaldırma

Genel olarak, düğmeler arasına boşluk eklemek için bunları başka uzağa araç sürükleyin. Alanı kaldırmak için bunları birbirine doğru sürükleyin.

### <a name="to-insert-a-space-before-a-button-that-isnt-followed-by-a-space"></a>Ardından bir boşluk olmayan bir düğme öncesinde bir boşluk eklemek için

İleri düğmesine hakkında yarı yarıya çakışıyor kadar aşağı ya da sağ düğme sürükleyin.

### <a name="to-insert-a-space-before-a-button-that-is-followed-by-a-space-and-to-keep-the-trailing-space"></a>Sondaki boşluğu bulundurmanız gereken ve ardından bir boşluk bir düğme önce boşluk Ekle

Düğmeyi kadar sağa sürükleyin veya alt kenarı yalnızca İleri düğmesine oncollisionstay veya yalnızca çakışıyor.

### <a name="to-insert-a-space-before-a-button-that-is-followed-by-a-space-and-close-up-that-following-space"></a>Ardından bir boşluk bir düğme önce bir boşluk ekleyin ve aşağıdaki söz konusu alanı kapatmak için

İleri düğmesine hakkında yarı yarıya çakışıyor kadar aşağı ya da sağ düğme sürükleyin.

### <a name="to-remove-a-space-between-buttons-on-a-toolbar"></a>Araç çubuğundaki düğmeler arasına boşluk kaldırmak için

Kadar olan sürenin yarısına ulaşıldığında hakkında İleri düğmesine çakışıyor düğmeyi bir düğmeyi diğer tarafta doğru alanı alanı tarafında sürükleyin.

   Liste kutusundan sürükleyerek düğmeyi kenarındaki boşluk olmaması ve düğmeyi birden fazla bitişik düğmesi, son yarısı sürükleyin **araç** Düzenleyicisi de ters tarafında boşluk çeken düğmenin ekler sürükleme.

## <a name="to-change-the-properties-of-a-toolbar-button"></a>Araç çubuğu düğmesi özelliklerini değiştirme

1. Bir C++ projesinde araç çubuğu düğmesini seçin.

1. İçinde yeni kimlik yazın **kimliği** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), ya da yeni bir seçmek için açılan listeyi kullanın **kimliği**.

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)
