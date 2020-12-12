---
description: 'Daha fazla bilgi edinin: MFC programı veya denetim kaynağı ve üstbilgi dosyaları'
title: MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], MFC source and header
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
ms.openlocfilehash: dfe20b2e458db72a14c9ccc78df6f481442b72b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137858"
---
# <a name="mfc-program-or-control-source-and-header-files"></a>MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları

Oluşturduğunuz proje için belirlediğiniz seçeneklere bağlı olarak, Visual Studio 'da bir MFC projesi oluşturduğunuzda aşağıdaki dosyalar oluşturulur. Örneğin, projeniz yalnızca bir iletişim kutusu tabanlı proje veya sınıf oluşturursanız *ProjName* DLG. cpp ve *ProjName* DLG. h dosyalarını içerir.

Bu dosyaların tümü, *ProjName* dizininde ve Çözüm Gezgini Içindeki üstbilgi dosyaları (. h dosyaları) klasöründe veya kaynak dosyaları (. cpp dosyaları) klasöründe bulunur.

|Dosya adı|Açıklama|
|---------------|-----------------|
|*ProjName*. h|Program veya DLL için ana ekleme dosyası. `#include`Diğer üstbilgi dosyaları için tüm genel sembolleri ve yönergeleri içerir. `CPrjnameApp`Sınıfını öğesinden türetir `CWinApp` ve bir `InitInstance` üye işlevi bildirir. Bir denetim için, `CPrjnameApp` sınıf öğesinden türetilir `COleControlModule` .|
|*ProjName*. cpp|Ana program kaynak dosyası. Sınıfından türetilen sınıfının bir nesnesi oluşturur `CPrjnameApp` `CWinApp` ve `InitInstance` üye işlevini geçersiz kılar.<br /><br /> Yürütülebilir dosyalar için `CPrjnameApp::InitInstance` birkaç şey vardır. Belgeler ve görünümler arasında bağlantı işlevi sunan belge şablonlarını kaydeder; ana çerçeve penceresi oluşturur; ve boş bir belge oluşturur (veya bir belge, uygulama için komut satırı bağımsız değişkeni olarak belirtilmişse bir belgeyi açar).<br /><br /> Dll 'Ler ve ActiveX (eski adıyla OLE) denetimleri için, `CProjNameApp::InitInstance` çağırarak ve çağrısı yaparak denetimin nesne fabrikasını OLE ile kaydeder `COleObjectFactory::RegisterAll` `AfxOLEInit` . Ayrıca, `CProjNameApp::ExitInstance` bir **AfxOleTerm** çağrısıyla denetimi bellekten kaldırmak için üye işlevi kullanılır.<br /><br /> Bu dosya Ayrıca ve işlevlerini uygulayarak Windows kayıt veritabanındaki denetimi kaydeder ve kaydını siler `DllRegisterServer` `DllUnregisterServer` .|
|*ProjName* CTRL. h, *ProjName* CTRL. cpp|Sınıfını bildirin ve uygulayın `CProjnameCtrl` . `CProjnameCtrl` , öğesinden türetilir `COleControl` ve bazı üye işlevlerinin iskelet uygulamaları, denetimi Başlatan, çizmiş ve seri hale getirmeyi (yükleme ve kaydetme) tanımlanır. İleti, olay ve dağıtım haritaları da tanımlanmıştır.|
|*ProjName* DLG. cpp, *ProjName* DLG. h|İletişim kutusu tabanlı bir uygulama seçerseniz oluşturulur. Dosyalar, iletişim kutusu başlatmak ve iletişim `CProjnameDlg` kutusu veri değişimi (DDX) gerçekleştirmek için iskelet üye işlevlerini, adlandırılmış ve içerir. İletişim kutusu sınıfınız, *ProjName*. cpp yerine bu dosyalara de yerleştirilir.|
|Dlproxy. cpp, Dlproxy. h|İletişim kutusu tabanlı bir programda, ana iletişim kutusu için projenin Otomasyon proxy sınıfı için uygulama ve üstbilgi dosyası. Bu yalnızca otomasyon desteğini seçtiyseniz kullanılır.|
|*ProjName* Doc. cpp, *ProjName* Doc. h|Belgeyi `CProjnameDoc` başlatmak, bir belgeyi seri hale getirmek (kaydetmek ve yüklemek) ve hata ayıklama tanılamayı uygulamak için, adlandırılmış ve çatı üyesi işlevleri içeren belge sınıfını türetir ve uygulayın.|
|*ProjName* set. h/. cpp|Veritabanını destekleyen ve kayıt kümesi sınıfını içeren bir program oluşturursanız oluşturulur.|
|*ProjName* görünümü. cpp, *ProjName* görünümü. h|`CProjnameView`Belge verilerini görüntülemek ve yazdırmak için kullanılan adlı görünüm sınıfını türetebilir ve uygulayın. `CProjnameView`Sınıfı AŞAĞıDAKI MFC sınıflarından birinden türetilir:<br /><br />- [CEditView](../../mfc/reference/ceditview-class.md)<br />- [CFormView](../../mfc/reference/cformview-class.md)<br />- [CRecordView](../../mfc/reference/crecordview-class.md)<br />- [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)<br />- [CTreeView](../../mfc/reference/ctreeview-class.md)<br />- [CListView](../../mfc/reference/clistview-class.md)<br />- [CRichEditView](../../mfc/reference/cricheditview-class.md)<br />- [CScrollView](../../mfc/reference/cscrollview-class.md)<br />- [CView](../../mfc/reference/cview-class.md)<br />- [CHTMLView](../../mfc/reference/chtmlview-class.md)<br />- [CHTMLEditView](../../mfc/reference/chtmleditview-class.md)<br /><br /> Projenin görünüm sınıfı, görünümü çizmek ve hata ayıklama tanılamayı uygulamak için iskelet üye işlevlerini içerir. Yazdırma desteğini etkinleştirdiyseniz, yazdırma, yazdırma ayarı ve baskı önizleme komut iletileri için ileti eşleme girdileri eklenir. Bu girişler, temel görünüm sınıfında karşılık gelen üye işlevlerini çağırır.|
|*ProjName* PropPage. h, *ProjName* PropPage. cpp|Sınıfını bildirin ve uygulayın `CProjnamePropPage` . `CProjnamePropPage` öğesinden türetilir `COlePropertyPage` ve bir iskelet üye işlevi, `DoDataExchange` veri değişimi ve doğrulama uygulamak için sağlanır.|
|IPframe. cpp, IPFRAME. h|Uygulama sihirbazının **Otomasyon seçenekleri** sayfasında Mini-Server veya Full-Server seçeneği işaretliyse oluşturulur (adım 3 ' ün 6. adımında). Dosyalar, sunucu bir kapsayıcı program tarafından etkinleştirildiğinde kullanılan **Cinplaceframe** adlı yerinde çerçeve pencere sınıfını türetebilir ve uygular.|
|MainFrm. cpp, MainFrm. h|Cana **bilgisayar** sınıfını [CFRAMEWND](../../mfc/reference/cframewnd-class.md) (SDI uygulamaları Için) veya [CMDIFRAMEWND](../../mfc/reference/cmdiframewnd-class.md) (MDI uygulamaları için) öğesinden türetebilirsiniz. **Canabilgisayar** sınıfı, uygulama Sihirbazı 'Nın **uygulama seçenekleri** sayfasında (adım 4 ' ün 6. adımında) ilgili seçenekler seçiliyse, araç çubuğu düğmelerinin ve durum çubuğunun oluşturulmasını işler. **Cana bilgisayar** kullanımı hakkında bilgi için bkz. [Uygulama sihirbazı tarafından oluşturulan Frame-Window sınıfları](../../mfc/frame-window-classes-created-by-the-application-wizard.md).|
|Childfrm. cpp, childfrm. h|[Cmdictepdwnd](../../mfc/reference/cmdichildwnd-class.md)'Ten **CChildFrame** sınıfını türet. **CChildFrame** sınıfı, MDI belge çerçevesi pencereleri için kullanılır. MDI seçeneğini belirlerseniz bu dosyalar her zaman oluşturulur.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)<br>
[ATL programı veya denetim kaynağı ve üstbilgi dosyaları](atl-program-or-control-source-and-header-files.md)<br>
[CLR projeleri](files-created-for-clr-projects.md)
