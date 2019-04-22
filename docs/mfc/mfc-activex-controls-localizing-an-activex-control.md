---
title: 'MFC ActiveX denetimleri: ActiveX denetimini yerelleştirme'
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
ms.openlocfilehash: 13c8ff545763017b01685e012ab2d497eaf7084a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767554"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX denetimleri: ActiveX denetimini yerelleştirme

ActiveX denetim arabirimleri yerelleştirme için yordamlar anlatılmaktadır.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

ActiveX denetimi bir Uluslararası pazara uyarlamak isterseniz, Denetim yerelleştirmek isteyebilirsiniz. Windows varsayılan İngilizce, Almanca, Fransızca ve İsveç dili gibi ek olarak çok sayıda dili destekler. Arabirimi yalnızca İngilizce olarak ise bu denetim için sorunları sunabilir.

Genel olarak, ActiveX denetimleri, yerel ayar LocaleID ortam özelliği temel her zaman. Bunu yapmak için üç yolu vardır:

- Her zaman geçerli LocaleID ortam özelliği değerine göre isteğe bağlı kaynakları yükleyin. MFC ActiveX denetimleri örnek [YERELLEŞTİRİN](../overview/visual-cpp-samples.md) bu strateji kullanır.

- İlk denetim, ortam LocaleID özelliğini temel alarak örnekli yükleme kaynakları ve diğer tüm örnekleri için bu kaynakları kullanın. Bu makalede, bu strateji gösterilmektedir.

    > [!NOTE]
    >  Farklı yerel ayarlar gelecekteki örneğiniz varsa bu bazı durumlarda, çalışmaz.

- Kullanım `OnAmbientChanged` bildirim işlevini kapsayıcının yerel ayar için doğru kaynakları dinamik olarak yüklenemiyor.

    > [!NOTE]
    >  Bu denetim için çalışır, ancak LocaleID ortam özelliği değiştiğinde çalışma zamanı DLL kendi kaynaklarını dinamik olarak güncelleştirmez. Ayrıca, çalışma zamanı dll ActiveX denetimleri için yerel kaynaklarını belirlemek için iş parçacığı yerel ayarı kullanın.

Bu makalenin geri kalanında, iki yerelleştirme stratejilerini açıklar. İlk strateji [denetimin programlama arabirimi yerelletirilmesi](#_core_localizing_your_control.92.s_programmability_interface) (özellikleri, yöntemleri ve olayları adları). İkinci strateji [denetimin kullanıcı arabirimi yerelletirilmesi](#_core_localizing_the_control.92.s_user_interface), kapsayıcının ortam LocaleID özelliğini kullanma. MFC ActiveX denetimleri örnek denetimi yerelleştirme gösterimi için bkz. [YERELLEŞTİRİN](../overview/visual-cpp-samples.md).

##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a> Denetimin programlama arabirimi yerelleştirme

Denetimin programlama arabirimi (denetiminiz kullanan uygulamalar yazma programcılar tarafından kullanılan arabirimi) yerelleştirme, denetimin değiştirilmiş bir sürümünü oluşturmanız gerekir. IDL dosyası (denetimi tür kitaplığına oluşturmaya yönelik bir komut dosyası) desteklemeyi planladığınız her dil için. Bu, denetim özelliği adları yerelleştirmek için gereken tek yerdir.

Yerelleştirilmiş bir denetim geliştirdiğinizde, tür kitaplığı düzeyinde özniteliği olarak yerel ayar kimliği içerir. Örneğin, bir tür kitaplığı ile Fransızca yerelleştirilmiş özellik adları sağlamak istiyorsanız, örneğin bir kopyasını olun. IDL dosyası ve SAMPLEFR çağırın. IDL. Bir yerel ayar kimliği öznitelik (0x040c Fransızca için yerel ayar kimliği'dir) dosyasına eklemek için aşağıdakilere benzer:

[!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]

Özellik adlarını alınan SAMPLEFR değiştirin. IDL kendi Fransızca eşdeğerleri ve MKTYPLIB kullanın. Fransızca üretmek için EXE kitaplığı SAMPLEFR yazın. TLB.

Birden fazla yerelleştirilmiş tür kitaplığı oluşturmak için tüm yerelleştirilmiş ekleyebilirsiniz. IDL dosyaları projeye ve otomatik olarak oluşturulur.

#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>Eklemek için bir. ActiveX denetimi projenize IDL dosyası

1. Projenizle denetimi açık **proje** menüsünde tıklatın **varolan öğeyi Ekle**.

   **Varolan öğeyi Ekle** iletişim kutusu görüntülenir.

1. Gerekirse, sürücü ve görüntülemek için dizini seçin.

1. İçinde **dosya türü** kutusunda **tüm dosyalar (\*.\*)** .

1. Dosya liste kutusuna çift tıklayın. IDL dosyası projeye eklemek istediğiniz.

1. Tıklayın **açık** zaman eklediğiniz tüm gerekli. IDL dosyaları.

Dosya projeye eklenmemiş olduğundan, bunlar projenin geri kalanını oluşturulduğunda oluşturulur. Yerelleştirilmiş tür kitaplıklarını geçerli ActiveX denetimi proje dizininde yer alır.

Kodunuz içinde (genellikle, İngilizce) iç özellik adları her zaman kullanılır ve hiçbir zaman yerelleştirilmiş. Bu denetim dağıtım eşlemesi, özellik değişim işlevleri ve özellik sayfası veri exchange kodunuzu içerir.

Yalnızca bir tür kitaplığı (. TLB) dosya denetim uygulamasının kaynaklara bağlı (. OCX) dosyası. Genellikle bu sürümle standartlaştırılmış budur (genellikle, İngilizce) adları. Denetiminiz ihtiyacınız göndermeye yerelleştirilmiş bir sürümünü oluşturmak için. (Bu varsayılan olarak önceden bağlandı. OCX TLB sürüm) ve. TLB uygun yerel ayar için. Bu, yalnızca anlamına gelir. OCX İngilizce sürümleri için doğru beri gereklidir. TLB zaten kendisine bağlandı. Diğer yerel ayar için yerelleştirilmiş bir tür kitaplığı da ile birlikte gelen gerekir. OCX.

İstemciler denetiminizin yerelleştirilmiş tür kitaplığı bulabileceğinizden emin olmak için yerel ayara özgü kaydedin. Windows Sistem kayıt defterini TypeLib bölümünde TLB dosyaları. Öğesinin üçüncü parametresi (normalde isteğe bağlı) [AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib) işlevi, bu amaç için sağlanır. Aşağıdaki örnek, bir ActiveX denetimi için Fransızca tür kitaplığını kaydeder:

[!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]

Denetiminiz kaydedildiğinde `AfxOleRegisterTypeLib` işlevi otomatik olarak arar belirtilen. Denetim ile aynı dizinde TLB dosyası ve Windows kayıt defteri veritabanındaki kaydeder. Varsa. TLB dosya bulunamazsa, işlev hiçbir etkisi olmaz.

##  <a name="_core_localizing_the_control.92.s_user_interface"></a> Denetimin kullanıcı arabirimi yerelleştirme

Bir denetimin kullanıcı arabirimi yerelleştirmek için tüm denetim kullanıcıya görünen kaynakları (örneğin, özellik sayfaları ve hata iletileri) dile özgü kaynak DLL'leri yerleştirin. Kapsayıcının ortam LocaleID özelliği daha sonra kullanıcının yerel ayar için uygun DLL seçmek için de kullanabilirsiniz.

Aşağıdaki kod örneği bulun ve belirli bir yerel ayar için kaynak DLL'ini yükler için bir yaklaşım gösterilmektedir. Bu üye, çağrılan işlev, `GetLocalizedResourceHandle` Bu örnekte, bir ActiveX denetimi sınıfının üye işlevi olabilir:

[!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]

Alt dili kimliği daha özel yerelleştirme sağlamak için switch deyimi, her durumda iade edilemedi unutmayın. Bu işlev bir gösterimi için bkz. `GetResourceHandle` işlevinde MFC ActiveX denetimleri örnek [YERELLEŞTİRİN](../overview/visual-cpp-samples.md).

Denetimin ilk kez kendisi bir kapsayıcıya yüklediğinde çağırabilirsiniz [COleControl::AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid) yerel ayar kimliğini almak için Denetimin ardından döndürülen yerel ayar kimliği değeri geçirebilirsiniz `GetLocalizedResourceHandle` uygun kaynak kitaplığı yükleyen bir işlev. Denetim varsa, sonuçta elde edilen tanıtıcı geçmelidir için [AfxSetResourceHandle](../mfc/reference/application-information-and-management.md#afxsetresourcehandle):

[!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]

Yukarıdaki kod örneğinde, bir üye işlev geçersiz kılma gibi denetimin yerleştirin [COleControl::OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite). Ayrıca, *m_hResDLL* denetim sınıfının bir üye değişkeni olmalıdır.

Bir denetimin özellik sayfası yerelleştirmek için de aynı mantığı kullanabilirsiniz. Özellik sayfasını yerelleştirmek için aşağıdaki örneğe benzer bir kod özelliği sayfanızın uygulama dosyasına ekleyin (geçersiz kılma olarak [COlePropertyPage::OnSetPageSite](../mfc/reference/colepropertypage-class.md#onsetpagesite)):

[!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)
