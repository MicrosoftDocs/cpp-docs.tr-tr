---
title: "MFC programı veya Denetim Kaynağı ve başlık dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], MFC source and header
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 81964c410f01505ef49c75b51ef2629daed2f6ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-program-or-control-source-and-header-files"></a>MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları
Oluşturduğunuz proje için belirttiğiniz seçeneklere bağlı olarak Visual Studio'da bir MFC projesi oluşturduğunuzda, aşağıdaki dosyaları oluşturulur. Örneğin, projenizi içeren *Projname*dlg.cpp ve *Projname*dlg.h dosyaları yalnızca proje iletişim tabanlı ya da sınıf oluşturursanız.  
  
 Tüm bu dosyaları bulunan *Projname* dizin ve başlık dosyaları (.h dosyaları) klasör ya da Çözüm Gezgini kaynak dosyaları (.cpp) klasöründe.  
  
|Dosya adı|Açıklama|  
|---------------|-----------------|  
|*PROJNAME*.h|Program ya da DLL için ana içerme dosyası. Tüm genel simgeler içeriyor ve `#include` diğer üstbilgi dosyaları için yönergeleri. Bunu türetilen `CPrjnameApp` sınıfıyla `CWinApp` ve bildiren bir `InitInstance` üye işlevi. Bir denetim için `CPrjnameApp` sınıfı türetilir `COleControlModule`.|  
|*PROJNAME*.cpp|Ana program kaynak dosyası. Sınıfın bir nesnesi oluşturur `CPrjnameApp`, türetilen `CWinApp`ve geçersiz kılmalar `InitInstance` üye işlevi.<br /><br /> Yürütülebilir dosyalar için `CPrjnameApp::InitInstance` birkaç işlemi yapar. Belgeler ve görünümler arasında bir bağlantı olarak hizmet şablonların kaydeder; bir ana çerçeve penceresi oluşturur; ve boş bir belge oluşturur (veya uygulama için komut satırı bağımsız değişkeni olarak belirtilmişse, bir belge açılır).<br /><br /> DLL'ler ve (önceki adıyla OLE) ActiveX denetimleri için `CProjNameApp::InitInstance` çağırarak ile OLE denetimin nesne üreteci kaydeder `COleObjectFactory::RegisterAll` ve çağrıda `AfxOLEInit`. Ayrıca, üye fonksiyonu `CProjNameApp::ExitInstance` çağrısıyla bellek denetiminden kaldırmak için kullanılan **AfxOleTerm**.<br /><br /> Bu dosya ayrıca kaydeder ve Windows kayıt veritabanını denetiminde uygulayarak kaydını siler `DllRegisterServer` ve `DllUnregisterServer` işlevleri.|  
|*PROJNAME*ctrl.h, *Projname*ctrl.cpp|Bildirme ve uygulama `CProjnameCtrl` sınıfı. `CProjnameCtrl`türetilmiş `COleControl`, ve bazı üye işlevleri, iskelet uygulamalarını başlatmak, çizme ve seri tanımlanır (yükleme ve kaydetme) denetimi. İleti, olay ve eşlemeleri dağıtma de tanımlanır.|  
|*PROJNAME*dlg.cpp, *Projname*dlg.h|İletişim tabanlı bir uygulama seçerseniz oluşturulur. Dosyaları türetmek ve adlı iletişim sınıf uygulama `CProjnameDlg`ve bir iletişim kutusu başlatılmaya ve iletişim kutusu veri değişimi (DDX) gerçekleştirmek için iskelet üye işlevlerini içerir. Hakkında iletişim sınıfınızı yerine, bu dosyaları da yerleştirilir *Projname*.cpp.|  
|Dlgproxy.cpp, Dlgproxy.h|Bir iletişim tabanlı program, uygulama ve üstbilgi dosyasında projenin Otomasyon proxy sınıfı için ana iletişim için. Bu, yalnızca Otomasyon desteği seçtiyseniz kullanılır.|  
|*PROJNAME*doc.cpp, *Projname*doc.h|Türetirseniz ve adlı belgeyi sınıf uygulama `CProjnameDoc`ve bir belgeyi başlatmak, seri hale getirmek için iskelet üye işlevleri dahil (kaydetme ve yükleme) bir belge ve uygulama tanılama hata ayıklama.|  
|*PROJNAME*set.h/.cpp|Bir veritabanı destekler ve kayıt kümesi sınıfı içeren bir program oluşturursanız, oluşturulan.|  
|*PROJNAME*view.cpp, *Projname*view.h|Türetilen ve adlı görünüm sınıf uygulama `CProjnameView`, görüntülemek ve belge verileri yazdırmak için kullanılır. `CProjnameView` Sınıfı aşağıdaki MFC sınıfları birinden elde edilmiştir:<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [Cformview'yu](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> Projenin görünüm sınıfı Görünüm ve uygulama tanılama hata ayıklama çizmek için iskelet üye işlevlerini içerir. Yazdırma desteğini etkinleştirdiyseniz, ardından ileti eşleme girişleri yazdırma, yazdırma kurulumu için eklenir ve önizleme komut iletileri yazdırın. Bu girişler temel view sınıfında karşılık gelen üye işlevleri çağırma.|  
|*PROJNAME*PropPage.h, *Projname*PropPage.cpp|Bildirme ve uygulama `CProjnamePropPage` sınıfı. `CProjnamePropPage`türetilmiş `COlePropertyPage` ve bir iskelet üye fonksiyonu `DoDataExchange`, veri değişimi ve doğrulaması uygulamak için sağlanır.|  
|IPframe.cpp, IPframe.h|Uygulama Sihirbazı'nda 's Mini sunucu veya tam sunucu seçeneği seçili değilse oluşturulan **Otomasyon seçenekleri** sayfa (adım 3 / 6). Dosyaları türetmek ve adlı yerinde çerçeve penceresi sınıf uygulama **CInPlaceFrame**, sunucunun bir kapsayıcı program tarafından etkinleştirilen yerinde olduğunda kullanılır.|  
|Mainfrm.cpp, Mainfrm.h|Türetilen **CMainFrame** ya da sınıfından [CFrameWnd](../mfc/reference/cframewnd-class.md) (için SDI uygulamaları) veya [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) (için MDI uygulamaları). **CMainFrame** sınıfı, karşılık gelen seçenekleri Uygulama Sihirbazı'nda 's seçtiyseniz oluşturulmasını araç çubuğu düğmeleri ve durum çubuğu işler **uygulama seçenekleri** sayfa (4. adım 6). Kullanma hakkında bilgi için **CMainFrame**, bkz: [çerçeve penceresi sınıfları tarafından oluşturulan Uygulama Sihirbazı'nı](../mfc/frame-window-classes-created-by-the-application-wizard.md).|  
|Childfrm.cpp, Childfrm.h|Türetilen **CChildFrame** sınıfıyla [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md). **CChildFrame** sınıfı MDI belge çerçeve pencereleri için kullanılır. MDI seçeneğini belirlerseniz bu dosyaları her zaman oluşturulur.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ projeleri için oluşturulan dosya türleri](../ide/file-types-created-for-visual-cpp-projects.md)   
 [ATL programı veya Denetim Kaynağı ve başlık dosyaları](../ide/atl-program-or-control-source-and-header-files.md)   
 [CLR projeleri](../ide/files-created-for-clr-projects.md)