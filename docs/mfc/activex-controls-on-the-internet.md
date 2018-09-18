---
title: Internet'te ActiveX denetimleri | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
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
ms.openlocfilehash: d3e7603bfe2074022cdaa0e99024627c32452b46
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072803"
---
# <a name="activex-controls-on-the-internet"></a>Internet'te ActiveX Denetimleri

OLE denetim belirtimi güncelleştirilmiş sürümünü ActiveX denetimleri var. 

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. Daha fazla bilgi için [ActiveX denetimlerini](activex-controls.md).

Farklı kapsayıcılar, Internet üzerindeki COM kullanan Web tarayıcıları dahil olmak üzere çeşitli kullanılabilir programlanabilir yazılım bileşenleri geliştirmek için birincil bir mimari denetimlerdir. Herhangi bir ActiveX denetimi Internet denetimi ve işlevselliği için etkin bir belge ekleyebilir veya bir Web sayfasının parçası olarak. Bir Web sayfasındaki denetimleri komut dosyası aracılığıyla birbirleriyle iletişim kurabilir.  
  
 ActiveX denetimleri, Internet'e sınırlı değildir. Denetimin, kapsayıcı tarafından gerekli arabirimleri desteklediği sürece herhangi bir kapsayıcıda bir ActiveX denetimini de kullanılabilir.  
  
 **ActiveX denetimleri de dahil olmak üzere çeşitli avantajları vardır:**  
  
-   Daha az sayıda, önceki OLE denetimleri arabirimleri gereklidir.  
  
-   Penceresiz olmasını özelliği ve her zaman yerinde etkin.  
  
 **Bir ActiveX denetimi için Denetim gerekir:**  
  
-   Destek `IUnknown` arabirimi.  
  
-   Bir COM nesnesi olabilir.  
  
-   Dışarı aktarma **DLLRegisterServer** ve **DLLUnRegisterServer**.  
  
-   Ek arabirimleri işlevselliği için gerektiği şekilde destekler.  
  
## <a name="making-your-existing-controls-internet-friendly"></a>Mevcut denetimleri Internet uyumlu hale getirme  
 İyi bir Internet ortamda çalışacak bir denetimi tasarlarken göz önünde bulundurarak Internet üzerindeki düşük iletim hızları için gerektirir. Mevcut denetimleri kullanabilirsiniz; Ancak, kodunuzun boyutunu küçültmek ve zaman uyumsuz olarak indirin, denetim özelliklerini sağlamak için uygulamanız gereken adımlar vardır.  
  
 Denetimlerinizi performansını artırmak için verimlilik konuları üzerinde bu ipuçlarını izleyin:  
  
-   Makalesinde açıklanan teknikleri uygulamak [ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md).  
  
-   Bir denetimi nasıl örneği göz önünde bulundurun.  
  
-   Zaman uyumsuz olması; diğer programları tutmayın.  
  
-   Küçük bloklar veri indirin.  
  
     Bit eşlemler veya video verileri gibi büyük akışlarını indirirken bir denetimin veri kapsayıcısı ile işbirliği içinde zaman uyumsuz olarak erişin. İşbirliği ile verileri de alınırken diğer denetimlerle çalışma artımlı veya aşamalı bir biçimde, verileri alır. Kod ayrıca zaman uyumsuz olarak yükleniyor.  
  
-   Kod ve arka planda özellikleri yükleyin.  
  
-   Kullanıcı arabirimi haline mümkün olduğunca çabuk etkin.  
  
-   Göz önünde bulundurun kalıcı veriler nasıl hem özellikleri hem de büyük veri BLOB'ları (bir bit eşlem resim veya video veriler gibi).  
  
     Önemli miktarda büyük bit eşlemler ya da AVI dosyalar gibi kalıcı veri denetimleriyle yükleme yöntemi için çok dikkat gerektirir. Bir belge veya sayfa olabildiğince çabuk görünür hale gelir ve denetimlerini arka planda verileri alınırken bir sayfa ile etkileşim kurmak kullanıcı izin verebilirsiniz.  
  
-   Kod boyutu korumak ve çalışma zamanı için verimli yordamları yazın.  
  
     Yalnızca bazı baytını kalıcı veri sahip küçük düğme ve etiket denetimleri, Internet ortam ve iş tarayıcılar da içinde kullanmak için uygundur.  
  
-   İlerleme kapsayıcıya bildiriliyor göz önünde bulundurun.  
  
     Kullanıcı bir sayfa ile etkileşim başlatmak için ne zaman ve yükleme tamamlandığında gibi zaman uyumsuz indirme sürüyor kapsayıcı bildirin. (Tamamlanma gibi), kapsayıcı kullanıcıya ilerleme durumunu görüntüleyebilirsiniz.  
  
-   İstemci bilgisayarda kayıtlı denetimleri nasıl göz önünde bulundurun.  
  
## <a name="creating-a-new-activex-control"></a>Yeni bir ActiveX denetimi oluşturma  
 Uygulama Sihirbazı'nı kullanarak yeni bir denetim oluştururken, zaman uyumsuz adlar ve bunun yanı sıra diğer iyileştirmeler için desteği etkinleştirmeyi seçebilirsiniz. Denetim özelliklerini zaman uyumsuz olarak indirmek için destek eklemek üzere aşağıdaki adımları izleyin:  
  
#### <a name="to-create-your-project-using-the-mfc-activex-control-wizard"></a>MFC ActiveX Denetim Sihirbazı'nı kullanarak projenizi oluşturmak için  
  
1.  Tıklayın **yeni** üzerinde **dosya** menüsü.  
  
2.  Seçin **MFC ActiveX Denetim Sihirbazı** projeler Visual C++'tan ve projenize bir ad verin.  
  
3.  Üzerinde **denetim ayarları** sayfasında **zaman uyumsuz olarak özelliklerini yükler**. Bu seçeneğin belirlenmesi hazır durumda özelliği ve hazır durumu değişti olayını sizin için ayarlar.  
  
     Diğer iyileştirmeler gibi seçebilirsiniz **penceresiz etkinleştirme**, açıklanan [ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md).  
  
4.  Seçin **son** projeyi oluşturmak için.  
  
#### <a name="to-create-a-class-derived-from-cdatapathproperty"></a>CDataPathProperty türetilmiş bir sınıf oluşturmak için  
  
1.  Türetilen bir sınıf oluşturma `CDataPathProperty`.  
  
2.  Her denetim için üst bilgi dosyası içeren kaynak dosyalarınız, kendisinden önce bu sınıf için üst bilgi dosyası ekleyin.  
  
3.  Bu sınıf, geçersiz kılma `OnDataAvailable`. Görüntülenecek veriler kullanılabilir olduğunda bu işlev çağrılır. Veri kullanılabilir oldukça, örneğin aşamalı olarak işleyerek seçtiğiniz herhangi bir şekilde işleyebilir.  
  
     Aşağıdaki kod Alıntısı, aşamalı bir düzenleme denetiminde veri görüntüleme, basit bir örnektir. Bayrağı kullanımına dikkat edin **BSCF_FIRSTDATANOTIFICATION** düzenleme denetiminin temizleyin.  
  
     [!code-cpp[NVC_MFCActiveXControl#1](../mfc/codesnippet/cpp/activex-controls-on-the-internet_1.cpp)]  
  
     AFXCMN içermesi gerektiğini unutmayın. Kullanılacak H `CListCtrl` sınıfı.  
  
4.  Denetiminiz genel olduğunda durumu (örneğin, yükleme için başlatılmış veya etkileşimli kullanıcı), çağrı değişiklikleri `COleControl::InternalSetReadyState`. Denetim yalnızca bir veri yolu özelliği varsa, kod üzerinde ekleyebilirsiniz **BSCF_LASTDATANOTIFICATION** kapsayıcı indirmenizin tamamlandığını bildirmek için. Örneğin:  
  
     [!code-cpp[NVC_MFCActiveXControl#2](../mfc/codesnippet/cpp/activex-controls-on-the-internet_2.cpp)]  
  
5.  Geçersiz kılma `OnProgress`. İçinde `OnProgress`, en büyük aralık gösteren bir sayı geçirilir ve bir sayı gösteren geçerli indirme boyunca ne kadar olan. Bu numaraları gibi tamamlanma durumu kullanıcıya göstermek için kullanabilirsiniz.  
  
 Sonraki yordam yalnızca türetilmiş bir sınıf kullanma denetimine bir özellik ekler.  
  
#### <a name="to-add-a-property"></a>Bir özellik eklemek için  
  
1.  İçinde **sınıf görünümü**, kitaplık düğümünün altında bir arabirime sağ tıklayın ve seçin **Ekle**, ardından **Özellik Ekle**. Bu başlatır **Özellik Ekleme Sihirbazı'nı**.  
  
2.  İçinde **Özellik Ekleme Sihirbazı'nı**seçin **Set/Get metodları** radyo düğmesi, türü **özellik adı**, örneğin, EditControlText ve select BSTR olarak**Özellik türü**.  
  
3.  **Son**'a tıklayın.  
  
4.  Üye değişkeni bildirmek, `CDataPathProperty`-ActiveX denetim sınıfı türetilmiş sınıf.  
  
     [!code-cpp[NVC_MFCActiveXControl#3](../mfc/codesnippet/cpp/activex-controls-on-the-internet_3.h)]  
  
5.  Uygulama `Get/Set` yöntemleri. İçin `Get`, dizeyi döndür. İçin `Set`, özellik ve çağrı yük `SetModifiedFlag`.  
  
     [!code-cpp[NVC_MFCActiveXControl#4](../mfc/codesnippet/cpp/activex-controls-on-the-internet_4.cpp)]  
  
6.  İçinde [DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange), aşağıdaki satırı ekleyin:  
  
     [!code-cpp[NVC_MFCActiveXControl#5](../mfc/codesnippet/cpp/activex-controls-on-the-internet_5.cpp)]  
  
7.  Geçersiz kılma [ResetData](../mfc/reference/cdatapathproperty-class.md#resetdata) bu satırı ekleyerek denetimiyle sıfırlama özelliği bildirmek için:  
  
     [!code-cpp[NVC_MFCActiveXControl#6](../mfc/codesnippet/cpp/activex-controls-on-the-internet_6.cpp)]  
  
## <a name="deciding-whether-to-derive-from-cdatapathproperty-or-ccacheddatapathproperty"></a>CDataPathProperty veya CCachedDataPathProperty türetmek karar verme  
 Önceki örnekte denetiminizin özelliğinden türetme adımlarını açıklar `CDataPathProperty`. Bu, sık sık değişen ve tüm verileri, ancak yalnızca geçerli değerini tutmak gerekmez gerçek zamanlı veri indiriyorsanız iyi bir seçimdir. Bir bandı denetimi buna bir örnektir.  
  
 Ayrıca türetebilirsiniz `CCachedDataPathProperty`. Bu durumda, indirilen veriler, bir bellek dosyasında önbelleğe alınır. İndirilen tüm verileri tutmak gerekirse bu iyi bir seçimdir — Örneğin, bir bit eşlem aşamalı olarak işleyen bir denetim. Bu durumda, verilerinizi içeren bir üye değişkeni sınıfı vardır:  
  
 `CMemFile m_Cache;`  
  
 ActiveX denetim sınıfı bu bellek eşlenen dosyasında kullanabilirsiniz `OnDraw` verileri görüntülemek için. ActiveX denetimi içinde `CCachedDataPathProperty`-türetilmiş sınıf, üye işlev geçersiz kılınamıyor `OnDataAvailable` ve temel sınıf uygulamasına çağrıldıktan sonra denetimi geçersiz.  
  
 [!code-cpp[NVC_MFCActiveXControl#7](../mfc/codesnippet/cpp/activex-controls-on-the-internet_7.cpp)]  
  
## <a name="downloading-data-asynchronously-using-activex-controls"></a>Zaman uyumsuz olarak ActiveX denetimlerini kullanarak verileri yükleniyor  
 Bir ağ üzerinden veri yükleme zaman uyumsuz olarak gerçekleştirilmelidir. Avantajı Bunun yapılması, bu nedenle, büyük miktarda veri aktarılır veya bağlantısı yavaşsa, indirme işlemini istemci üzerinde başka işlemler engellemez olur.  
  
 Zaman uyumsuz adlar, verileri ağ üzerinden zaman uyumsuz olarak indirmek için bir yol sağlar. Bir okuma işlemi zaman uyumsuz bir bilinen ad, işlemi tamamlanmamış bile hemen döndürür.  
  
 Örneğin, yalnızca 10 bayt mevcuttur ve okunur 1 K dosya zaman uyumsuz olarak adlandırılır, okuma engelleme yapmadığından ancak şu anda 10 bayt ile döndürür.  
  
 Uygulamanız [zaman uyumsuz adlar](../mfc/asynchronous-monikers-on-the-internet.md) kullanarak `CAsyncMonikerFile` sınıfı. Ancak, ActiveX denetimlerini kullanabilirsiniz `CDataPathProperty` sınıfından türetilen sınıf `CAsyncMonikerFile`, zaman uyumsuz denetim özellikleri uygulamak için.  
  
 ASYNDOWN örnek bir zaman uyumsuz döngü verileri okumak için zamanlayıcılar kullanılarak ayarlama işlemini gösterir. ASYNDOWN "Nasıl yapılır: AsyncDown gösteren zaman uyumsuz veri indirin" (Q177244) Bilgi Bankası makalesinde ayrıntılı olarak açıklanmıştır ve Microsoft Download Center indirilerek kullanılabilir. ("Nasıl elde Microsoft destek dosyaları gelen çevrimiçi Hizmetleri" (Q119591) Microsoft Bilgi Bankası'nda makale Microsoft Download Center'dan gelen dosyaları indirme hakkındaki daha fazla bilgi için bkz.) Bilgi Bankası makalelerini bulabilirsiniz [ http://support.microsoft.com/support ](http://support.microsoft.com/support).  
  
 ASYNDOWN içinde kullanılan temel bir süreölçeri düzenlemek için bir tekniktir **CDataPathProperty::OnDataAvailable** veri kullanılabilir olduğunda belirtmek için. Zamanlayıcı iletisi alındığında, uygulama veri 128 bayt bloklarında okur ve bir düzenleme denetimi doldurur. Zamanlayıcı ileti işlendiğinde veri kullanılabilir durumda değilse, Zamanlayıcıyı kapalıdır. `OnDataAvailable` Daha fazla veri daha sonra geldiğinde, Zamanlayıcıyı kapatır.  
  
## <a name="displaying-a-control-on-a-web-page"></a>Bir Web sayfası denetiminde görüntüleme  
 Bir nesne etiketi ve özniteliklerinin bir denetimi Web sayfasına eklemek için bir örnek aşağıda verilmiştir.  
  
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
  
## <a name="updating-an-existing-ole-control-to-use-new-activex-control-features"></a>Yeni bir ActiveX denetimi özelliklerini kullanmak için mevcut bir OLE denetim güncelleştiriliyor  
 OLE denetim 4.2 önce Visual C++'ın bir sürümüyle oluşturulduysa, performansı ve işlevselliği geliştirmek için atabileceğiniz adımlar vardır. Bu değişiklikler hakkında ayrıntılı bilgi için bkz: [ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md).  
  
 Varolan bir denetimi zaman uyumsuz bir özellik destek ekliyorsanız, hazır durumunda özellik eklemeniz gerekir ve `ReadyStateChange` olay kendiniz. Denetiminiz için bir oluşturucuda ekleyin:  
  
 [!code-cpp[NVC_MFCActiveXControl#8](../mfc/codesnippet/cpp/activex-controls-on-the-internet_8.cpp)]  
  
 Kodunuzu çağırarak indirilen olarak hazır durumda güncelleştirilir [COleControl::InternalSetReadyState](../mfc/reference/colecontrol-class.md#internalsetreadystate). Tek bir yerde, çağırın `InternalSetReadyState` dandır `OnProgress` , geçersiz kılma `CDataPathProperty`-türetilmiş sınıf.  
  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet programlama görevleri](../mfc/mfc-internet-programming-tasks.md)   
 [MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)

