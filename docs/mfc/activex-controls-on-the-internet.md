---
title: Internet'te ActiveX Denetimleri
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX controls [MFC], creating
- ActiveX controls [MFC], Internet
- downloading data with ActiveX controls
- OLE controls [MFC], upgrading to ActiveX
- Internet applications [MFC], ActiveX controls
- networks [MFC], downloading with ActiveX controls
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
ms.openlocfilehash: f06a6f6f71e922163fd95c59836c50b88b05ed3a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616474"
---
# <a name="activex-controls-on-the-internet"></a>Internet'te ActiveX Denetimleri

ActiveX denetimleri, OLE denetim belirtiminin güncelleştirilmiş sürümüdür.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. Daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Denetimler, Internet 'teki COM uyumlu Web tarayıcıları dahil olmak üzere çeşitli farklı kapsayıcılarda kullanılabilen programlanabilir yazılım bileşenleri geliştirmeye yönelik birincil mimaridir. Herhangi bir ActiveX denetimi Internet denetimi olabilir ve işlevselliğini etkin bir belgeye ekleyebilir veya bir Web sayfasının parçası olabilir. Bir Web sayfasındaki denetimler, komut dosyası kullanarak birbirleriyle iletişim kurabilir.

ActiveX denetimleri Internet ile sınırlı değildir. Denetim, bu kapsayıcının gerektirdiği arabirimleri desteklediği sürece, herhangi bir kapsayıcıda bir ActiveX denetimi de kullanılabilir.

**ActiveX denetimleri aşağıdakiler dahil olmak üzere çeşitli avantajlar sunar:**

- Önceki OLE denetimlerinden daha az gerekli arabirim.

- Penceresiz ve her zaman yerinde etkin olabilir.

**Bir ActiveX denetimi olabilmesi için bir denetim şu şekilde olmalıdır:**

- Arabirimi destekler `IUnknown` .

- Bir COM nesnesi olmalıdır.

- **DllRegisterServer** ve **DllUnregisterServer**'yi dışarı aktarın.

- İşlevselliği için gereken ek arabirimleri destekleme.

## <a name="making-your-existing-controls-internet-friendly"></a>Mevcut denetimlerinizi Internet 'e uygun hale getirme

Internet ortamında iyi şekilde çalışacak bir denetim tasarlamak, Internet 'teki görece düşük iletim ücretleri için göz önünde bulundurmanız gerekir. Mevcut denetimlerinizi kullanabilirsiniz; Ancak, kod boyutunuzu daha küçük hale getirmek ve denetim özelliklerinizi zaman uyumsuz olarak indirmek için gerçekleştirmeniz gereken adımlar vardır.

Denetimlerinizin performansını geliştirmek için, verimlilik konusunda bu ipuçlarını izleyin:

- [ActiveX denetimleri: iyileştirme](mfc-activex-controls-optimization.md)makalesinde açıklanan teknikleri uygulayın.

- Bir denetimin nasıl örneklendiği göz önünde bulundurun.

- Zaman uyumsuz olmalıdır; diğer programları basılı tutun.

- Küçük bloklar halinde veri indirin.

   Bit eşlemler veya video verileri gibi büyük akışları indirirken, kapsayıcı ile birlikte işlem sırasında denetim verilerine zaman uyumsuz olarak erişin. Verileri artımlı veya aşamalı bir biçimde alarak, verileri alan diğer denetimlerle birlikte çalışmaya çalışma. Kod zaman uyumsuz olarak da karşıdan yüklenebilir.

- Arka planda kod ve Özellikler indirin.

- Kullanıcı arabirimini mümkün olduğunca hızlı bir şekilde etkin hale gelir.

- Kalıcı verilerin nasıl depolandığını, hem Özellikler hem de büyük veri Bloblarını (örneğin, bir bit eşlem görüntüsü veya video verileri) göz önünde bulundurun.

   Büyük bit eşlemler veya AVI dosyaları gibi önemli miktarda kalıcı verileri olan denetimler, indirme yöntemine dikkat etmeniz gerekir. Bir belge veya sayfa mümkün olan en kısa sürede görünür hale gelebilir ve denetimler arka planda verileri alırken kullanıcının sayfayla etkileşime girmesine izin verebilirsiniz.

- Kod boyutunu tutmak ve çalışma süresini korumak için etkili yordamlar yazın.

   Küçük düğme ve etiket denetimleri, yalnızca birkaç bayt kalıcı veri ile Internet ortamında kullanım için uygundur ve tarayıcıların içinde iyi çalışır.

- İlerlemeyi, kapsayıcıya iletilir.

   Kullanıcının bir sayfayla etkileşime başlayabileceği ve indirme tamamlandığında de dahil olmak üzere, zaman uyumsuz indirme sırasında ilerleme kapsayıcısını bilgilendirin. Kapsayıcı, kullanıcıya ilerlemeyi (Tamamlanma yüzdesi gibi) görüntüleyebilir.

- Denetimlerin istemci bilgisayarda nasıl kaydedildiğini göz önünde bulundurun.

## <a name="creating-a-new-activex-control"></a>Yeni bir ActiveX denetimi oluşturma

Uygulama Sihirbazı 'nı kullanarak yeni bir denetim oluştururken, zaman uyumsuz takma ve diğer iyileştirmelerin desteğini etkinleştirmeyi seçebilirsiniz. Denetim özelliklerini zaman uyumsuz olarak indirme desteği eklemek için aşağıdaki adımları izleyin:

#### <a name="to-create-your-project-using-the-mfc-activex-control-wizard"></a>MFC ActiveX denetimi Sihirbazı 'Nı kullanarak projenizi oluşturmak için

1. **Dosya** menüsünde **Yeni** ' ye tıklayın.

1. Visual Studio C++ projeleri ' nden **MFC ActiveX denetimi Sihirbazı** ' nı seçin ve projenizi adlandırın.

1. **Denetim ayarları** sayfasında, **özellikleri zaman uyumsuz olarak yükler**' i seçin. Bu seçeneğin belirlenmesi, sizin için Ready State özelliğini ve Ready durumu değişti olayını ayarlar.

   Ayrıca, [ActiveX denetimleri: iyileştirme](mfc-activex-controls-optimization.md)' de açıklanan **penceresiz etkinleştirme**gibi diğer iyileştirmeler de seçebilirsiniz.

1. Projeyi oluşturmak için **son** ' a tıklayın.

#### <a name="to-create-a-class-derived-from-cdatapathproperty"></a>CDataPathProperty öğesinden türetilmiş bir sınıf oluşturmak için

1. Öğesinden türetilmiş bir sınıf oluşturun `CDataPathProperty` .

1. Denetiminizin başlık dosyasını içeren kaynak dosyalarınızın her birinde, bu sınıfın başlık dosyasını önce ekleyin.

1. Bu sınıfta, öğesini geçersiz kılın `OnDataAvailable` . Bu işlev, veriler görüntülenmek üzere kullanılabilir olduğunda çağrılır. Veriler kullanılabilir hale geldiğinde, bunu istediğiniz şekilde işleyebilir, örneğin aşamalı olarak işleme alabilirsiniz.

   Aşağıdaki kod alıntısı, bir düzenleme denetimindeki verileri aşamalı olarak görüntülemeye yönelik basit bir örnektir. Düzenleme denetimini temizlemek için bayrak **BSCF_FIRSTDATANOTIFICATION** kullanımını aklınızda bırakın.

   [!code-cpp[NVC_MFCActiveXControl#1](codesnippet/cpp/activex-controls-on-the-internet_1.cpp)]

   AFXCMN 'yi dahil etmeniz gerektiğini unutmayın. Bu `CListCtrl` sınıfı kullanın.

1. Denetiminizin genel durumu değiştiğinde (örneğin, yüklenmeye veya Kullanıcı etkileşimlidir), çağrısı yapın `COleControl::InternalSetReadyState` . Denetiminizin yalnızca bir veri yolu özelliği varsa, indirmenin tamamlandığını kapsayıcıya bildirmek için **BSCF_LASTDATANOTIFICATION** kod ekleyebilirsiniz. Örnek:

   [!code-cpp[NVC_MFCActiveXControl#2](codesnippet/cpp/activex-controls-on-the-internet_2.cpp)]

1. Geçersiz kıl `OnProgress` . `OnProgress`' De, en büyük aralığı gösteren bir sayı ve geçerli indirmenin ne kadar olduğunu gösteren bir sayı geçirirsiniz. Bu numaraları, kullanıcının tamamlanma yüzdesi gibi durumu göstermek için kullanabilirsiniz.

Sonraki yordam, yeni türetilmiş sınıfı kullanmak için denetime bir özellik ekler.

#### <a name="to-add-a-property"></a>Bir özellik eklemek için

1. **Sınıf görünümü**, kitaplık düğümünün altındaki arabirime sağ tıklayın ve **Ekle**' yi ve ardından **Özellik Ekle**' yi seçin. Bu işlem **Özellik Ekleme Sihirbazı 'nı**başlatır.

1. **Özellik Ekleme sihirbazında**, **Ayarla/al metotları** radyo düğmesini seçin, **özellik adını**yazın, örneğin, EditControlText yazın ve **özellik türü**olarak BSTR ' yi seçin.

1. **Son**'a tıklayın.

1. `CDataPathProperty`ActiveX denetim sınıfınıza türetilmiş sınıfınızın bir üye değişkenini bildirin.

   [!code-cpp[NVC_MFCActiveXControl#3](codesnippet/cpp/activex-controls-on-the-internet_3.h)]

1. Yöntemlerini uygulayın `Get/Set` . İçin `Get` , dizeyi döndürün. İçin `Set` , özelliğini yükleyin ve çağırın `SetModifiedFlag` .

   [!code-cpp[NVC_MFCActiveXControl#4](codesnippet/cpp/activex-controls-on-the-internet_4.cpp)]

1. [DoPropExchange](reference/colecontrol-class.md#dopropexchange)'te aşağıdaki satırı ekleyin:

   [!code-cpp[NVC_MFCActiveXControl#5](codesnippet/cpp/activex-controls-on-the-internet_5.cpp)]

1. Bu satırı ekleyerek denetimin denetimini sıfırlamasına izin vermek için [ResetData](reference/cdatapathproperty-class.md#resetdata) öğesini geçersiz kılın:

   [!code-cpp[NVC_MFCActiveXControl#6](codesnippet/cpp/activex-controls-on-the-internet_6.cpp)]

## <a name="deciding-whether-to-derive-from-cdatapathproperty-or-ccacheddatapathproperty"></a>CDataPathProperty veya CCachedDataPathProperty öğesinden türetilip Türetilmeyeceğine karar verme

Önceki örnekte, denetiminizin özelliğini ' den türetmede uygulanacak adımlar açıklanmaktadır `CDataPathProperty` . Sık değişen gerçek zamanlı verileri karşıdan yüklüyorsanız ve tüm verileri tutmanız gerekmiyorsa yalnızca geçerli değer olan bu iyi bir seçenektir. Bir hisse senedi şeridi denetimi örneği.

Ayrıca, öğesinden türetebilirsiniz `CCachedDataPathProperty` . Bu durumda, indirilen veriler bir bellek dosyasında önbelleğe alınır. Tüm indirilen verileri tutmanız gerekiyorsa (örneğin, aşamalı olarak bir bit eşlem işleyen bir denetim gibi) bu iyi bir seçenektir. Bu durumda, sınıfının verilerinizi içeren bir üye değişkeni vardır:

`CMemFile m_Cache;`

ActiveX denetim sınıfınıza, verileri göstermek için içinde bu bellek eşlemeli dosyayı kullanabilirsiniz `OnDraw` . ActiveX denetimi `CCachedDataPathProperty` türetilmiş sınıfınız içinde, üye işlevini geçersiz kılın `OnDataAvailable` ve temel sınıf uygulamasını çağırdıktan sonra denetimi geçersiz kılın.

[!code-cpp[NVC_MFCActiveXControl#7](codesnippet/cpp/activex-controls-on-the-internet_7.cpp)]

## <a name="downloading-data-asynchronously-using-activex-controls"></a>ActiveX denetimlerini kullanarak verileri zaman uyumsuz olarak indirme

Verilerin ağ üzerinden indirilmesi zaman uyumsuz olarak yapılmalıdır. Bunu yapmanın avantajı, büyük miktarda veri aktarıldığında veya bağlantı yavaşsa, indirme işleminin istemcideki diğer işlemleri engellememe sürecimiz olur.

Zaman uyumsuz bilinen adlar, verileri zaman uyumsuz olarak bir ağ üzerinden indirmenin yolunu sağlar. Zaman uyumsuz bir bilinen ad üzerinde okuma işlemi, işlem tamamlanmamış olsa bile hemen döndürülür.

Örneğin, yalnızca 10 baytlık kullanılabilir ve okuma işlemi bir 1K dosyasında zaman uyumsuz olarak çağrılırsa, Read engellenmez, ancak şu anda kullanılabilir 10 bayt ile döner.

Sınıfını kullanarak [zaman uyumsuz adlar](asynchronous-monikers-on-the-internet.md) uygulayabilirsiniz `CAsyncMonikerFile` . Ancak, ActiveX denetimleri `CDataPathProperty` `CAsyncMonikerFile` zaman uyumsuz denetim özelliklerini uygulamaya yardımcı olmak için öğesinden türetilmiş sınıfını kullanabilir.

## <a name="displaying-a-control-on-a-web-page"></a>Web sayfasında bir denetimi görüntüleme

Bir Web sayfasına bir denetim eklemek için bir nesne etiketine ve özniteliklerine bir örnek aşağıda verilmiştir.

```xml
<OBJECT
  CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"
  CODEBASE="/ie/download/activex/iechart.ocx"
  ID=chart1
  WIDTH=400
  HEIGHT=200
  ALIGN=center
  HSPACE=0
  VSPACE=0>
  <PARAM NAME="BackColor" value="#ffffff"/>
  <PARAM NAME="ForeColor" value="#0000ff"/>
  <PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt"/>
</OBJECT>
```

## <a name="updating-an-existing-ole-control-to-use-new-activex-control-features"></a>Var olan bir OLE denetimini yeni ActiveX denetim özelliklerini kullanmak üzere güncelleştirme

OLE denetiminiz 4,2 ' den önceki bir Visual C++ sürümüyle oluşturulduysa, performansını iyileştirmek ve işlevselliğini geliştirmek için uygulayabileceğiniz adımlar vardır. Bu değişikliklere ilişkin ayrıntılı bir açıklama için bkz. [ActiveX denetimleri: iyileştirme](mfc-activex-controls-optimization.md).

Var olan bir denetime zaman uyumsuz özellik desteği ekliyorsanız, Ready durum özelliğini ve `ReadyStateChange` olayı kendiniz eklemeniz gerekecektir. Denetiminizin oluşturucusunda şunu ekleyin:

[!code-cpp[NVC_MFCActiveXControl#8](codesnippet/cpp/activex-controls-on-the-internet_8.cpp)]

Kodunuz [COleControl:: InternalSetReadyState](reference/colecontrol-class.md#internalsetreadystate)çağırarak indirildiğinden, Ready durumu güncelleirsiniz. Çağırabileceğiniz bir yer `InternalSetReadyState` , `OnProgress` türetilen sınıftan geçersiz kılınmasından oluşur `CDataPathProperty` .

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Görevleri](mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](mfc-internet-programming-basics.md)
