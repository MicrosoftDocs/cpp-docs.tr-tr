---
title: Internet'te ActiveX denetimlerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], creating
- ActiveX controls [MFC], Internet
- downloading data with ActiveX controls
- OLE controls [MFC], upgrading to ActiveX
- Internet applications [MFC], ActiveX controls
- networks [MFC], downloading with ActiveX controls
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a42a7bc042301cfbd7d62f82b7c676686146850
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="activex-controls-on-the-internet"></a>Internet'te ActiveX Denetimleri
ActiveX denetimleri OLE denetim belirtimi güncelleştirilmiş sürümü bulunur. Farklı kapsayıcılar, Internet üzerindeki COM kullanan Web tarayıcıları dahil olmak üzere çeşitli kullanılan programlanabilir yazılım bileşenleri geliştirmek için birincil bir mimari denetimleridir. Herhangi bir ActiveX denetimi bir Internet Denetim olması ve işlevselliği için etkin bir belge ekleyebilir veya bir Web sayfası bir parçası olarak. Bir Web sayfasındaki denetimleri birbirleri ile komut dosyası kullanarak iletişim kurabilir.  
  
 ActiveX denetimleri Internet'e sınırlı değildir. Bu kapsayıcı tarafından gerekli arabirimleri denetimi desteklediği sürece bir ActiveX denetimini herhangi kapsayıcısında de kullanılabilir.  
  
 **ActiveX denetimleri de dahil olmak üzere çeşitli avantajları vardır:**  
  
-   Daha az sayıda, daha önceki OLE denetimleri arabirimleri gereklidir.  
  
-   Penceresiz olması ve özelliği her zaman yerinde etkin.  
  
 **ActiveX denetimi olması için bir denetim gerekir:**  
  
-   Destek **IUnknown** arabirimi.  
  
-   Bir COM nesnesi olmalıdır.  
  
-   Dışarı aktarma **DLLRegisterServer** ve **DLLUnRegisterServer**.  
  
-   Ek arabirimleri işlevselliği için gerektiği şekilde destekler.  
  
## <a name="making-your-existing-controls-internet-friendly"></a>Internet kolay, var olan denetimleri yapma  
 Bir Internet ortamda iyi çalışır bir denetimi tasarlarken göz önünde bulundurarak Internet'te düşük iletim hızları için gerektirir. Var olan denetimleri kullanabilirsiniz; Ancak, kodunuzun boyutunu küçültmek ve zaman uyumsuz olarak karşıdan yükle, denetim özellikleri sağlamak için uygulamanız adımlar vardır.  
  
 Denetimlerinizin performansını artırmak için bu ipuçları verimliliği konuları izleyin:  
  
-   Makalede açıklanan teknikleri uygulamak [ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md).  
  
-   Bir denetim nasıl örneği göz önünde bulundurun.  
  
-   Zaman uyumsuz olabilir; diğer programları tutmayın.  
  
-   Küçük bloklar halinde veri indirin.  
  
     Bit eşlemler veya video verileri gibi büyük akışları indirirken bir denetimin veri kapsayıcısı ile işbirliği içinde zaman uyumsuz olarak erişim. İşbirliği ile verilerini de alma diğer denetimleriyle çalışma artımlı veya aşamalı bir şekilde, verileri. Kod ayrıca zaman uyumsuz olarak indiriliyor.  
  
-   Kod ve özellikleri arka planda indirin.  
  
-   Kullanıcı arabirimi hale etkin olarak mümkün olduğunca hızlı bir şekilde.  
  
-   Göz önünde bulundurun kalıcı veri depolanan nasıl özellikleri ve büyük veri BLOB'ların (bir bit eşlem resim veya görüntü veri gibi).  
  
     Önemli miktarda büyük bit eşlemler ya da AVI dosyalar gibi kalıcı veri denetimleriyle yöntemi indirme için dikkat gerektirir. Bir belge veya sayfası mümkün olan en kısa sürede görünür hale gelmiştir ve veri arka planda denetimleri sırasında sayfa ile etkileşim kurmak kullanıcı izin verebilirsiniz.  
  
-   Kod boyutu tutmak ve çalışma zamanı için verimli yordamları yazma.  
  
     Küçük düğme ve etiket denetimleri, yalnızca birkaç bayt kalıcı veri ile Internet ortamı ve tarayıcılar da içinde iş kullanım için uygundur.  
  
-   İlerleme kapsayıcıya iletilen göz önünde bulundurun.  
  
     Kullanıcı içeren bir sayfa etkileşim başlatmak için zaman ve yükleme tamamlandığında dahil olmak üzere zaman uyumsuz indirme ediyor kapsayıcı bildirin. (Tamamlanma yüzdesi gibi) kapsayıcı kullanıcıya ilerleme durumunu görüntüleyebilirsiniz.  
  
-   Denetimleri istemci bilgisayarda kayıtlı nasıl göz önünde bulundurun.  
  
## <a name="creating-a-new-activex-control"></a>Yeni bir ActiveX denetimi oluşturma  
 Uygulama Sihirbazı'nı kullanarak yeni bir denetim oluşturma zaman zaman uyumsuz adlar ve bunun yanı sıra diğer en iyi duruma getirme için destek etkinleştirmeyi seçebilirsiniz. Denetim Özellikleri zaman uyumsuz olarak indirmek için destek eklemek için aşağıdaki adımları izleyin:  
  
#### <a name="to-create-your-project-using-the-mfc-activex-control-wizard"></a>MFC ActiveX Denetim Sihirbazı'nı kullanarak projenizi oluşturmak için  
  
1.  Tıklatın `New` üzerinde **dosya** menüsü.  
  
2.  Seçin **MFC ActiveX Denetim Sihirbazı** Visual C++ projeleri ve projenizi adlandırın.  
  
3.  Üzerinde **denetim ayarlarını** sayfasında, **özellikleri zaman uyumsuz olarak yükleyen**. Bu seçeneğin belirlenmesi hazır state özelliği ve hazır durumu değişti olayını sizin için ayarlar.  
  
     Gibi diğer iyileştirmeler seçebilirsiniz **penceresiz etkinleştirme**, açıklanan [ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md).  
  
4.  Seçin **son** projesi oluşturmak için.  
  
#### <a name="to-create-a-class-derived-from-cdatapathproperty"></a>CDataPathProperty türetilmiş bir sınıf oluşturmak için  
  
1.  Türetilmiş bir sınıf oluşturun `CDataPathProperty`.  
  
2.  Her denetim için üstbilgi dosyası içeren kaynak dosyalarınız, kendisinden önce bu sınıf için üstbilgi dosyası ekleyin.  
  
3.  Bu sınıf, geçersiz kılma `OnDataAvailable`. Veri görüntüleme için kullanılabilir olduğunda bu işlev çağrılır. Veri olarak kullanılabilir hale geldiğinde, örneğin aşamalı olarak işleyerek seçtiğiniz herhangi bir şekilde işleyebilir.  
  
     Aşağıdaki kod Alıntısı aşamalı bir düzenleme denetimindeki verileri görüntüleme, basit bir örnek verilmiştir. Bayrağı Not **BSCF_FIRSTDATANOTIFICATION** düzenleme denetimi temizleyin.  
  
     [!code-cpp[NVC_MFCActiveXControl#1](../mfc/codesnippet/cpp/activex-controls-on-the-internet_1.cpp)]  
  
     AFXCMN içermesi gerektiğini unutmayın. Kullanılacak H `CListCtrl` sınıfı.  
  
4.  Denetim genel zaman durumu (örneğin, çok başlatılmış yüklenirken veya etkileşimli kullanıcı), çağrı değiştirir `COleControl::InternalSetReadyState`. Denetiminiz yalnızca bir veri yolu özelliğine sahipse, kod ekleyebilirsiniz **BSCF_LASTDATANOTIFICATION** kapsayıcı karşıdan tamamlandığını bildirmek için. Örneğin:  
  
     [!code-cpp[NVC_MFCActiveXControl#2](../mfc/codesnippet/cpp/activex-controls-on-the-internet_2.cpp)]  
  
5.  Geçersiz kılma `OnProgress`. İçinde `OnProgress`, en büyük aralığı gösteren bir sayı geçirilir ve bir numara gösteren ne kadar geçerli indirme boyunca olduğu. Bu sayı, kullanıcıya gibi tamamlanma durumunu görüntülemek için kullanabilirsiniz.  
  
 Sonraki yordam yalnızca türetilmiş sınıf kullanılacak denetim için bir özellik ekler.  
  
#### <a name="to-add-a-property"></a>Bir özellik eklemek için  
  
1.  İçinde **sınıf görünümü**, kitaplık düğümünün altında bir arabirime sağ tıklayın ve seçin **Ekle**, ardından **Özellik Ekle**. Bu başlatır **Özellik Ekleme Sihirbazı'nı**.  
  
2.  İçinde **Özellik Ekleme Sihirbazı'nı**seçin **kümesi/Get yöntemleri** radyo düğmesi, türü **özellik adı**, örneğin, EditControlText ve select BSTR olarak**Özellik türü**.  
  
3.  **Son**'a tıklayın.  
  
4.  Üye değişken bildirme, `CDataPathProperty`-ActiveX denetim sınıfınıza türetilmiş sınıf.  
  
     [!code-cpp[NVC_MFCActiveXControl#3](../mfc/codesnippet/cpp/activex-controls-on-the-internet_3.h)]  
  
5.  Uygulama **Get/Set** yöntemleri. İçin **almak**, dize döndürür. İçin `Set`, özellik ve çağrı yük `SetModifiedFlag`.  
  
     [!code-cpp[NVC_MFCActiveXControl#4](../mfc/codesnippet/cpp/activex-controls-on-the-internet_4.cpp)]  
  
6.  İçinde [DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange), aşağıdaki satırı ekleyin:  
  
     [!code-cpp[NVC_MFCActiveXControl#5](../mfc/codesnippet/cpp/activex-controls-on-the-internet_5.cpp)]  
  
7.  Geçersiz kılma [ResetData](../mfc/reference/cdatapathproperty-class.md#resetdata) bu satırı ekleyerek denetimiyle sıfırlamak için özellik bildirmek için:  
  
     [!code-cpp[NVC_MFCActiveXControl#6](../mfc/codesnippet/cpp/activex-controls-on-the-internet_6.cpp)]  
  
## <a name="deciding-whether-to-derive-from-cdatapathproperty-or-ccacheddatapathproperty"></a>CDataPathProperty veya CCachedDataPathProperty çıkarmaya karar verme  
 Önceki örnekte denetiminizin özelliğinden türetme adımlarını açıklar `CDataPathProperty`. Sık sık değişen ve tüm veriler, ancak yalnızca geçerli değer tutmak gerekmez gerçek zamanlı veri yüklüyorsanız bu iyi bir seçimdir. Bir bandı denetimi örneğidir.  
  
 Öğesinden türetilen `CCachedDataPathProperty`. Bu durumda, karşıdan yüklenen veri bellek dosyasına önbelleğe alınır. İndirilen tüm verileri tutmak gerekiyorsa bu iyi bir seçimdir — Örneğin, bir bit eşlem aşamalı olarak işleyen bir denetim. Bu durumda, sınıf verilerinizi içeren bir üye değişkenine sahiptir:  
  
 `CMemFile m_Cache;`  
  
 ActiveX denetimi sınıfınızda bu bellek eşlenen dosyasında kullanabilirsiniz `OnDraw` verileri görüntülemek için. ActiveX denetiminde `CCachedDataPathProperty`-türetilmiş sınıf, üye işlevi geçersiz kılma `OnDataAvailable` ve temel sınıf uygulamasını çağrıldıktan sonra Denetim geçersiz.  
  
 [!code-cpp[NVC_MFCActiveXControl#7](../mfc/codesnippet/cpp/activex-controls-on-the-internet_7.cpp)]  
  
## <a name="downloading-data-asynchronously-using-activex-controls"></a>Zaman uyumsuz olarak ActiveX denetimlerini kullanarak veri indirme  
 Bir ağ üzerinden veri indirme zaman uyumsuz olarak yapılmalıdır. Bunun avantajı dolayısıyla, büyük miktarda veri transfer veya bağlantı yavaşsa, indirme işlemini istemci üzerinde başka işlemler engellemez olur.  
  
 Zaman uyumsuz adlar verileri bir ağ üzerinden zaman uyumsuz olarak indirmek için bir yol sağlar. İşlem tamamlanmamış olsa bile okuma işlemi zaman uyumsuz bir takma hemen döndürür.  
  
 Örneğin, yalnızca 10 bayt kullanılabilir ve okuma 1 K dosyada çağrılan zaman uyumsuz okuma değil engeller, ancak şu anda kullanılabilir 10 bayt ile döndürür.  
  
 Uygulamanız [zaman uyumsuz adlar](../mfc/asynchronous-monikers-on-the-internet.md) kullanarak `CAsyncMonikerFile` sınıfı. Ancak, ActiveX denetimlerini kullanabilirsiniz `CDataPathProperty` türetilmiş sınıf `CAsyncMonikerFile`, zaman uyumsuz denetim özellikleri uygulamak yardımcı olacak.  
  
 ASYNDOWN örnek verileri okumak için zamanlayıcılar kullanılarak zaman uyumsuz bir döngü ayarlanacağı gösterilmiştir. ASYNDOWN "Nasıl yapılır: AsyncDown gösteren zaman uyumsuz veri indirme" (Q177244) Bilgi Bankası makalesinde ayrıntılı açıklanan ve Microsoft Download Center Merkezi'nden yüklenebilir. (Microsoft Download Center'dan gelen dosyaları indirme hakkında daha fazla bilgi için "Nasıl elde Microsoft destek dosyaları gelen çevrimiçi Hizmetleri" (Q119591) Microsoft Bilgi Bankası makalesine bakın.) Bilgi Bankası makalelerini bulabilirsiniz [ http://support.microsoft.com/support ](http://support.microsoft.com/support).  
  
 ASYNDOWN içinde kullanılan temel bir süreölçer ayarlamak için bir tekniktir **CDataPathProperty::OnDataAvailable** veriler kullanılabilir olduğunda belirtmek için. Süreölçer iletisi alındığında, uygulama veri 128 bayt bloklarında okur ve düzenleme denetimi doldurur. Zamanlayıcı ileti işlendiğinde veri kullanılabilir durumda değilse, Zamanlayıcı kapalıdır. `OnDataAvailable` Daha fazla veri daha sonra alınırsa zamanlayıcıda etkinleştirir.  
  
## <a name="displaying-a-control-on-a-web-page"></a>Bir Web sayfasında bir denetimi görüntüleme  
 Bir nesne etiketinin ve bir Web sayfasına denetim ekleme öznitelikleri bir örneği burada verilmiştir.  
  
 `<OBJECT`  
  
 `CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"`  
  
 `CODEBASE="/ie/download/activex/iechart.ocx"`  
  
 `ID=chart1`  
  
 `WIDTH=400`  
  
 `HEIGHT=200`  
  
 `ALIGN=center`  
  
 `HSPACE=0`  
  
 `VSPACE=0`  
  
 `>`  
  
 `<PARAM NAME="BackColor" value="#ffffff">`  
  
 `<PARAM NAME="ForeColor" value="#0000ff">`  
  
 `<PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt">`  
  
 `</OBJECT>`  
  
## <a name="updating-an-existing-ole-control-to-use-new-activex-control-features"></a>Yeni ActiveX denetimi özelliklerini kullanmak için mevcut bir OLE denetimi güncelleştiriliyor  
 OLE denetim 4.2 önce Visual C++ sürümüyle oluşturulduysa, kendi performansını artırmak ve işlevselliğini geliştirmek için atabileceğiniz adımlar vardır. Bu değişiklikler hakkında ayrıntılı bilgi için bkz: [ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md).  
  
 Varolan bir denetim için zaman uyumsuz özellik desteği ekliyorsanız, hazır durumda özellik eklemeniz gerekir ve `ReadyStateChange` olay kendiniz. Denetim Oluşturucusu ekleyin:  
  
 [!code-cpp[NVC_MFCActiveXControl#8](../mfc/codesnippet/cpp/activex-controls-on-the-internet_8.cpp)]  
  
 Kodunuzu çağırarak indirildiğini hazır durumunu güncelleştirir [COleControl::InternalSetReadyState](../mfc/reference/colecontrol-class.md#internalsetreadystate). Tek bir yerde çağrısı `InternalSetReadyState` arasındadır `OnProgress` , geçersiz kılma `CDataPathProperty`-türetilmiş sınıf.  
  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet programlama görevleri](../mfc/mfc-internet-programming-tasks.md)   
 [MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)

