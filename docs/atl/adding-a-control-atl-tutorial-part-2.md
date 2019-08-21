---
title: Denetim Ekleme (ATL Eğitmeni, Bölüm 2)
ms.custom: get-started-article
ms.date: 08/19/2019
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
ms.openlocfilehash: b7952f42b24c4211a2c44ea71fd17e4f65c3421a
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630707"
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>Denetim Ekleme (ATL Eğitmeni, Bölüm 2)

Bu adımda projenize bir denetim ekler, derleyebilir ve bir Web sayfasında test edersiniz.

## <a name="procedures"></a>Yordamlar

### <a name="to-add-an-object-to-an-atl-project"></a>ATL projesine bir nesne eklemek için

1. **Çözüm Gezgini**, `Polygon` projeye sağ tıklayın.

1. Kısayol menüsünde **Ekle** ' nin üzerine gelin ve alt menüdeki **Yeni öğe** ' ye tıklayın.

    **Yeni Öğe Ekle** iletişim kutusu görünür. Farklı nesne kategorileri soldaki ağaç yapısında listelenir.

1. **ATL** klasörünü tıklatın.

1. Sağdaki şablonlar listesinden **ATL denetimi**' ni seçin. **Ekle**'yi tıklatın. **Atl Denetim** Sihirbazı açılır ve denetimi yapılandırabilirsiniz.

1. Kısa `PolyCtl` ad olarak yazın ve diğer alanların otomatik olarak tamamlandığını unutmayın. Daha fazla değişiklik yapmanız gerektiğinden, henüz **son** ' a tıklamayın.

**Atl Denetim** Sihirbazı 'nın **adlar** sayfası aşağıdaki alanları içerir:

|Alan|İçindekiler|
|-----------|--------------|
|**Kısa ad**|Denetim için girdiğiniz ad.|
|**Sınıfı**|Denetimi C++ uygulamak için oluşturulan sınıf adı.|
|**. h dosyası**|C++ Sınıfının tanımını içerecek şekilde oluşturulan dosya.|
|**. cpp dosyası**|C++ Sınıfının uygulamasını içerecek şekilde oluşturulan dosya.|
|**CoClass**|Bu denetim için bileşen sınıfının adı.|
|**Arabirimi**|Denetimin özel yöntemlerini ve özelliklerini uygulayamayacağı arabirimin adı.|
|**Tür**|Denetim için bir açıklama.|
|**ProgID**|Denetimin CLSID 'sini aramak için kullanılabilecek okunabilir ad.|

**Atl Denetim** Sihirbazı 'nda birkaç ek ayar değiştirilmesi gerektiğini göreceksiniz.

### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>Zengin hata bilgileri ve bağlantı noktaları desteğini etkinleştirmek için

1. Seçenekler sayfasını açmak için **Seçenekler** ' e tıklayın.

1. **Bağlantı noktaları** onay kutusunu seçin. Bu seçenek, IDL dosyasındaki bir giden arabirim için destek oluşturur.

Ayrıca denetim işlevlerini genişletmek için arabirimler ekleyebilirsiniz.

### <a name="to-extend-the-controls-functionality"></a>Denetimin işlevselliğini genişletmek için

1. Arabirimler sayfasını açmak için **arabirimler** ' e tıklayın.

1. Yukarı `IProvideClassInfo2` oku seçin ve **desteklenen** listeye taşımak için **yukarı** okuna tıklayın.

1. Yukarı `ISpecifyPropertyPages` oku seçin ve **desteklenen** listeye taşımak için **yukarı** okuna tıklayın.

Ayrıca, denetimin *eklenebilir*olmasını sağlayabilirsiniz, bu da Excel veya Word gibi katıştırılmış nesneleri destekleyen uygulamalara katıştırılır.

### <a name="to-make-the-control-insertable"></a>Denetimi eklenebilir hale getirmek için

1. Görünüm sayfasını açmak için **Görünüm** ' e tıklayın.

1. **Insertable** onay kutusunu seçin.

Nesne tarafından görünen Çokgen düz bir Fill rengine sahip olacaktır, bu nedenle bir `Fill Color` stok özelliği eklemeniz gerekir.

### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>Bir doldur rengi stok özelliği eklemek ve denetimi oluşturmak için

1. Hisse senedi özellikleri sayfasını açmak için **Stok özellikleri** ' ne tıklayın.

1. **Desteklenmediğinden**, olası stok özellikleri listesini aşağı kaydırın. Yukarı `Fill Color` oku seçin ve **desteklenen** listeye taşımak için **yukarı** okuna tıklayın.

1. Seçin **son**.

Sihirbaz denetimi oluşturduğunda, birkaç kod değişikliği ve dosya eklemeleri oluşur. Aşağıdaki dosyalar oluşturulur:

|Dosya|Açıklama|
|----------|-----------------|
|PolyCtl. h|C++ Sınıfının`CPolyCtl`uygulamanın çoğunu içerir.|
|PolyCtl. cpp|Öğesinin `CPolyCtl`kalan bölümlerini içerir.|
|PolyCtl.rgs|Denetimi kaydetmek için kullanılan kayıt defteri betiğini içeren bir metin dosyası.|
|PolyCtl. htm|Yeni oluşturulan denetime başvuru içeren bir Web sayfası.|

Sihirbaz ayrıca aşağıdaki kod değişikliklerini yapar:

- Denetimleri desteklemek `#include` için gereken ATL dosyalarını dahil etmek için önceden derlenmiş üstbilgi dosyalarına bir ifade ekler.

- Yeni denetimin ayrıntılarını dahil etmek için Çokgen. IDL ' i değiştirir.

- Çokgen. cpp içindeki nesne eşlemesine yeni denetim ekler.

Artık bu denetimi bir eylemde görmek için oluşturabilirsiniz.

## <a name="building-and-testing-the-control"></a>Denetim oluşturma ve test etme

### <a name="to-build-and-test-the-control"></a>Denetimi derlemek ve test etmek için

1. **Yapı** menüsünde, **Yapı Çokgen**' e tıklayın.

    Denetim oluşturmayı tamamladıktan sonra, **Çözüm Gezgini** Içinde PolyCtl. htm dosyasına sağ tıklayın ve **Tarayıcıda görüntüle**' yi seçin. Denetimi içeren HTML Web sayfası görüntülenir. "PolyCtl nesnesi için ATL 8,0 test sayfası" başlığına ve denetiminiz, PolyCtl metin başlıklı bir sayfa görmeniz gerekir.

> [!NOTE]
> Denetim görünür değilse, bazı tarayıcıların ActiveX denetimlerini çalıştırmak için ayar ayarlamaları gerektirdiğini öğrenin. ActiveX denetimlerinin nasıl etkinleştirileceği hakkında daha fazla bilgi için tarayıcıya bakın.

> [!NOTE]
> Bu öğreticiyi tamamlarken, DLL dosyasının oluşturuolamayacağını belirten bir hata iletisi alırsanız, PolyCtl. htm dosyasını ve ActiveX denetimi test kapsayıcısını kapatın ve çözümü yeniden derleyin. Hala DLL 'yi oluşturamıyoruz, bilgisayarı yeniden başlatın veya Terminal Hizmetleri kullanıyorsanız oturumu kapatın.

Sonra, denetime özel bir özellik ekleyeceksiniz.

[1. adıma dön](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [Adım 3 ' e](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
