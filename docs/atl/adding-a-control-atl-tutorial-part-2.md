---
title: Denetim (ATL Eğitmeni, bölüm 2) ekleme | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3b8c7eb59579363ce3580c7319b80be2557a30d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>Denetim Ekleme (ATL Eğitmeni, Bölüm 2)
Bu adımda, Denetim projenize ekleme, onu oluşturmak ve bir Web sayfasında test.  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-add-an-object-to-an-atl-project"></a>ATL projesinde bir nesne eklemek için  
  
1.  Sınıf Görünümü'nde Çokgen projesine sağ tıklayın.  
  
2.  İşaret **Ekle** kısayol menüsüne ve ardından üzerinde **yeni öğe** alt menüsünde.  
  
     **Yeni Öğe Ekle** iletişim kutusu görüntülenir. Farklı nesne kategoriler, soldaki ağaç yapısındaki listelenir.  
  
3.  Tıklatın **ATL** klasör.  
  
4.  Sağdaki şablonları listesinden seçin **ATL Denetim**. **Ekle**'yi tıklatın. ATL Denetim Sihirbazı'nı açın ve denetimi yapılandırabilirsiniz.  
  
5.  Tür `PolyCtl` kısa bir ad ve Not diğer alanlar otomatik olarak doldurulur. ' A tıklamayın **son** henüz, çünkü bazı değişiklikler yapmak zorunda.  
  
 ATL Denetim sihirbazın **adları** sayfası aşağıdaki alanları içerir:  
  
|Alan|İçindekiler|  
|-----------|--------------|  
|**Kısa ad**|Denetim için girdiğiniz adı.|  
|**sınıfı**|Denetimi için oluşturulan C++ sınıf adı.|  
|**.h dosyası**|C++ sınıfının tanımını içerecek şekilde oluşturulan dosya.|  
|**.cpp dosyası**|C++ sınıfı uyarlamasını içeren için oluşturulan dosya.|  
|**Coclass'ı**|Bu denetim için bileşen sınıfı adı.|  
|**Arabirimi**|Denetim özel yöntemleri ve özellikleri gerçekleştireceksiniz arabirimi adı.|  
|**Türü**|Denetim için bir açıklama.|  
|**ProgID**|Denetim CLSID aramak için kullanılan okunabilir adı.|  
  
 ATL Denetim Sihirbazı'nda birkaç ek ayarlar yapmak zorunda.  
  
#### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>Zengin hata bilgileri ve bağlantı noktaları desteğini etkinleştirmek için  
  
1.  Tıklatın **seçenekleri** açmak için **seçenekleri** sayfası.  
  
2.  Seçin **bağlantı noktaları** onay kutusu. Bu, giden bir arabirim için destek IDL dosyasında oluşturur.  
  
 Belirten gösterge, Excel veya Word gibi katıştırılmış nesneler destekleyen uygulamalara katıştırılabilen anlamına gelir denetimi de yapabilirsiniz.  
  
#### <a name="to-make-the-control-insertable"></a>Denetim belirten gösterge yapma  
  
1.  Tıklatın **Görünüm** açmak için **Görünüm** sayfa.  
  
2.  Seçin **Insertable** onay kutusu.  
  
 Böylece eklemek zorunda nesne tarafından görüntülenen Çokgen bir düz dolgu rengi olacaktır bir `Fill Color` stok özellik.  
  
#### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>Dolgu rengi stok özellik ekleme ve denetimi oluşturmak için  
  
1.  Tıklatın **hisse senedi özellikleri** açmak için **hisse senedi özellikleri** sayfası.  
  
2.  Altında **desteklenmiyor**, olası stok özellikler listesini aşağı kaydırın. Çift `Fill Color` taşımak için kendisine **desteklenen** listesi.  
  
3.  Bu denetim için seçenekleri tamamlar. **Son**'a tıklayın.  
  
 Sihirbaz Denetimi oluşturulan gibi birkaç kod değişikliklerini ve dosya ekleri oluştu. Aşağıdaki dosyalar oluşturuldu:  
  
|Dosya|Açıklama|  
|----------|-----------------|  
|PolyCtl.h|C++ sınıfı uyarlamasını çoğunu içeren `CPolyCtl`.|  
|PolyCtl.cpp|Kalan bölümleri içeren `CPolyCtl`.|  
|PolyCtl.rgs|Denetim kaydetmek için kullanılan kayıt defteri komut dosyasını içeren bir metin dosyası.|  
|PolyCtl.htm|Yeni oluşturulan denetlemek için bir başvuru içeren bir Web sayfası.|  
  
 Sihirbaz aynı zamanda aşağıdaki kod değişikliklerini gerçekleştirilen:  
  
-   Eklenen bir `#include` ATL eklenecek stdafx.h ve stdafx.cpp dosyaları ifadesine denetimleri desteklemek için gereken dosyalar.  
  
-   Yeni Denetim ayrıntılarını içerecek şekilde değiştirilmiş Polygon.idl.  
  
-   Yeni denetim nesnesi eşleme Polygon.cpp içinde eklendi.  
  
 Şimdi eylemde görmek için denetimi oluşturabilirsiniz.  
  
## <a name="building-and-testing-the-control"></a>Derleme ve denetim test etme  
  
#### <a name="to-build-and-test-the-control"></a>Derleme ve denetim sınamak için  
  
1.  Üzerinde **yapı** menüsünde tıklatın **yapı Çokgen**.  
  
     Denetim yapı tamamlandıktan sonra PolyCtl.htm içinde sağ **Çözüm Gezgini** seçip **tarayıcıda görüntüle**. Denetimi içeren HTML Web sayfası görüntülenir. "Nesne PolyCtl için ATL 8.0 test sayfası" Başlık ve metin içeren bir sayfa görmeniz gerekir **PolyCtl**. Bu, denetimdir.  
  
> [!NOTE]
>  DLL dosyasının nerede oluşturulamıyor bir hata iletisi alırsanız, bu öğreticiyi tamamlarken PolyCtl.htm dosya ve ActiveX denetimi Test kapsayıcısı kapatın ve çözümü yeniden oluşturun. DLL hala oluşturamıyorsanız, bilgisayarı yeniden başlatın veya (Terminal Hizmetleri kullanıyorsanız) oturumu kapatın.  
  
 Sonra denetim için bir özel özellik ekleyeceksiniz.  
  
 [1. adım dön](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [adıma 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici](../atl/active-template-library-atl-tutorial.md)

