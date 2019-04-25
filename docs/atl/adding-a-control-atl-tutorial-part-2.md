---
title: Denetim Ekleme (ATL Eğitmeni, Bölüm 2)
ms.custom: get-started-article
ms.date: 09/26/2018
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
ms.openlocfilehash: 45841c33ad30ff427f9b792a779d135b4f6e7eca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223551"
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>Denetim Ekleme (ATL Eğitmeni, Bölüm 2)

Bu adımda, projenize bir denetim ekleyin, derleyin ve bir Web sayfası üzerinde sınarsınız.

## <a name="procedures"></a>Yordamlar

### <a name="to-add-an-object-to-an-atl-project"></a>ATL projesine nesne eklemek için

1. İçinde **Çözüm Gezgini**, sağ `Polygon` proje.

1. İşaret **Ekle** kısayol menüsüne ve ardından şirket **yeni öğe** alt menüsü.

    **Yeni Öğe Ekle** iletişim kutusu görünür. Farlı nesne kategorileri soldaki ağaç yapısında listelenmiştir.

1. Tıklayın **ATL** klasör.

1. Sağdaki şablonlar listesinden seçin **ATL denetimi**. **Ekle**'yi tıklatın. **ATL denetimi** Sihirbazı açılır ve denetimi yapılandırabilirsiniz.

1. Tür `PolyCtl` kısa bir ad ve diğer alanları otomatik olarak tamamlanacağını unutmayın. Tıklamayın **son** henüz, çünkü bazı değişiklikler yapmanız gerekir.

**ATL denetimi** sihirbazın **adları** sayfası aşağıdaki alanları içerir:

|Alan|İçindekiler|
|-----------|--------------|
|**Kısa ad**|Denetim için girdiğiniz ad.|
|**Sınıfı**|Denetimi uygulamak için oluşturulan C++ sınıfı adı.|
|**.h dosyası**|C++ sınıfının tanımını içerecek şekilde oluşturulan dosya.|
|**.cpp dosyası**|C++ sınıfının uygulaması içerecek şekilde oluşturulan dosya.|
|**Coclass'ı**|Bu denetim için bileşen sınıfının adı.|
|**Arabirimi**|Denetimin özel yöntemleri ve özellikleri gerçekleştireceksiniz arabirimin adı.|
|**Tür**|Denetim için bir açıklama.|
|**ProgID**|Denetimin CLSID'sini aramak için kullanılabilecek okunabilir ad.|

Birkaç ek ayarlar yapmanız **ATL denetimi** Sihirbazı.

### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>Zengin hata bilgileri ve bağlantı noktaları desteğini etkinleştirmek için

1. Tıklayın **seçenekleri** açmak için **seçenekleri** sayfası.

1. Seçin **bağlantı noktaları** onay kutusu. Bu IDL dosyasına giden bir arabirim için destek oluşturacaktır.

Denetimin işlevlerini genişletmek için arabirimleri de ekleyebilirsiniz.

### <a name="to-extend-the-controls-functionality"></a>Denetimin işlevlerini genişletmek için

1. Tıklayın **arabirimleri** açmak için **arabirimleri** sayfası.

1. Seçin `IProvideClassInfo2` tıklatıp **yukarı** taşımak için ok **desteklenen** listesi.

1. Seçin `ISpecifyPropertyPages` tıklatıp **yukarı** taşımak için ok **desteklenen** listesi.

Denetimin eklenebilir, Excel veya Word gibi katıştırılmış nesneleri destekleyen uygulamalar içine gömülebilir anlamına gelir de yapabilirsiniz.

### <a name="to-make-the-control-insertable"></a>Denetimin eklenebilir olmasını sağlamak için

1. Tıklayın **Görünüm** açmak için **Görünüm** sayfası.

1. Seçin **Insertable** onay kutusu.

Nesne tarafından görüntülenen çokgenin eklemek zorunda bir dolgu rengi düz olacaktır bir `Fill Color` stok özelliği.

### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>Dolgu rengi stok özelliği eklemek ve denetimi oluşturmak için

1. Tıklayın **stok özellikleri** açmak için **stok özellikleri** sayfası.

1. Altında **desteklenmiyor**, olası stok özellikleri listesinde aşağıya ilerleyin. Seçin `Fill Color` tıklatıp **yukarı** taşımak için ok **desteklenen** listesi.

1. Bu, denetimin seçeneklerini tamamlar. **Son**'a tıklayın.

Sihirbaz denetim oluşturduğunda birtakım kod değişiklikleri ve dosya ekleri oluştu. Aşağıdaki dosyalar oluşturulmuştur:

|Dosya|Açıklama|
|----------|-----------------|
|PolyCtl.h|C++ sınıfının uygulaması çoğunu içeren `CPolyCtl`.|
|PolyCtl.cpp|Kalan bölümlerini içerir `CPolyCtl`.|
|PolyCtl.rgs|Denetimi kaydetmek için kullanılan kayıt betiği içeren bir metin dosyası.|
|Polyctl.htm dosyasını|Yeni oluşturulan denetime başvuru içeren bir Web sayfası.|

Sihirbazı, aşağıdaki kod değişikliklerini de gerçekleştirmiştir:

- Eklenen bir `#include` ATL dahil etmek için stdafx.h ve stdafx.cpp dosyalarına deyimi denetimleri desteklemek için gerekli dosyaları.

- Yeni denetimin ayrıntılarını içerecek şekilde Polygon.idl.

- Polygon.cpp nesne eşlemesine yeni denetim eklendi.

Şimdi nasıl çalıştığını görmek için denetimi yapılandırabilirsiniz.

## <a name="building-and-testing-the-control"></a>Derleme ve denetimini test etme

### <a name="to-build-and-test-the-control"></a>Yapı ve denetim test etmek için

1. Üzerinde **derleme** menüsünde tıklatın **yapı çokgeni**.

    Denetim yapıyı tamamlandıktan sonra polyctl.htm dosyasını sağ tıklatın **Çözüm Gezgini** seçip **tarayıcıda görüntüle**. Denetimi içeren HTML Web sayfası görüntülenir. "PolyCtl nesnesi için ATL 8.0 test sayfası" başlığını ve PolyCtl metin içeren bir sayfa görmeniz gerekir. Bu denetiminizdir.

> [!NOTE]
> Denetim görünür durumda değilse bazı tarayıcılar ayarları düzeltmeleri ActiveX denetimlerini çalıştırmak için gerekli olduğunu bilirsiniz. ActiveX denetimleri etkinleştirme hakkında tarayıcının belgelere bakın.

> [!NOTE]
> DLL dosyasının nerede oluşturulamıyor bir hata iletisi alırsanız, bu öğreticiyi tamamlarken, PolyCtl.htm dosyasını ve ActiveX denetimi Test kapsayıcısını kapatın ve çözümü yeniden oluşturun. DLL'yi yine oluşturamazsanız, bilgisayarı yeniden başlatın veya (Terminal Hizmetleri'ni kullanıyorsanız) oturumu kapatın.

Sonra denetime özel bir özellik ekleyeceksiniz.

[1. adım dön](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [açın 3. adım](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
