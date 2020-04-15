---
title: 'MFC ActiveX Denetimleri: ActiveX Denetimini Yerelleştirme'
ms.date: 09/12/2018
f1_keywords:
- LocaleID
- AfxOleRegisterTypeLib
helpviewer_keywords:
- localization, ActiveX controls
- MFC ActiveX controls [MFC], localizing
- LocaleID ambient property [MFC]
- LOCALIZE sample [MFC]
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
ms.openlocfilehash: 987cde2117307cdb5940a31e6f01efb15c527b84
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364593"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Yerelleştirme

Bu makalede ActiveX denetim arabirimlerini yerelleştirme yordamları anlatılmaktadır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

ActiveX denetimini uluslararası bir pazara uyarlamak istiyorsanız, denetimi yerelleştirmek isteyebilirsiniz. Windows, Varsayılan İngilizce'ye ek olarak Almanca, Fransızca ve İsveççe dahil olmak üzere birçok dili destekler. Bu, arabirimi yalnızca İngilizce ise denetim için sorun ortaya çıkabilir.

Genel olarak, ActiveX denetimleri her zaman ortam LocaleID özelliği kendi yerel temel olmalıdır. Bunu yapmanın üç yolu vardır:

- Ortam LocaleID özelliğinin geçerli değerine bağlı olarak, her zaman isteğe bağlı kaynakları yükleyin. MFC ActiveX, [LOCALIZE](../overview/visual-cpp-samples.md) örneklerini denetler bu stratejiyi kullanır.

- Ortam LocaleID özelliğini temel alan ilk denetim örneklendiğinde kaynakları yükleyin ve bu kaynakları diğer tüm örnekler için kullanın. Bu makale, bu stratejiyi göstermektedir.

    > [!NOTE]
    >  Gelecekteki örneklerin farklı yerel durumları varsa, bu durum bazı durumlarda doğru çalışmaz.

- Kapsayıcının `OnAmbientChanged` yerel durumu için uygun kaynakları dinamik olarak yüklemek için bildirim işlevini kullanın.

    > [!NOTE]
    >  Bu denetim için çalışır, ancak ortam LocaleID özelliği değiştiğinde çalışma zamanı DLL dinamik olarak kendi kaynaklarını güncelleştirmez. Buna ek olarak, ActiveX denetimleri için çalışma zamanı DL'leri, kaynaklarının yerel konumunu belirlemek için iş parçacığı yerelsini kullanır.

Bu makalenin geri kalanında iki yerelleştirme stratejileri açıklanmaktadır. İlk [strateji, denetimin programlanabilirlik arabirimini](#_core_localizing_your_control.92.s_programmability_interface) (özelliklerin, yöntemlerin ve olayların adları) yerelleştirir. İkinci strateji, kapsayıcının ortam LocaleID özelliğini kullanarak [denetimin kullanıcı arabirimini yerelleştirir.](#_core_localizing_the_control.92.s_user_interface) Denetim yerelleştirme bir gösteri için, MFC ActiveX denetimleri örnek [LOCALIZE](../overview/visual-cpp-samples.md)bakın.

## <a name="localizing-the-controls-programmability-interface"></a><a name="_core_localizing_your_control.92.s_programmability_interface"></a>Denetimin Programlanabilirlik Arabirimini Yerelleştirme

Denetimin programlanabilirlik arabirimini (denetiminizi kullanan uygulamaları yazan programcılar tarafından kullanılan arabirim) yerelleştirdiğinizde, denetimin değiştirilmiş bir sürümünü oluşturmanız gerekir. Desteklemek istediğiniz her dil için IDL dosyası (denetim türü kitaplığını oluşturmak için bir komut dosyası). Denetim özelliği adlarını yerelleştirmek için gereken tek yer burasıdır.

Yerelleştirilmiş bir denetim geliştirdiğinizde, tür kitaplığı düzeyinde bir öznitelik olarak yerel kimliği ekleyin. Örneğin, Fransızca yerelleştirilmiş özellik adlarını içeren bir tür kitaplığı sağlamak istiyorsanız, ÖRNEK'inizin bir kopyasını yapın. IDL dosyası ve SAMPLEFR diyoruz. ıdl. Dosyaya yerel kimlik özniteliği ekleyin (Fransızca için yerel kimlik 0x040c'dir), aşağıdakilere benzer:

[!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]

SAMPLEFR'deki özellik adlarını değiştirin. IDL kendi Fransızca eşdeğerleri için, ve sonra MKTYPLIB kullanın. EXE Fransız türü kütüphane, SAMPLEFR üretmek için. Tlb.

Birden çok yerelleştirilmiş tür kitaplıkları oluşturmak için herhangi bir yerelleştirilmiş. Projeye IDL dosyaları ve otomatik olarak inşa edilecektir.

#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>Bir . ActiveX kontrol projenize IDL dosyası

1. Denetim projeniz açıkken, **Proje** menüsünde **Varolan Öğeyi Ekle'yi**tıklatın.

   **Varolan Öğe Ekle** iletişim kutusu görüntülenir.

1. Gerekirse, görüntülemek için sürücü ve dizin seçin.

1. Tür dosyası kutusunda Tüm **Dosyalar (\*\*. )** seçeneğini **belirleyin.**

1. Dosya listesi kutusunda, çift tıklatın. Projeye eklemek istediğiniz IDL dosyası.

1. Gerekli tüm eklemeyaptığınızda **Aç'ı** tıklatın. IDL dosyaları.

Dosyalar projeye eklendiğinden, projenin geri kalanı oluşturulunca oluşturulur. Yerelleştirilmiş tür kitaplıkları geçerli ActiveX denetim proje dizininde yer alır.

Kodunuz içinde, dahili özellik adları (genellikle İngilizce) her zaman kullanılır ve hiçbir zaman yerelleştirilmez. Buna denetim gönderme eşlemi, özellik değiştirme işlevleri ve özellik sayfası veri alışverişi kodunuzu içerir.

Yalnızca bir tür kitaplığı (. TLB) dosyası denetim uygulamasının kaynaklarına bağlı olabilir (. OCX) dosyası. Bu genellikle standart (genellikle İngilizce) adlarla yapılan sürümdür. Denetiminizin yerelleştirilmiş bir sürümünü sevk etmek için. OCX (zaten varsayılan bağlı olmuştur . TLB sürümü) ve . Uygun yerel bölge için TLB. Bu sadece anlamına gelir . OCX İngilizce sürümleri için gereklidir, doğru beri . TLB zaten ona bağlı olmuştur. Diğer yerel leştirilmiş ler için, yerelleştirilmiş tür kitaplığı da . Ocx.

Denetimistemcilerinizin yerelleştirilmiş tür kitaplığını bulabilmesi için, yerel e-özel kitaplığınızı kaydedin. TLB dosyası(lar) Windows sistem kayıt defterinin TypeLib bölümü altında. Bu amaçla [AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib) işlevinin üçüncü parametresi (normalde isteğe bağlı) sağlanır. Aşağıdaki örnek, ActiveX denetimi için Bir Fransız türü kitaplığını kaydeder:

[!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]

Denetiminiz kaydedildiğinde, `AfxOleRegisterTypeLib` işlev otomatik olarak belirtilen . TLB dosyası denetimle aynı dizinde yer eder ve Windows kayıt veritabanına kaydeder. Eğer . TLB dosyası bulunamadı, işlevin hiçbir etkisi yoktur.

## <a name="localizing-the-controls-user-interface"></a><a name="_core_localizing_the_control.92.s_user_interface"></a>Denetimin Kullanıcı Arabirimini Yerelleştirme

Denetimin kullanıcı arabirimini yerelleştirmek için, denetimin kullanıcı tarafından görülebilen tüm kaynaklarını (özellik sayfaları ve hata iletileri gibi) dile özgü kaynak DL'lerine yerleştirin. Daha sonra, kullanıcının yerel durumu için uygun DLL'yi seçmek için kapsayıcının ortam LocaleID özelliğini kullanabilirsiniz.

Aşağıdaki kod örneği, belirli bir yerel ayar için kaynak DLL'yi bulmak ve yüklemek için bir yaklaşım gösterir. Bu örnek için `GetLocalizedResourceHandle` çağrılan bu üye işlev ActiveX denetim sınıfınızın bir üye işlevi olabilir:

[!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]

Daha özel yerelleştirme sağlamak için, alt dil kimliğinin geçiş deyiminin her durumunda denetlenebileceğini unutmayın. Bu işlevin bir gösterimi `GetResourceHandle` için, MFC ActiveX denetimleri örnek [LOCALIZE](../overview/visual-cpp-samples.md)işlevibakın.

Denetim kendisini bir kapsayıcıya ilk yüklendiğinde, yerel kimliği almak için [COleControl::AmbientLocaleID'i](../mfc/reference/colecontrol-class.md#ambientlocaleid) arayabilir. Denetim daha sonra döndürülen yerel kimlik `GetLocalizedResourceHandle` değerini, uygun kaynak kitaplığını yükleyen işleve geçirebilir. Denetim, varsa, ortaya çıkan tutamacı [AfxSetResourceHandle'a](../mfc/reference/application-information-and-management.md#afxsetresourcehandle)geçirmelidir:

[!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]

Yukarıdaki kod örneğini COleControl geçersiz kılıntKoşulu gibi denetimin bir üye işlevine [yerleştirin::OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite). Buna ek olarak, *m_hResDLL* kontrol sınıfının bir üye değişkenolmalıdır.

Denetimin özellik sayfasını yerelleştirmek için benzer mantığı kullanabilirsiniz. Özellik sayfasını yerelleştirmek için, özellik sayfanızın uygulama dosyasına aşağıdaki örneğe benzer kod ekleyin [(COlePropertyPage geçersiz kılınması::OnSetPageSite):](../mfc/reference/colepropertypage-class.md#onsetpagesite)

[!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
