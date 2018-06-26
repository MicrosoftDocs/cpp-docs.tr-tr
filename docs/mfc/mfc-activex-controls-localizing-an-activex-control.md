---
title: 'MFC ActiveX denetimleri: ActiveX denetimini yerelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- LocaleID
- AfxOleRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- localization, ActiveX controls
- MFC ActiveX controls [MFC], localizing
- LocaleID ambient property [MFC]
- LOCALIZE sample [MFC]
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9a6495c23695f8cdedf45fbdd7cbc915b96873e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929614"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Yerelleştirme
Bu makalede ActiveX denetim arabirimleri yerelleştirme için yordamlar açıklanmaktadır.  
  
 Uluslararası pazar bir ActiveX denetimine uyum isterseniz, Denetim yerelleştirme isteyebilirsiniz. Windows varsayılan İngilizce, Almanca, Fransızca ve İsveççe dahil olmak üzere ek olarak birçok dili destekler. Onun arabirim sadece İngilizce'dir, bu denetimi için sorun oluşturabilir.  
  
 Genel olarak, ActiveX denetimlerini kendi yerel ortam LocaleID özelliği temel her zaman almalısınız. Bunu yapmak için üç yolu vardır:  
  
-   Her zaman geçerli değerine göre ortam LocaleID özelliği isteğe bağlı kaynakları yükleyin. MFC ActiveX denetimleri örnek [LOCALIZE](../visual-cpp-samples.md) bu strateji kullanır.  
  
-   İlk denetim ortam LocaleID özelliğine dayalı instanced kaynakları yükleme ve bu kaynakları diğer tüm örnekler için kullanın. Bu makalede bu stratejiyi gösterir.  
  
    > [!NOTE]
    >  Gelecekteki örnekleri farklı yerel ayarlara varsa bu bazı durumlarda, çalışmaz.  
  
-   Kullanım `OnAmbientChanged` kapsayıcının yerel ayar için doğru kaynakları dinamik olarak yüklemek için bildirim işlevi.  
  
    > [!NOTE]
    >  Bu denetim için çalışır, ancak ortam LocaleID özelliği değiştiğinde çalışma zamanı DLL kendi kaynaklarını dinamik olarak güncelleştirilmez. Ayrıca, çalışma zamanı DLL'ler ActiveX denetimleri için iş parçacığı yerel ayar kaynaklarını yerel belirlemek için kullanın.  
  
 Bu makalenin geri kalanında iki yerelleştirme stratejilerini açıklar. İlk stratejisi [denetimin programlama arabirimi yerelletirilmesi](#_core_localizing_your_control.92.s_programmability_interface) (özellikleri, yöntemleri ve olayları adları). İkinci stratejisi [denetimin kullanıcı arabirimi yerelletirilmesi](#_core_localizing_the_control.92.s_user_interface), kapsayıcının ortam LocaleID özelliği kullanarak. MFC ActiveX denetimleri örneği denetimini yerelleştirme tanıtımı için bkz: [LOCALIZE](../visual-cpp-samples.md).  
  
##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a> Denetimin programlama arabirimi yerelleştirme  
 Denetimin programlama arabirimi (denetiminizi kullanan uygulamaları yazma programcıları tarafından kullanılan arabirim) yerelleştirme, Denetim değiştirilmiş bir sürümünü oluşturmanız gerekir. IDL, desteklemek istediğiniz her dil için (Denetim tür kitaplığı oluşturmak için bir komut dosyası) dosyası. Bu, denetim özellik adları yerelleştirme gereken tek yerdir.  
  
 Yerelleştirilmiş denetimi geliştirirken, yerel ayar kimliği türü kitaplığı düzeyinde bir öznitelik olarak içerir. Örneğin, Fransızca yerelleştirilmiş özellik adlarıyla bir tür kitaplığı sağlamak istiyorsanız, ÖRNEĞİNİZİ bir kopyasını oluşturun. IDL dosya ve SAMPLEFR çağırın. IDL. Yerel ayar kimliği özniteliği (Fransızca için yerel ayar kimliği: 0x040c) dosyasına eklemek için aşağıdakilere benzer:  
  
 [!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]  
  
 SAMPLEFR özellik adlarını değiştirin. IDL kendi Fransızca eşdeğerleri ve MKTYPLIB kullanın. Fransızca üretmek için EXE kitaplığı, SAMPLEFR yazın. TLB.  
  
 Birden çok yerelleştirilmiş tür kitaplıklarının oluşturmak için herhangi bir yerelleştirilmiş ekleyebilirsiniz. Projeye IDL dosyaları ve otomatik olarak oluşturulacak.  
  
#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>Eklemek için bir. ActiveX denetimi projenize IDL dosyası  
  
1.  Projenizle denetim açık **proje** menüsünde tıklatın **varolan öğeyi Ekle**.  
  
     **Varolan öğeyi Ekle** iletişim kutusu görüntülenir.  
  
2.  Gerekirse, sürücü ve görüntülemek için dizini seçin.  
  
3.  İçinde **dosya türü** kutusunda **tüm dosyalar (\*.\*)** .  
  
4.  Dosya liste kutusunu çift tıklatın. IDL dosyası projeye eklemek istediğiniz.  
  
5.  Tıklatın **açık** zaman eklediğiniz tüm gerekli. IDL dosyaları.  
  
 Dosyaları projeye eklenmiş olduğundan, bunlar projenin kalanı yapılandırıldığında oluşturulacaktır. Yerelleştirilmiş tür kitaplıklarının geçerli ActiveX denetimi proje dizininde bulunur.  
  
 Kodunuz içinde (genellikle İngilizce dilinde) iç özellik adları her zaman kullanılır ve hiçbir zaman yerelleştirilmiştir. Bu denetim gönderme eşlemesi, özellik exchange işlevleri ve özellik sayfası veri exchange kodunuzu içerir.  
  
 Yalnızca bir tür kitaplığı (. TLB) dosya denetim uygulaması kaynakları bağlı (. OCX) dosyası. Bu genellikle standartlaştırılmış ile sürümdür (genellikle İngilizce) adları. Yerelleştirilmiş bir sürümün sevk gerekir, denetimin sevk etmek. OCX (hangi zaten varsayılan bağlandı. TLB sürüm) ve. TLB uygun yerel ayar için. Bu, yalnızca anlamına gelir. OCX İngilizce sürümleri için bu yana doğru gereklidir. TLB zaten kendisine bağlandı. Diğer ülkeler için yerelleştirilmiş tür kitaplığı da ile birlikte gelen gerekir. OCX.  
  
 İstemcileri denetiminizin yerelleştirilmiş tür kitaplığı bulabilmeniz için yerel ayarlara özgü kaydedin. TLB dosyaları Windows Sistem kayıt defteri TypeLib bölümü altında. Üçüncü parametrenin (normalde isteğe bağlı) [AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib) işlevi bu amaç için sağlanır. Aşağıdaki örnek, bir ActiveX denetimini Fransızca tür kitaplığının kaydeder:  
  
 [!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]  
  
 Denetim kaydedildiğinde `AfxOleRegisterTypeLib` işlevi otomatik olarak arar için belirtilen. TLB dosyası denetimi ile aynı dizinde ve Windows kayıt veritabanında kaydeder. Varsa. TLB dosya bulunamadı, işlevi hiçbir etkisi olmaz.  
  
##  <a name="_core_localizing_the_control.92.s_user_interface"></a> Denetimin kullanıcı arabirimi yerelleştirme  
 Bir denetimin kullanıcı arabirimi yerelleştirme için tüm denetim kullanıcıya görünen kaynakları (örneğin, özellik sayfaları ve hata iletileri) dile özgü kaynak DLL'leri yerleştirin. Kullanıcının yerel ayarı için uygun DLL seçmek için kapsayıcının ortam LocaleID özelliği sonra kullanabilirsiniz.  
  
 Aşağıdaki kod örneğinde bulmak ve belirli bir yerel kaynak DLL'si yüklemek için bir yaklaşım gösterilmektedir. Adlı bu üye işlevi `GetLocalizedResourceHandle` Bu örnekte, ActiveX denetimi sınıfınızın üye işlevi olabilir:  
  
 [!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]  
  
 Alt dili kimliği daha özelleştirilmiş yerelleştirme sağlamak için switch deyimi, her durumda iade edilemedi unutmayın. Bu işlev tanıtımı için bkz: `GetResourceHandle` işlevinde MFC ActiveX denetimleri örnek [LOCALIZE](../visual-cpp-samples.md).  
  
 Bir kapsayıcıya, kendisini ilk denetimi yüklediğinde, çağırabilirsiniz [COleControl::AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid) yerel ayar kimliğini almak için Denetimin ardından döndürülen yerel ayar kimliği değerine geçirebilirsiniz `GetLocalizedResourceHandle` uygun kaynak kitaplığı yükler işlevi. Denetim elde edilen tanıtıcı varsa geçirmelisiniz için [AfxSetResourceHandle](../mfc/reference/application-information-and-management.md#afxsetresourcehandle):  
  
 [!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]  
  
 Üye işlevi geçersiz kılma gibi denetimin Yukarıdaki kod örneğini yerleştirin [COleControl::OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite). Ayrıca, *m_hResDLL* control sınıfının üye değişkeni olmalıdır.  
  
 Bir denetimin özellik sayfası yerelleştirme için benzer mantığı kullanabilirsiniz. Özellik sayfası yerelleştirme için aşağıdaki örneğe benzer bir kod özelliği sayfanızın uygulama dosyasına ekleyin (geçersiz kılma içinde [COlePropertyPage::OnSetPageSite](../mfc/reference/colepropertypage-class.md#onsetpagesite)):  
  
 [!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

