---
title: MFC uygulamaları oluşturmak için işlem dizisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], developing
ms.assetid: 6973c714-fe20-48c6-926b-de88356b3a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1bafcec75643c292a887b54de1b852609dd251c0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383815"
---
# <a name="sequence-of-operations-for-building-mfc-applications"></a>MFC Uygulamaları Oluşturmak için İşlem Dizisi
Aşağıdaki tabloda, MFC Uygulama geliştirirken, genellikle uygulayabilir genel sıra açıklanmaktadır.  
  
### <a name="sequence-for-building-an-application-with-the-framework"></a>Uygulama Çerçevesi ile oluşturma sırası  
  
|Görev|Bunu|Framework mu|  
|----------|------------|------------------------|  
|İskelet bir uygulama oluşturun.|Çalıştırma [MFC Uygulama Sihirbazı'nı](../mfc/reference/mfc-application-wizard.md). Seçenekler sayfalarında istediğiniz seçenekleri belirtin. Bir COM bileşeni, kapsayıcı ya da her ikisini de uygulama yapma seçenekleri içerir; Otomasyonu ekleme; ve uygulamayı veritabanı uyumlu hale getirme.|MFC Uygulama Sihirbazı'nı uygulama, belge, Görünüm ve çerçeve pencereleri için kaynak dosyaları dahil olmak üzere bir iskelet uygulama dosyalarını oluşturur; kaynak dosyası; bir proje dosyası; ve diğer tüm uyarlanmış, belirtimleri.|  
|Bkz. satır kendi kodunuzu eklemeden ne framework ve MFC Uygulama Sihirbazı'nı sunar.|İskelet uygulama oluşturun ve Visual c++'ta çalıştırın.|Birçok standart çalışan iskelet uygulama türetilen **dosya**, **Düzenle**, **Görünüm**, ve **yardımcı** çerçeveden menü komutları. MDI uygulamaları için de tam olarak işlevsel bir Windows menüsü almak ve çerçeve oluşturma, düzenleme ve MDI alt pencereleri yok etme yönetir.|  
|Uygulamanızın kullanıcı arabirimi oluşturmak.|Visual C++ kullanma [kaynak düzenleyicileri](../windows/resource-editors.md) görsel olarak uygulamanın kullanıcı arabiriminde düzenlemek için:<br /><br /> -Menüleri oluşturun.<br />-Hızlandırıcıları tanımlayın.<br />-İletişim kutuları oluşturma.<br />-Oluşturun ve bit eşlemler, simgeler ve İmleçler düzenleyin.<br />-, MFC Uygulama Sihirbazı tarafından oluşturulan araç düzenleyin.<br />-Oluşturun ve diğer kaynakları düzenleyin.<br /><br /> İletişim kutuları da iletişim kutusu Düzenleyicisi'nde test edebilirsiniz.|MFC Uygulama Sihirbazı tarafından oluşturulan varsayılan kaynak dosyası ihtiyacınız olan kaynakları çoğunu sağlar. Visual C++, var olan kaynakların düzenleyebilir ve kolayca ve görsel olarak yeni kaynakları ekleyebilirsiniz olanak tanır.|  
|Menüleri işleyici işlevlerine eşleyin.|Kullanım **olayları** düğmesini [Özellikler penceresini](/visualstudio/ide/reference/properties-window) işleyici işlevleri kodunuzda menüleri ve Hızlandırıcıları bağlanmak için.|Özellikler penceresini ileti eşleme girişi ve boş işlev şablonları belirtin ve birçok el ile kodlama görevleri yöneten kaynak dosyalarına ekler.|  
|İşleyici kodunuzu yazın.|Sınıf Görünümü doğrudan kod kaynak kod düzenleyicisinde atlamak için kullanın. İşleyici işlevleri için kod doldurun. Sınıf görünümü kullanarak ve projeye kod ekleme sihirbazları hakkında daha fazla bilgi için bkz: [kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md).|Sınıf Görünümü Düzenleyicisi'ni açar, boş işlevi şablona kaydırır ve sizin için imleci konumlandırır.|  
|Araç çubuğu düğmeleri komutları eşleyin.|Düğme uygun komut kimliği atayarak her, araç çubuğunda bir menü veya Hızlandırıcı komutu eşleme|Çizim, etkinleştirme, devre dışı bırakma, denetleme ve araç çubuğu düğmelerini visual diğer yönlerini framework denetler.|  
|İşleyici işlevleri sınayın.|Program yeniden oluşturun ve, işleyicilerin doğru şekilde çalıştığını sınamak için yerleşik hata ayıklama araçlarını kullanın.|Adım veya nasıl, işleyicilerini çağırma görmek için kod boyunca izleme. İşleyici kod doldurduktan, işleyicileri komutları yürütmek. Framework otomatik olarak menü öğeleri ve değil işlenir araç çubuğu düğmelerini devre dışı bırakır.|  
|Ekleme [iletişim kutuları](../mfc/dialog-boxes.md).|İletişim şablonu kaynakları ile iletişim kutusu Düzenleyicisi tasarlayın. Daha sonra bir iletişim kutusu sınıfı ve iletişim kutusunu işleyen kodu oluşturun.|Framework'te iletişim kutusu yönetir ve kullanıcı tarafından girilen bilgileri alınıyor kolaylaştırır.|  
|Başlatma, doğrulayın ve iletişim kutusu verilerini alma.|Ayrıca, iletişim kutusunun denetimleri başlatıldı ve doğrulandı şeklini tanımlayabilirsiniz. Üye değişkenleri iletişim sınıfına ekleyin ve iletişim kutusu denetimlerine eşlemek için Visual Studio'yu kullanın. Kullanıcı verileri girerken her denetim için uygulanacak doğrulama kurallarını belirtin. İsterseniz, kendi özel doğrulama sağlar.|Framework'te iletişim kutusu başlatma ve doğrulama yönetir. Kullanıcı geçersiz bilgiler girerse, framework bir ileti kutusu görüntüler ve verileri yeniden girmek kullanıcı olanak tanır.|  
|Ek sınıfları oluşturun.|Sınıf Görünümü ek belge, Görünüm ve çerçeve penceresi sınıfları MFC Uygulama Sihirbazı tarafından otomatik olarak oluşturulanların dışındaki oluşturmak için kullanın. Ek veritabanı kayıt kümesi sınıfları, iletişim kutusu sınıfları ve benzeri oluşturabilirsiniz. (Sınıf görünümü ile MFC sınıfları türetilmemiş sınıfları oluşturabilirsiniz.)|Sınıf Görünümü bu sınıfları, kaynak dosyalarına ekler ve bunlar işlemek herhangi bir komut kendi bağlantılarını tanımlamanıza yardımcı olur.|  
|Kullanıma hazır bileşenleri uygulamanıza ekleyin.|Kullanım `New Item dialog box` öğeleri çeşitli eklemek için.|Uygulamanıza tümleştirmek ve iş büyük bir bölümünü kaydetmek bu öğeler kolaydır.|  
|Belge sınıfı uygulayın.|Uygulamaya özgü belge sınıfı veya sınıfları uygulayın. Veri yapıları tutmak için üye değişkenleri ekleyin. Verileri için bir arabirim sağlamak için üye işlevleri ekleyin.|Framework zaten belge veri dosyalarıyla etkileşim kurmayı bilir. Bunu açabilir ve belge dosyaları kapatın, okuma ve belgenin veri yazma ve diğer kullanıcı arabirimleri tanıtıcı. Belgenin veri nasıl yönetilebilir odaklanabilirsiniz.|  
|Kaydet, Aç, uygulama ve komut olarak kaydedin.|Belgenin için kod yazma `Serialize` üye işlevi.|İletişim kutuları için framework görüntüler **açık**, **kaydetmek**, ve **Kaydet** komutlarını **dosya** menüsü. Yazar ve okur geri belirtilen veri biçimi kullanarak bir belge, `Serialize` üye işlevi.|  
|View sınıfı uygulayın.|Belgelerinizi için karşılık gelen bir veya daha fazla görünümü sınıfları uygulayın. Sınıf Görünümü kullanıcı arabirimiyle eşlenmiş görünümün üye işlevlerini uygular. Çeşitli [CView](../mfc/reference/cview-class.md)-türetilen sınıflar da dahil, kullanılabilir [CListView](../mfc/reference/clistview-class.md) ve [CTreeView](../mfc/reference/ctreeview-class.md).|Çerçeve bir belge ve kendi görünüm arasındaki ilişkiyi çoğunu yönetir. Görünümün üye işlevleri görünümün belge görüntüsünü ekran veya yazdırılan sayfa üzerinde oluşturulacak ve belgenin veri yapılarını yanıt düzenleme komutları kullanıcı olarak güncelleştirmek için erişim.|  
|Varsayılan yazdırmayı geliştirin.|Birden çok yazdırma desteklemeniz gerekiyorsa, görünümü üye işlevleri geçersiz kılar.|Framework destekleyen **yazdırma**, **sayfa yapısı**, ve **Baskı Önizleme** komutlarını **dosya** menüsü. Bu belgeyi birden çok sayfaya ayırmak nasıl bildirmeniz gerekir.|  
|Kaydırma ekleyin.|View sınıfı veya sınıflardan kaydırma desteklemeniz gerekiyorsa, türetilen [CScrollView](../mfc/reference/cscrollview-class.md).|Görünüm penceresi çok küçük olduğunda görünüm kaydırma çubukları otomatik olarak ekler.|  
|Form görünümleri oluşturun.|View sınıfı veya sınıflardan görünümlerinizi iletişim şablonu kaynaklardaki temel almasını istiyorsanız, türetilen [Cformview'yu](../mfc/reference/cformview-class.md).|Görünüm iletişim şablon kaynağı denetimleri göstermek için kullanır. Kullanıcı denetimden denetim görünümünde sekmesinde.|  
|Veritabanı formları oluşturun.|Bir form tabanlı veri erişimi uygulama istiyorsanız, görünüm sınıfından türetilen [CRecordView](../mfc/reference/crecordview-class.md) (için ODBC programlama).|Görünüm bir form görünümü gibi çalışır, ancak kendi denetimler alanları için bağlı bir [CRecordset](../mfc/reference/crecordset-class.md) bir veritabanı tablosu temsil eden nesne. MFC veri denetimleri ve kayıt kümesi arasında sizin için taşır.|  
|Basit bir metin düzenleyicisi oluşturun.|Görünümünüzü basit bir metin düzenleyicisi olmasını istiyorsanız, görünüm sınıfı veya sınıftan türetilen [CEditView](../mfc/reference/ceditview-class.md) veya [CRichEditView](../mfc/reference/cricheditview-class.md).|İşlevler, Pano desteği ve dosya giriş/çıkış düzenleme görünümü sağlar. `CRichEditView` stilde metin sağlar.|  
|Bölümlendirici pencereler ekleyin.|Pencere bölme desteklemek istiyorsanız, ekleme bir [CSplitterWnd](../mfc/reference/csplitterwnd-class.md) SDI çerçeve penceresi ya da MDI alt pencere nesnesi ve pencerenin içinde takma [OnCreateClient](../mfc/reference/cframewnd-class.md#oncreateclient) üye işlevi.|Framework kaydırma çubukları yanındaki Bölümlendirici kutusu denetimleri sağlar ve birden çok bölmelere görünümünüzü bölme yönetir. Kullanıcı bir pencere ayırır, framework oluşturur ve ek görünüm nesneleri belgeye ekler.|  
|Derleme, test ve uygulamanızda hata ayıklama.|Derleme, test ve uygulamanızda hata ayıklama için Visual C++ tesis kullanın.|Visual C++, derleme, bağlantı ve diğer seçenekleri ayarlamanıza olanak sağlar. Ayrıca, kaynak kodu ve sınıf yapısı Gözat sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE uygulamaları oluşturmak için işlem dizisi](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [ActiveX denetimleri oluşturmak için işlem dizisi](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [Veritabanı uygulamaları oluşturmak için işlem dizisi](../mfc/sequence-of-operations-for-creating-database-applications.md)   
 [Framework'te Derleme](../mfc/building-on-the-framework.md)

