---
description: 'Daha fazla bilgi edinin: denetim ekleme (ATL öğreticisi, Bölüm 2)'
title: Denetim Ekleme (ATL Eğitmeni, Bölüm 2)
ms.custom: get-started-article
ms.date: 08/19/2019
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
ms.openlocfilehash: 91e0f6ba4b091b6ca213495fb81727714755c635
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166310"
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>Denetim Ekleme (ATL Eğitmeni, Bölüm 2)

Bu adımda projenize bir denetim ekler, derleyebilir ve bir Web sayfasında test edersiniz.

## <a name="procedures"></a>Yordamlar

### <a name="to-add-an-object-to-an-atl-project"></a>ATL projesine bir nesne eklemek için

1. **Çözüm Gezgini**, projeye sağ tıklayın `Polygon` .

1. Kısayol menüsünde **Ekle** ' nin üzerine gelin ve alt menüdeki **Yeni öğe** ' ye tıklayın.

    **Yeni Öğe Ekle** iletişim kutusu görünür. Farklı nesne kategorileri soldaki ağaç yapısında listelenir.

1. **ATL** klasörünü tıklatın.

1. Sağdaki şablonlar listesinden **ATL denetimi**' ni seçin. **Ekle**'ye tıklayın. **Atl Denetim** Sihirbazı açılır ve denetimi yapılandırabilirsiniz.

1. `PolyCtl`Kısa ad olarak yazın ve diğer alanların otomatik olarak tamamlandığını unutmayın. Daha fazla değişiklik yapmanız gerektiğinden, henüz **son** ' a tıklamayın.

**Atl Denetim** Sihirbazı 'nın **adlar** sayfası aşağıdaki alanları içerir:

|Alan|İçindekiler|
|-----------|--------------|
|**Kısa ad**|Denetim için girdiğiniz ad.|
|**Sınıf**|Denetimi uygulamak için oluşturulan C++ sınıf adı.|
|**. h dosyası**|C++ sınıfının tanımını içerecek şekilde oluşturulan dosya.|
|**. cpp dosyası**|C++ sınıfının uygulamasını içerecek şekilde oluşturulan dosya.|
|**CoClass**|Bu denetim için bileşen sınıfının adı.|
|**Arabirim**|Denetimin özel yöntemlerini ve özelliklerini uygulayamayacağı arabirimin adı.|
|**Tür**|Denetim için bir açıklama.|
|**ProgID**|Denetimin CLSID 'sini aramak için kullanılabilecek okunabilir ad.|

**Atl Denetim** Sihirbazı 'nda birkaç ek ayar değiştirilmesi gerektiğini göreceksiniz.

### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>Zengin hata bilgileri ve bağlantı noktaları desteğini etkinleştirmek için

1. **Seçenekler sayfasını açmak** için **Seçenekler** ' e tıklayın.

1. **Bağlantı noktaları** onay kutusunu seçin. Bu seçenek, IDL dosyasındaki bir giden arabirim için destek oluşturur.

Ayrıca denetim işlevlerini genişletmek için arabirimler ekleyebilirsiniz.

### <a name="to-extend-the-controls-functionality"></a>Denetimin işlevselliğini genişletmek için

1. **Arabirimler sayfasını açmak** için **arabirimler** ' e tıklayın.

1. `IProvideClassInfo2` **Yukarı** oku seçin ve **desteklenen** listeye taşımak için yukarı okuna tıklayın.

1. `ISpecifyPropertyPages` **Yukarı** oku seçin ve **desteklenen** listeye taşımak için yukarı okuna tıklayın.

Ayrıca, denetimin *eklenebilir* olmasını sağlayabilirsiniz, bu da Excel veya Word gibi katıştırılmış nesneleri destekleyen uygulamalara katıştırılır.

### <a name="to-make-the-control-insertable"></a>Denetimi eklenebilir hale getirmek için

1. **Görünüm sayfasını açmak** için **Görünüm** ' e tıklayın.

1. **Insertable** onay kutusunu seçin.

Nesne tarafından görünen Çokgen düz bir Fill rengine sahip olacaktır, bu nedenle bir `Fill Color` Stok özelliği eklemeniz gerekir.

### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>Bir doldur rengi stok özelliği eklemek ve denetimi oluşturmak için

1. Hisse **senedi özellikleri sayfasını açmak** Için **Stok özellikleri** ' ne tıklayın.

1. **Desteklenmediğinden**, olası stok özellikleri listesini aşağı kaydırın. `Fill Color` **Yukarı** oku seçin ve **desteklenen** listeye taşımak için yukarı okuna tıklayın.

1. **Son**’u seçin.

Sihirbaz denetimi oluşturduğunda, birkaç kod değişikliği ve dosya eklemeleri oluşur. Aşağıdaki dosyalar oluşturulur:

|Dosya|Açıklama|
|----------|-----------------|
|PolyCtl. h|C++ sınıfının uygulamanın çoğunu içerir `CPolyCtl` .|
|PolyCtl. cpp|Öğesinin kalan bölümlerini içerir `CPolyCtl` .|
|PolyCtl. rgs|Denetimi kaydetmek için kullanılan kayıt defteri betiğini içeren bir metin dosyası.|
|PolyCtl.htm|Yeni oluşturulan denetime başvuru içeren bir Web sayfası.|

Sihirbaz ayrıca aşağıdaki kod değişikliklerini yapar:

- `#include`Denetimleri desteklemek için gereken ATL dosyalarını dahil etmek için önceden derlenmiş üstbilgi dosyalarına bir ifade ekler.

- Yeni denetimin ayrıntılarını dahil etmek için Çokgen. IDL ' i değiştirir.

- Çokgen. cpp içindeki nesne eşlemesine yeni denetim ekler.

Artık bu denetimi bir eylemde görmek için oluşturabilirsiniz.

## <a name="building-and-testing-the-control"></a>Denetim oluşturma ve test etme

### <a name="to-build-and-test-the-control"></a>Denetimi derlemek ve test etmek için

1. **Yapı** menüsünde, **Yapı Çokgen**' e tıklayın.

    Denetim, oluşturmayı tamamladıktan sonra **Çözüm Gezgini** PolyCtl.htm sağ tıklayıp **Tarayıcıda görüntüle**' yi seçin. Denetimi içeren HTML Web sayfası görüntülenir. "PolyCtl nesnesi için ATL 8,0 test sayfası" başlığına ve denetiminiz, PolyCtl metin başlıklı bir sayfa görmeniz gerekir.

> [!NOTE]
> Denetim görünür değilse, bazı tarayıcıların ActiveX denetimlerini çalıştırmak için ayar ayarlamaları gerektirdiğini öğrenin. ActiveX denetimlerinin nasıl etkinleştirileceği hakkında daha fazla bilgi için tarayıcıya bakın.

> [!NOTE]
> Bu öğreticiyi tamamlarken, DLL dosyasının oluşturuolamayacağını belirten bir hata iletisi alırsanız, PolyCtl.htm dosyasını ve ActiveX denetimi test kapsayıcısını kapatın ve çözümü yeniden derleyin. Hala DLL 'yi oluşturamıyoruz, bilgisayarı yeniden başlatın veya Terminal Hizmetleri kullanıyorsanız oturumu kapatın.

Sonra, denetime özel bir özellik ekleyeceksiniz.

Adım [1 ' e geri döndüğünüzde](../atl/creating-the-project-atl-tutorial-part-1.md) [3. adım](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124;

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
