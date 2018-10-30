---
title: 'MFC ActiveX denetimleri: Gelişmiş konular | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- MFC ActiveX controls [MFC], accessing invisible dialog controls
- MFC ActiveX controls [MFC], advanced topics
- FireError method [MFC]
- MFC ActiveX controls [MFC], database classes
- MFC ActiveX controls [MFC], special keys
- PreTranslateMessage method [MFC]
- MFC ActiveX controls [MFC], parameterized property
- ThrowError method [MFC]
ms.assetid: e9e34abb-8e2d-461e-bb9c-a1aec5dcecbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: defc160b2b45185031160e0ba3dd553f8896e372
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204697"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC ActiveX Denetimleri: Gelişmiş Konular

Bu makalede, ActiveX denetimleri geliştirme ile ilgili gelişmiş konular ele alınmaktadır. Bu güncelleştirmeler şunlardır:

- [ActiveX denetimlerinde veritabanı sınıflarını kullanma](#_core_using_database_classes_in_activex_controls)

- [Parametreli özellik uygulama](#_core_implementing_a_parameterized_property)

- [ActiveX denetimi, hataları işleme](#_core_handling_errors_in_your_activex_control)

- [Özel anahtarları denetiminde işleme](#_core_handling_special_keys_in_your_control)

- [Çalışma zamanında görünmez iletişim kutusu denetimlerine erişme](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

##  <a name="_core_using_database_classes_in_activex_controls"></a> ActiveX denetimlerinde veritabanı sınıflarını kullanma

ActiveX denetim sınıfları sınıf kitaplığının bir parçası olduğundan, aynı yordamları ve veritabanı sınıfları kullanan MFC veritabanı sınıfları ActiveX denetimleri geliştirme için standart bir MFC uygulaması kullanılarak kuralları uygulayabilirsiniz.

MFC veritabanı sınıfları genel bir bakış için bkz: [MFC veritabanı sınıfları (DAO ve ODBC)](../data/mfc-database-classes-odbc-and-dao.md). MFC ODBC sınıfları makaleyi tanıtır ve MFC DAO sınıflarını ve ya da daha fazla ayrıntı için yönlendirir.

> [!NOTE]
>  Sihirbazlar ve Visual C++ ortamına DAO (DAO sınıflarına eklenmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, kullanmanızı önerir [OLE DB Şablonları](../data/oledb/ole-db-programming.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) yeni projeler için. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.

##  <a name="_core_implementing_a_parameterized_property"></a> Parametreli özellik uygulama

Bir parametreli özelliği (özellik dizisi olarak da adlandırılır), homojen bir değerler koleksiyonu denetimin tek bir özellik olarak kullanıma sunmak için kullanılan bir yöntemdir. Örneğin, parametreli bir özellik, bir dizi veya bir sözlük bir özellik olarak kullanıma sunmak için kullanabilirsiniz. Visual Basic'te, böyle bir özellik dizisi gösterimi kullanılarak erişilir:

[!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]

Parametreli bir özellik için Özellik Ekleme Sihirbazı'nı kullanın. Özellik Ekleme Sihirbazı'nı, bir çift Get/Set işlevlerin yukarıdaki gösterimini kullanarak bir özelliğe erişmek Denetim verin veya standart bir biçimde ekleyerek özelliğini uygular.

Yöntemlere ve özelliklere, parametreli özellikleri benzer ayrıca izin verilen parametre sayısı için bir sınır vardır. Parametreli özellikler söz konusu olduğunda, 15 parametreleriyle (bir parametre) özellik değerini depolamak için ayrılmış bir sınırdır.

Aşağıdaki yordamda, iki boyutlu bir tamsayı dizisi erişilebilen bir dizi olarak adlandırılan, parametreli bir özellik ekler.

#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak bir parametreli özellik eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Özellik Ekle**.

1. İçinde **özellik adı** kutusuna `Array`.

1. İçinde **özellik türü** kutusunda **kısa**.

1. İçin **uygulama** türüne tıklayın **Get/Set yöntemleri**.

1. İçinde **alma işlevi** ve **ayarlamak işlevi** kutuları, Al ve Ayarla işlevleri için benzersiz adlarını yazabilir veya varsayılan adı kabul edin.

9. Adlı bir parametreyi ekleyin *satır* (tür *kısa*) kullanarak **parametre adı** ve **parametre türü** kontrol eder.

10. Adlı ikinci bir parametre ekleyin *sütun* (tür *kısa*).

11. **Son**'a tıklayın.

### <a name="changes-made-by-the-add-property-wizard"></a>Tarafından yapılan değişiklikler Özellik Ekleme Sihirbazı

Özellik Ekleme Sihirbazı'nı bir özel özellik eklediğinizde, control sınıfı üst bilgisi için değişiklikleri yapar (. H) ve uygulama (. Dosyaların CPP).

Aşağıdaki satırları denetim sınıfa eklenir. H dosyası:

[!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]

Bu kod adlı iki işlev bildirir `GetArray` ve `SetArray` özelliğine erişirken bir özel satır ve sütun isteği kullanıcıya izin verin.

Ayrıca, Özellik Ekleme Sihirbazı'nı aşağıdaki satırları denetim sınıfı uygulaması içinde bulunan denetim dağıtım eşlemesi ekler (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]

Son olarak, uygulamaları `GetArray` ve `SetArray` işlevleri sonuna eklenir. CPP dosyasına. Çoğu durumda Get işlevi özelliğinin değerini döndürecek şekilde değiştirir. Set işlevi genellikle önce veya sonra özellik değişikliklerinin yürütülecek kodu içerir.

Bu özellik kullanışlı olması bir denetim sınıf türünde iki boyutlu dizi üye değişkeni bildirip **kısa**, parametreli özellik değerlerini depolamak için. Ardından Get işlevi, parametreler ile belirtildiği gibi uygun satır ve sütun depolanan değer döndürecek şekilde değiştirin ve satır ve sütun parametreleri tarafından başvurulan değer kümesi işleviyle değiştirmek.

##  <a name="_core_handling_errors_in_your_activex_control"></a> ActiveX denetimi, hataları işleme

Denetimi hata koşullarını ortaya çıkarsa, Denetim kapsayıcıya hatayı bildirin gerekebilir. Hatalar, hata oluştuğu durumu raporlama için iki yöntem vardır. Hata oluşursa bir özelliğin içinde almak veya ayarlamak, işlev veya bir OLE Otomasyon yöntemin uygulanmasını içinde denetim çağırmalıdır [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror), hangi sinyalleri denetim kullanıcıya bir hata oluştu. Diğer herhangi bir anda hata meydana gelirse, denetimin çağırmalıdır [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror), stok bir hata olayı tetikler.

Gerçekleşen hata türünü belirtmek için denetim bir hata koduna geçmelidir `ThrowError` veya `FireError`. Bir hata kodu bir 32-bit değere sahip bir OLE durum kodudur. Mümkün olduğunda, bir hata kodu kodları OLECTL içinde tanımlı standart kümesini seçin. H üst bilgi dosyası. Aşağıdaki tabloda bu kodları özetlenmektedir.

### <a name="activex-control-error-codes"></a>ActiveX denetimi hata kodları

|Hata|Açıklama|
|-----------|-----------------|
|CTL_E_ILLEGALFUNCTIONCALL|Geçersiz işlev çağrısı|
|CTL_E_OVERFLOW|taşma|
|CTL_E_OUTOFMEMORY|Bellek yetersiz|
|CTL_E_DIVISIONBYZERO|Sıfıra bölme|
|CTL_E_OUTOFSTRINGSPACE|Dize alanı yetersiz|
|CTL_E_OUTOFSTACKSPACE|Yığın alanı yetersiz|
|CTL_E_BADFILENAMEORNUMBER|Hatalı dosya adı veya numarası|
|CTL_E_FILENOTFOUND|Dosya bulunamadı|
|CTL_E_BADFILEMODE|Hatalı dosya modu|
|CTL_E_FILEALREADYOPEN|Dosya zaten açık|
|CTL_E_DEVICEIOERROR|Cihaz G/Ç hatası|
|CTL_E_FILEALREADYEXISTS|Dosya zaten var.|
|CTL_E_BADRECORDLENGTH|Hatalı kayıt uzunluğu|
|CTL_E_DISKFULL|Disk dolu|
|CTL_E_BADRECORDNUMBER|Geçersiz kayıt numarası|
|CTL_E_BADFILENAME|Hatalı dosya adı|
|CTL_E_TOOMANYFILES|Çok fazla sayıda dosya|
|CTL_E_DEVICEUNAVAILABLE|Cihaz kullanılamıyor|
|CTL_E_PERMISSIONDENIED|İzin reddedildi|
|CTL_E_DISKNOTREADY|Disk hazır değil|
|CTL_E_PATHFILEACCESSERROR|Yol/dosya erişim hatası|
|CTL_E_PATHNOTFOUND|Yol bulunamadı|
|CTL_E_INVALIDPATTERNSTRING|Geçersiz desen dizesi|
|CTL_E_INVALIDUSEOFNULL|NULL geçersiz kullanımı|
|CTL_E_INVALIDFILEFORMAT|Dosya biçimi geçersiz|
|CTL_E_INVALIDPROPERTYVALUE|Geçersiz özellik değeri|
|CTL_E_INVALIDPROPERTYARRAYINDEX|Geçersiz özellik dizisi dizini|
|CTL_E_SETNOTSUPPORTEDATRUNTIME|Çalışma zamanında desteklenmeyen ayarlayın|
|CTL_E_SETNOTSUPPORTED|Desteklenmeyen set (salt okunur özelliği)|
|CTL_E_NEEDPROPERTYARRAYINDEX|Need özelliği dizi dizini|
|CTL_E_SETNOTPERMITTED|İzin kümesi|
|CTL_E_GETNOTSUPPORTEDATRUNTIME|Çalışma zamanında desteklenmeyen|
|CTL_E_GETNOTSUPPORTED|Desteklenmiyor (salt yazılır özellik) alma|
|CTL_E_PROPERTYNOTFOUND|Özellik bulunamadı|
|CTL_E_INVALIDCLIPBOARDFORMAT|Geçersiz Pano biçimi|
|CTL_E_INVALIDPICTURE|Geçersiz resim|
|CTL_E_PRINTERERROR|Yazıcı hatası|
|CTL_E_CANTSAVEFILETOTEMP|TEMP dosyası kaydedilemiyor|
|CTL_E_SEARCHTEXTNOTFOUND|Arama metni bulunamadı|
|CTL_E_REPLACEMENTSTOOLONG|Değişiklik çok uzun|

Gerekirse, CUSTOM_CTL_SCODE makrosu standart kodları biri tarafından kapsanmıyor bir koşul için bir özel hata kodunu tanımlamak için kullanın. Bu makro parametresi 1000 arasında bir tamsayı olmalıdır ve 32767 dahil. Örneğin:

[!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]

VBX varolan bir denetimi değiştirmek için bir ActiveX denetimi oluşturuyorsanız, ActiveX denetimi hata kodları VBX denetimi hata kodları uyumlu olduğundan emin olmak için kullanır ve aynı sayısal değerlerini tanımlayın.

##  <a name="_core_handling_special_keys_in_your_control"></a> Özel anahtarları denetiminde işleme

Bazı durumlarda, bazı tuş bileşimlerini özel bir şekilde işlemek isteyebilirsiniz; Örneğin, çok satırlı metin ENTER tuşuna basıldığında yeni bir satır kutusu denetim veya Düzen grubu arasında taşıma ekleme denetimleri yönlü zaman tuşu basılı kimliği.

Temel sınıf ActiveX denetiminizin ise `COleControl`, geçersiz kılabilirsiniz [CWnd::PreTranslateMessage](../mfc/reference/cwnd-class.md#pretranslatemessage) kapsayıcı bunları işlemeden önce iletileri işlemek için. Bu tekniği kullanarak, her zaman dönüş **TRUE** geçersiz kılmada iletisini işlemek, `PreTranslateMessage`.

Aşağıdaki kod örneği tek yönlü anahtarları ilgili tüm iletileri işleme olası yolunu gösterir.

[!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]

Bir ActiveX denetimi için klavye arabirimleri işleme ile ilgili daha fazla bilgi için ActiveX SDK belgelerine bakın.

##  <a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a> Çalışma zamanında görünmez iletişim kutusu denetimlerine erişme

Hiçbir kullanıcı arabirimi ve çalışma zamanında görünmez iletişim kutusu denetimleri oluşturabilirsiniz. Bir görünmez iletişim kutusu ve kullanmak için çalışma zamanında ActiveX denetimi eklerseniz, [CWnd::GetDlgItem](../mfc/reference/cwnd-class.md#getdlgitem) erişim denetimi için denetim düzgün çalışmaz. Bunun yerine, aşağıdaki tekniklerden birini denetimini temsil eden bir nesne elde etmek üzere kullanmanız gerekir:

- Ekleme üye değişkeni Sihirbazı'nı kullanarak seçin **denetim değişkeni** ve denetim kimliğini seçin. Üye değişken adını girin ve denetimin sarmalayıcı sınıfı olarak seçin **denetim türü**.

     veya

- Bir yerel değişkeni ve alt iletişim öğesi olarak bildirin. Aşağıdakine benzer bir kod ekleyin (`CMyCtrl` sarmalayıcı sınıftır IDC_MYCTRL1 olduğu denetimin kimliği):

   [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

