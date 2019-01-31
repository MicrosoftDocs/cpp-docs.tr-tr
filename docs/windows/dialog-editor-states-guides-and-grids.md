---
title: İletişim kutusu Düzenleyicisi durumları (Kılavuzlar ve Izgaralar) (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Dialog Editor [C++], guides and margins
- guides, clearing
- guides
- dialog box controls [C++], placement
- controls [C++], guides and margins
- guides, creating
- guides, moving
- margins, moving
- DLUs (dialog units)
- controls [C++], aligning
- Dialog Editor [C++], snap to guides
- guides, tick mark interval
- dialog box controls [C++], placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
- guides, disabling snapping
- controls [C++], snap to guides/grid
- controls [C++], layout grid
- snap to layout grid
- grids, turning on or off
- layout grid in Dialog Editor
- grids, changing size
- grid spacing
- guides, settings
- layout grid in Dialog Editor
- controls [C++], snap to guides/grid
- Guide Settings dialog box (Dialog editor)
ms.assetid: dbacf9ef-e8b0-4125-a7ce-84911c482e98
ms.openlocfilehash: 52fc19d8a39680c16692177e2758fba78afc7d3a
ms.sourcegitcommit: 5270117dbecc4c49bca0cf10b927bae3c9930038
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/31/2019
ms.locfileid: "55485000"
---
# <a name="dialog-editor-states-guides-and-grids-c"></a>İletişim kutusu Düzenleyicisi durumları (Kılavuzlar ve Izgaralar) (C++)

Denetimler ile iletişim kutularında düzenleyebilirsiniz **iletişim** farklı üç durumdan birine düzenleyicisinde:

- Kılavuzlar ve kenar boşlukları (varsayılan ayar) ile

- İçeren düzen kılavuz

- Herhangi bir yaslama veya hizalama özellik

[İletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md) durumunu denetle düğmeleri içerir. Durumu değiştirmek için ilgili simgeye tıklayın. Durumları kullanarak da değiştirebilirsiniz **Kılavuz ayarları** komutunu **biçimi** menüsü.

**Kılavuz ayarları** iletişim kutusunda, aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---|
|**Düzen kılavuzları**|Düzen kılavuzları ayarlarını görüntüler.|
|**Yok.**|Düzen Araçları gizler.|
|**Cetveller ve Kılavuzlar**|Etkin olduğunda, düzeni araçları Cetveller ekler; kılavuzları cetvellerin yerleştirilebilir. Varsayılan sürükleyerek taşınabilir kenar boşluklarını kılavuzlardır. Bir kılavuz yerleştirmek için cetvellerden seçin. "Denetimleri üzerinden veya bunların yanındaki taşındığında denetimleri Kılavuzlara Daya". Kendisine bağlı sonra denetimleri ile bir kılavuz da taşıyın. Her iki taraftaki bir kılavuz bir denetimin ekli olduğu ve bir kılavuz taşınır, denetimi yeniden boyutlandırır.|
|**Kılavuz**|Düzen kılavuzunu oluşturur. Yeni denetimler kılavuza otomatik olarak uyum sağlar.|
|**Kılavuz aralığı**|Kılavuz aralığı Ayarları iletişim kutusu birimleri (Dlu'lar) görüntüler.|
|**Genişlik: Dlu'lar**|Düzen kılavuzunu genişliğini Dlu'lar ayarlar. Yatay DLU dört tarafından ayrılmış iletişim kutusu yazı tipinin ortalama genişliğidir.|
|**Yükseklik: Dlu'lar**|Düzen kılavuzunu yüksekliğini Dlu'lar ayarlar. Dikey DLU sekiz tarafından ayrılmış iletişim kutusu yazı tipi ortalama yüksekliği olur.|

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="create-and-set-guides-and-margins"></a>Kılavuzlar ve kenar boşlukları oluşturma ve

Denetimleri ekleme denetimleri, Taşımakta olduğunuz ya da geçerli düzenini yeniden düzenleme, kılavuzları yardımcı olabilecek bir iletişim kutusu içinde doğru bir şekilde denetimleri hizalayın. Kılavuzlar arasında Düzenleyicisi'ni ve karşılık gelen okları Cetveller üst ve sol tarafında görüntülenen iletişim kutusunda olarak mavi noktalı çizgilerin görünür **iletişim** Düzenleyici.

Bir iletişim kutusu oluşturduğunuzda, dört kenar boşlukları sağlanır. Kenar boşlukları, mavi noktalı çizgiler olarak görünen, değiştirilen kılavuzlardır.

### <a name="to-create-a-guide"></a>Bir kılavuz oluşturmak için

Cetvel içinde bir kılavuz oluşturmak için bir kez tıklayın. (Tek bir tıklamayla oluşturur, yeni bir kılavuzu; başlatır çift **Kılavuz ayarları** içinde belirtebilirsiniz kılavuz Ayarları iletişim kutusu.)

### <a name="to-set-a-guide"></a>Bir kılavuz ayarlamak için

İletişim kutusunda, Kılavuzu'nu tıklatın ve yeni bir konuma sürükleyin. (Ayrıca ilişkili Kılavuzu sürüklemek için cetvelin oka tıklayabilirsiniz.)

Kılavuzu koordinatlarını cetvel ve pencerenin altındaki durum çubuğunda görüntülenir. Tam Kılavuzu konumunu görüntülemek için cetvelin oka üzerine getirin.

### <a name="to-delete-a-guide"></a>Bir kılavuz silmek için

İletişim kutusunu kılavuzu sürükleyin.

\- veya -

Cetvelin karşılık gelen oku sürükleyin.

### <a name="to-move-margins"></a>Kenar boşlukları taşımak için

Kenar boşluğu yeni konumuna sürükleyin.

Bir kenar boşluğu kaybolmasını sağlamak için kenar sıfır bir konuma taşıyın. Kenar boşluğu geri getirmek için işaretçiyi kenar ait sıfır konumuna getirin ve kenar boşluğu konumuna taşıyın.

## <a name="align-controls-on-a-guide"></a>Kılavuzdaki denetimleri hizalama

Boyutlandırma denetimleri denetimleri taşınır ve daha önce Kılavuzu yaslanmış denetimler yoksa kılavuzları denetimlere Yasla Kılavuzlara Daya. Bir kılavuz taşındığında, kendisine tutturulduğunu denetimleri de taşıyın. Bir kılavuz taşındığında birden fazla Kılavuzu yaslanmış denetimleri yeniden boyutlandırılır.

Değer çizgilerinin kılavuzları ve denetimlerin aralığı belirlemek Cetveller içinde iletişim kutusu birimleri (Dlu'lar) tarafından tanımlanır. Bir DLU iletişim kutusu yazı tipi, normalde 8 noktası MS Shell Dlg boyutuna bağlıdır. Yatay DLU dört tarafından ayrılmış iletişim kutusu yazı tipinin ortalama genişliğidir. Dikey DLU sekiz tarafından ayrılmış yazı tipi ortalama yüksekliği olur.

### <a name="to-size-a-group-of-controls-with-guides"></a>Denetim grubunun kılavuzlarıyla boyutlandırmak için

1. Denetimin (veya denetimleri) bir tarafı bir kılavuza yapışır.

1. Diğer tarafında denetimin (veya denetimleri) için bir kılavuz sürükleyin.

   Gerekirse birden çok denetimlerle her ikinci kılavuza uydurmayı boyutu.

1. Denetimin (veya denetimleri) boyutlandırmak için iki Kılavuzu taşıyın.

### <a name="to-change-the-intervals-of-the-tick-marks"></a>Değer çizgilerinin aralıklarına değiştirmek için

1. Gelen **biçimi** menüsünde seçin **Kılavuz ayarları**.

1. İçinde **Kılavuz ayarları** iletişim kutusundaki **ızgara Aralama** alanında, yeni genişliği ve yüksekliği içinde Dlu'lar belirtin.

## <a name="disable-guides"></a>Kılavuzları devre dışı bırak

Özel anahtarları Yaslanma etkisini kılavuzları devre dışı bırakmak için fare ile birlikte kullanabilirsiniz. Kullanarak **Alt** anahtarı, seçilen Kılavuzu Yaslanma etkilerini devre dışı bırakır. Taşıma Kılavuzu ile **Shift** anahtar yaslanan denetimlerin kılavuzla taşınmasını engeller.

### <a name="to-disable-the-snapping-effect-of-the-guides"></a>Yaslanma etkisini kılavuzları devre dışı bırakmak için

Tutarken denetimi sürükleyin **Alt** anahtarı.

### <a name="to-move-guides-without-moving-the-snapped-controls"></a>Yaslanan denetimlerin taşımadan kılavuzları taşımak için

Tutarken kılavuzu sürükleyin **Shift** anahtarı.

### <a name="to-turn-off-the-guides"></a>Kılavuzları için

1. Gelen **biçimi** menüsünde seçin **Kılavuz ayarları**.

1. İçinde **Kılavuz ayarları** iletişim kutusunun **düzeni kılavuzları**seçin **hiçbiri**.

   > [!NOTE]
   > Ayrıca cetvel çubuğuna erişmek için çift **Kılavuz ayarları** iletişim kutusu.

\- veya -

Üzerinde **biçimi** menüsünde **rehberi Aç/Kapat**.

## <a name="modify-the-layout-grid"></a>Düzen kılavuzunu değiştirme

Yerleştirme ya da iletişim kutusunda denetimleri düzenleme için daha kesin konumlandırma Düzen kılavuzunu kullanabilirsiniz. Kılavuz açıldığında, "için kılavuz noktalı satırlarını manyetik hale getirme gibi ek bileşen için" denetimleri görünür. Bu "kılavuz çizgilerinde" özelliğini açıp kapatmak ve Düzen kılavuz hücreleri boyutunu değiştirin.

### <a name="to-turn-the-layout-grid-on-or-off"></a>Düzen kılavuzunu açıp kapatmak için

1. Gelen **biçimi** menüsünde seçin **Kılavuz ayarları**.

1. İçinde **Kılavuz ayarları** iletişim kutusu, seçin veya temizleyin **kılavuz** düğmesi.

   Tek tek kılavuz yine de denetleyebilirsiniz **iletişim** Düzenleyici pencerelerini kullanarak **Kılavuzu Aç/Kapat** düğmesini [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

### <a name="to-change-the-size-of-the-layout-grid"></a>Düzen kılavuzunu boyutunu değiştirmek için

1. Gelen **biçimi** menüsünde seçin **Kılavuz ayarları**.

1. İçinde **Kılavuz ayarları** iletişim yükseklik ve genişlik kılavuzdaki hücreleri Dlu'lar içinde yazın. Minimum yükseklik veya genişlik 4 Dlu'lar ' dir. Dlu'lar hakkında daha fazla bilgi için bkz. [denetimleri düzenleme iletişim kutularında](../windows/arrangement-of-controls-on-dialog-boxes.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler (MFC)](../mfc/controls-mfc.md)<br/>
