---
title: MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], MFC source and header
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
ms.openlocfilehash: a46fedc9f9bbc888e9b59d2ed313eaf7146394ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321325"
---
# <a name="mfc-program-or-control-source-and-header-files"></a>MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları

Oluşturduğunuz proje için belirlediğiniz seçeneklere bağlı olarak Visual Studio'da bir MFC projesi oluşturduğunuzda, aşağıdaki dosyalar oluşturulur. Örneğin, projenizi içeren *Projname*dlg.cpp ve *Projname*dlg.h dosyaları yalnızca bir iletişim kutusu tabanlı proje ya da sınıf oluşturun.

Bu dosyaların tümünün bulunan *Projname* dizin ve üst bilgi dosyaları (.h) klasör ya da Çözüm Gezgini'nde klasörü kaynak dosyaları (.cpp).

|Dosya adı|Açıklama|
|---------------|-----------------|
|*PROJNAME*.h|Program veya DLL için ana içerme dosyası. Tüm genel simgeler içeriyor ve `#include` yönergeleri için diğer üst bilgi dosyaları. Türetilen `CPrjnameApp` gelen sınıfı `CWinApp` ve bildiren bir `InitInstance` üye işlevi. Bir denetim için `CPrjnameApp` sınıfı türetilen `COleControlModule`.|
|*PROJNAME*.cpp|Ana program kaynak dosyası. Sınıfın bir nesnesi oluşturur `CPrjnameApp`, türetilen `CWinApp`ve geçersiz kılmaları `InitInstance` üye işlevi.<br /><br /> Yürütülebilir dosyaları için `CPrjnameApp::InitInstance` çeşitli işlemler yapar. Bu belge şablonları, belgeleri ve görünümleri arasında bir bağlantı işlevi görür; kaydeder bir ana çerçeve penceresi oluşturur. ve boş bir belge oluşturur (veya uygulama için komut satırı bağımsız değişkeni olarak belirtilmişse, bir belgeyi açar).<br /><br /> DLL'ler ve (eski adı OLE) ActiveX denetimleri için `CProjNameApp::InitInstance` çağırarak OLE ile denetimin nesne üreteci kaydettirir `COleObjectFactory::RegisterAll` ve çağrıda `AfxOLEInit`. Ayrıca, üye işlevi `CProjNameApp::ExitInstance` bellek çağrısıyla denetiminden kaldırmak için kullanılan **AfxOleTerm**.<br /><br /> Bu dosya ayrıca kaydeder ve uygulayarak Windows kayıt defteri veritabanında denetim kaydını `DllRegisterServer` ve `DllUnregisterServer` işlevleri.|
|*PROJNAME*ctrl.h, *Projname*ctrl.cpp|Bildirme ve uygulama `CProjnameCtrl` sınıfı. `CProjnameCtrl` türetilen `COleControl`, ve bazı üye işlevleri, çatı uygulamalarını başlatmak, çizme ve seri hale getirme tanımlanır (yükleme ve kaydetme) denetimi. İleti ve olay gönderme eşlemeleri de tanımlanır.|
|*PROJNAME*dlg.cpp, *Projname*dlg.h|İletişim tabanlı bir uygulama seçtiğinizde oluşturulur. Dosyaları türetilir ve adlı iletişim kutusu sınıfı uygulamak `CProjnameDlg`ve bir iletişim kutusu başlatılmaya ve iletişim kutusu veri değişimi (DDX) gerçekleştirmek için iskelet üye işlevleri içerir. Hakkında iletişim sınıfınızı de yerine bu dosyalar da yerleştirilir *Projname*.cpp.|
|Dlgproxy.cpp, Dlgproxy.h|Bir iletişim kutusu tabanlı programı, uygulama ve üst bilgi dosyasında ana iletişim kutusu için proje Otomasyon proxy sınıfı. Bu, yalnızca Otomasyon desteği seçtiyseniz kullanılır.|
|*PROJNAME*doc.cpp, *Projname*doc.h|Türetilir ve adlı belge sınıfı uygulamak `CProjnameDoc`ve bir belgeyi başlatın, seri hale getirmek için iskelet üye işlevleri içerir (kaydetme ve yükleme) bir belge ve hata ayıklama ve tanılama uygulayın.|
|*PROJNAME*set.h/.cpp|Bir veritabanı destekler ve kayıt kümesi sınıfı içeren bir program oluşturursanız oluşturuldu.|
|*PROJNAME*view.cpp, *Projname*view.h|Türetilir ve adlı görünüm sınıfı uygulamak `CProjnameView`, görüntülemek ve belge verilerini yazdırmak için kullanılır. `CProjnameView` Sınıfı aşağıdaki MFC sınıflarının birinden türetilir:<br /><br />- [CEditView](../../mfc/reference/ceditview-class.md)<br />- [CFormView](../../mfc/reference/cformview-class.md)<br />- [CRecordView](../../mfc/reference/crecordview-class.md)<br />- [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)<br />- [CTreeView](../../mfc/reference/ctreeview-class.md)<br />- [CListView](../../mfc/reference/clistview-class.md)<br />- [CRichEditView](../../mfc/reference/cricheditview-class.md)<br />- [CScrollView](../../mfc/reference/cscrollview-class.md)<br />- [CView](../../mfc/reference/cview-class.md)<br />- [CHTMLView](../../mfc/reference/chtmlview-class.md)<br />- [CHTMLEditView](../../mfc/reference/chtmleditview-class.md)<br /><br /> Projenin görünümü sınıf görünümü ve hata ayıklama ve tanılama uygulamanıza çizmek için iskelet üye işlevleri içerir. Yazdırma desteği etkinleştirilirse, ardından ileti eşlemesi girişleri için yazdırma, Yazdırma Kurulumu eklenir ve önizleme komut iletilerini yazdırma. Bu girişlerin karşılık gelen üye işlevleri temel görünümü sınıfında çağırın.|
|*PROJNAME*PropPage.h, *Projname*PropPage.cpp|Bildirme ve uygulama `CProjnamePropPage` sınıfı. `CProjnamePropPage` türetilen `COlePropertyPage` ve bir çatı üye işlevini `DoDataExchange`, veri değişimi ve doğrulaması uygulamak için sağlanır.|
|IPframe.cpp, IPframe.h|Mini sunucu veya tam sunucu seçeneği Uygulama Sihirbazı'nda kişinin seçtiyseniz oluşturulan **Otomasyon seçenekleri** sayfa (adım 3 / 6). Dosyaları türetilir ve adlı yerinde çerçeve penceresini sınıf uygulama **CInPlaceFrame**, sunucunun bir kapsayıcı program tarafından etkinleştirilen bir yerde olduğunda kullanılır.|
|Mainfrm.cpp, Mainfrm.h|Türetilen **CMainFrame** ya da bir sınıftan [CFrameWnd](../../mfc/reference/cframewnd-class.md) (için SDI uygulamaları) veya [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) (için MDI uygulamaları). **CMainFrame** sınıfı işler araç çubuğu düğmeleri ve durum çubuğu oluşturma Uygulama Sihirbazı'nda kişinin ilgili seçenekleri seçtiyseniz **uygulama seçenekleri** sayfa (adım 4 / 6). Kullanma hakkında bilgi için **CMainFrame**, bkz: [çerçeve pencere sınıfları tarafından oluşturulan Uygulama Sihirbazı'nı](../../mfc/frame-window-classes-created-by-the-application-wizard.md).|
|Childfrm.cpp, Childfrm.h|Türetilen **CChildFrame** gelen sınıfı [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md). **CChildFrame** sınıfı MDI belge çerçeve pencereleri için kullanılır. MDI seçeneğini belirlerseniz bu dosyaları her zaman oluşturulur.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Projeleri için Oluşturulan Dosya Türleri](file-types-created-for-visual-cpp-projects.md)<br>
[ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları](atl-program-or-control-source-and-header-files.md)<br>
[CLR projeleri](files-created-for-clr-projects.md)
