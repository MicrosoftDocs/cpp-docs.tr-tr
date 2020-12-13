---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: ActiveX denetimini yerelleştirme'
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
ms.openlocfilehash: 830fecd316b48f61da4f90136dd29455801ec725
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150221"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Yerelleştirme

Bu makalede, ActiveX denetim arabirimlerini yerelleştirme yordamları ele alınmaktadır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Bir ActiveX denetimini uluslararası bir pazara uyarlamak istiyorsanız, denetimi yerelleştirmek isteyebilirsiniz. Windows, Almanca, Fransızca ve Isveççe dahil olmak üzere varsayılan Ingilizce 'ye ek olarak birçok dili destekler. Bu, arabirimi yalnızca Ingilizce ise denetim için sorunlar oluşturabilir.

Genel olarak, ActiveX denetimleri çevresel LocaleID özelliğinde her zaman yerel ayarlarını temel almalıdır. Bunu yapmak için üç yol vardır:

- Çevresel LocaleID özelliğinin geçerli değerine bağlı olarak, her zaman isteğe bağlı kaynakları yükleyin. MFC ActiveX denetimleri örnek [yerelleştirilmesi](../overview/visual-cpp-samples.md) bu stratejiyi kullanır.

- Ortam LocaleID özelliğine bağlı olarak ilk denetim ınstanşedildiğinde kaynakları yükleyin ve diğer tüm örnekler için bu kaynakları kullanın. Bu makalede bu strateji gösterilmektedir.

    > [!NOTE]
    >  Bu işlem, gelecekteki örneklerin farklı yerel ayarlara sahip olması durumunda, bazı durumlarda düzgün çalışmaz.

- `OnAmbientChanged`Kapsayıcının yerel ayarı için uygun kaynakları dinamik olarak yüklemek için bildirim işlevini kullanın.

    > [!NOTE]
    >  Bu denetim için çalışır, ancak çevresel LocaleID özelliği değiştiğinde çalışma zamanı DLL 'SI kendi kaynaklarını dinamik olarak güncelleştirmeyecektir. Ayrıca, ActiveX denetimleri için çalışma zamanı dll 'Leri, kaynakları için yerel ayarı tespit etmek üzere iş parçacığı yerel ayarını kullanır.

Bu makalenin geri kalanında iki yerelleştirme stratejisi açıklanmaktadır. İlk strateji [denetimin programlama arabirimini](#_core_localizing_your_control.92.s_programmability_interface) (özellikler, Yöntemler ve olayların adları) yerelleştirir. İkinci strateji, kapsayıcının çevresel LocaleID özelliğini kullanarak [denetimin kullanıcı arabirimini yerelleştirir](#_core_localizing_the_control.92.s_user_interface). Denetim yerelleştirmesi gösterimi için bkz. MFC ActiveX denetimleri örnek [yerelleştirin](../overview/visual-cpp-samples.md).

## <a name="localizing-the-controls-programmability-interface"></a><a name="_core_localizing_your_control.92.s_programmability_interface"></a> Denetimin programlama arabirimini yerelleştirme

Denetimin programlama arabirimini (sizin denetiminizi kullanan uygulamalar yazan programcılar tarafından kullanılan arabirim) yerelleştirilirken, denetimin değiştirilmiş bir sürümünü oluşturmanız gerekir. Desteklemek istediğiniz her dil için IDL dosyası (denetim türü kitaplığı oluşturmak için bir komut dosyası). Bu, denetim özelliği adlarını yerelleştirmek için ihtiyaç duyduğunuz tek yerdir.

Yerelleştirilmiş bir denetim geliştirdiğinizde, yerel ayar KIMLIĞINI tür kitaplığı düzeyinde bir öznitelik olarak ekleyin. Örneğin, Fransızca yerelleştirilmiş özellik adları içeren bir tür kitaplığı sağlamak istiyorsanız, ÖRNEKLERINIZIN bir kopyasını oluşturun. Bu dosyayı çağırın ve SAMPLEFR. IDL. Dosyaya benzer bir yerel ayar KIMLIĞI özniteliği ekleyin (Fransız için yerel ayar KIMLIĞI 0x040c), aşağıdakine benzer:

[!code-cpp[NVC_MFC_AxLoc#1](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]

SAMPLEFR içindeki özellik adlarını değiştirin. IDL 'nin Fransızca eşdeğerlerine göre ve ardından MKTYPLIB.EXE kullanarak Fransızca tür kitaplığı, SAMPLEFR 'yi oluşturun. TLB.

Birden çok yerelleştirilmiş tür kitaplığı oluşturmak için herhangi bir yerelleştirilmiş ekleyebilirsiniz. IDL dosyaları projeye eklenir ve otomatik olarak oluşturulur.

#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>Eklemek için. IDL dosyasını ActiveX Denetim projenize

1. Denetim projeniz açıkken, **Proje** menüsünde, **Varolan öğe Ekle**' ye tıklayın.

   **Varolan öğe Ekle** iletişim kutusu görüntülenir.

1. Gerekirse, görüntülenecek sürücüyü ve dizini seçin.

1. **Dosya türü** kutusunda, **tüm dosyalar ( \* . \* )** öğesini seçin.

1. Dosya listesi kutusunda, öğesine çift tıklayın. Projeye eklemek istediğiniz IDL dosyası.

1. Gerekli olan tüm ' ı eklediğinizde **Aç** ' a tıklayın. IDL dosyaları.

Dosyalar projeye eklendiğinden, projenin geri kalanı derlendiklerinde oluşturulmazlar. Yerelleştirilmiş tür kitaplıkları geçerli ActiveX denetimi proje dizininde bulunur.

Kodunuzun içinde iç özellik adları (genellikle Ingilizce olarak) her zaman kullanılır ve hiç yerelleştirilmez. Bu, denetim dağıtım haritasını, özellik değişimi işlevlerini ve özellik sayfası Veri Değişim kodunuzu içerir.

Yalnızca bir tür kitaplığı (. TLB) dosyası, denetim uygulamasının kaynaklarına bağlanabilir (. OCX) dosyası. Bu, genellikle standartlaştırılmış (genellikle Ingilizce) adlara sahip olan sürümdür. Denetiminizin yerelleştirilmiş bir sürümünü teslim etmek için, ' i teslim etmeniz gerekir. OCX (zaten varsayılan olarak bir bağlanmıştır. TLB sürümü) ve. Uygun yerel ayar için TLB. Yani yalnızca. Doğru olduğundan, OCX, Ingilizce sürümler için gereklidir. TLB zaten kendisine bağlıydı. Diğer yerel ayarlarda, yerelleştirilmiş tür kitaplığının de ile birlikte gönderililmesi gerekir. Dosyasındaki.

Denetiminizin istemcilerinin yerelleştirilmiş tür kitaplığını bulaseçememesini sağlamak için, yerel ayarınızı kaydettirin. Windows sistem kayıt defteri 'nin TypeLib bölümünde TLB dosyaları. [AfxOleRegisterTypeLib](reference/registering-ole-controls.md#afxoleregistertypelib) işlevinin üçüncü parametresi (normal olarak isteğe bağlıdır), bu amaçla sağlanır. Aşağıdaki örnek, bir ActiveX denetimi için bir Fransızca tür kitaplığı kaydeder:

[!code-cpp[NVC_MFC_AxLoc#2](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]

Denetiminiz kayıtlıysa, `AfxOleRegisterTypeLib` işlev otomatik olarak belirtilen şekilde görünür. TLB dosyasını denetimiyle aynı dizinde ve Windows kayıt veritabanına kaydeder. . TLB dosyası bulunamadı, işlevin etkisi yok.

## <a name="localizing-the-controls-user-interface"></a><a name="_core_localizing_the_control.92.s_user_interface"></a> Denetimin kullanıcı arabirimini yerelleştirme

Bir denetimin kullanıcı arabirimini yerelleştirmek için denetimin tüm Kullanıcı görünür kaynaklarını (Özellik sayfaları ve hata iletileri gibi) dile özgü kaynak dll 'Lerine yerleştirin. Daha sonra kapsayıcının çevresel LocaleID özelliğini kullanarak kullanıcının yerel ayarı için uygun DLL 'yi seçebilirsiniz.

Aşağıdaki kod örneğinde, belirli bir yerel ayar için kaynak DLL 'sini bulma ve yükleme için bir yaklaşım gösterilmektedir. Bu örnek için çağrılan bu üye işlevi `GetLocalizedResourceHandle` , ActiveX denetim sınıfınızın bir üye işlevi olabilir:

[!code-cpp[NVC_MFC_AxLoc#3](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]

Daha özelleştirilmiş yerelleştirme sağlamak için, anahtar ifadesinin her durumunda alt dil KIMLIĞININ denetlenebileceğini unutmayın. Bu işlevin tanıtımı için, `GetResourceHandle` MFC ActiveX denetimleri örnek [yerelde](../overview/visual-cpp-samples.md)işlevine bakın.

Denetim önce kendisini bir kapsayıcıya yüklediğinde, yerel ayar KIMLIĞINI almak için [Cotacontrol:: AmbientLocaleID](reference/colecontrol-class.md#ambientlocaleid) ' ı çağırabilir. Daha sonra Denetim, döndürülen yerel ayar KIMLIĞI değerini `GetLocalizedResourceHandle` , uygun kaynak kitaplığını yükleyen işleve geçirebilir. Denetim, varsa, [AfxSetResourceHandle](reference/application-information-and-management.md#afxsetresourcehandle)'a sonuç olan tanıtıcıyı iletmelidir:

[!code-cpp[NVC_MFC_AxLoc#4](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]

Kod örneğini, bir denetimin üye işlevine ( [Copacontrol:: OnSetClientSite](reference/colecontrol-class.md#onsetclientsite)için geçersiz kılma gibi) yerleştirin. Ayrıca, *m_hResDLL* denetim sınıfının bir üye değişkeni olmalıdır.

Bir denetimin özellik sayfasını yerelleştirmek için de benzer mantığı kullanabilirsiniz. Özellik sayfasını yerelleştirmek için, özellik sayfanızın uygulama dosyasına ( [COlePropertyPage:: OnSetPageSite](reference/colepropertypage-class.md#onsetpagesite)geçersiz kılması) aşağıdaki örneğe benzer bir kod ekleyin:

[!code-cpp[NVC_MFC_AxLoc#5](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
