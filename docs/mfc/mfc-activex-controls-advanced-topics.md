---
title: 'MFC ActiveX Denetimleri: Gelişmiş Konular'
ms.date: 09/12/2018
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
ms.openlocfilehash: 5ae29ed40d9cc5b78945fb9846a36d6b5a0b27d7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225039"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC ActiveX Denetimleri: Gelişmiş Konular

Bu makalede, ActiveX denetimleri geliştirmeyle ilgili gelişmiş konular ele alınmaktadır. Bunlara

- [ActiveX denetimlerinde veritabanı sınıflarını kullanma](#_core_using_database_classes_in_activex_controls)

- [Parametreli özellik uygulama](#_core_implementing_a_parameterized_property)

- [ActiveX Denetiinizdeki hataları işleme](#_core_handling_errors_in_your_activex_control)

- [Denetimdeki özel anahtarları işleme](#_core_handling_special_keys_in_your_control)

- [Çalışma zamanında görünmeyen Iletişim kutusu denetimlerine erişme](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

## <a name="using-database-classes-in-activex-controls"></a><a name="_core_using_database_classes_in_activex_controls"></a>ActiveX denetimlerinde veritabanı sınıflarını kullanma

ActiveX denetim sınıfları sınıf kitaplığının bir parçası olduğundan, MFC veritabanı sınıflarını kullanan ActiveX denetimleri geliştirmek için, veritabanı sınıflarını standart bir MFC uygulamasında kullanmaya yönelik aynı yordamları ve kuralları uygulayabilirsiniz.

MFC veritabanı sınıflarına genel bir bakış için bkz. [MFC veritabanı sınıfları (DAO ve ODBC)](../data/mfc-database-classes-odbc-and-dao.md). Bu makalede hem MFC ODBC sınıfları hem de MFC DAO sınıfları tanıtılmakta ve üzerinde daha fazla ayrıntı için sizi yönlendirmaktadır.

> [!NOTE]
> DAO, Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir. Visual C++ ortamı ve sihirbazları DAO 'YU desteklemez (DAO sınıfları dahil edilip kullanmaya devam edebilirsiniz). Microsoft, yeni projeler için [OLE DB şablonlarını](../data/oledb/ole-db-programming.md) veya [ODBC 'yi ve MFC 'yi](../data/odbc/odbc-and-mfc.md) kullanmanızı önerir. Yalnızca var olan uygulamaları korumak için DAO kullanmanız gerekir.

## <a name="implementing-a-parameterized-property"></a><a name="_core_implementing_a_parameterized_property"></a>Parametreli özellik uygulama

Parametreli bir Özellik (bazen Özellik dizisi olarak adlandırılır), denetimin tek bir özelliği olarak bir homojen değer koleksiyonunu kullanıma sunma yöntemidir. Örneğin, bir dizi veya sözlüğü bir özellik olarak göstermek için parametreli bir özellik kullanabilirsiniz. Visual Basic, bu tür bir özelliğe dizi gösterimi kullanılarak erişilir:

[!code-vb[NVC_MFC_AxVb#1](codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]

Parametreli bir özellik uygulamak için Özellik Ekleme Sihirbazı 'nı kullanın. Özellik Ekleme Sihirbazı, denetim kullanıcısının yukarıdaki gösterimi veya standart biçimde özelliğe erişmesine izin veren bir dizi get/set işlevi ekleyerek özelliğini uygular.

Yöntemlere ve özelliklere benzer şekilde parametreli özellikler de izin verilen parametrelerin sayısıyla sınırlıdır. Parametreli özellikler söz konusu olduğunda, sınır 15 parametretir (özellik değerini depolamak için bir parametre ayrılmış olarak).

Aşağıdaki yordam, iki boyutlu tamsayılar dizisi olarak erişilebilen Array adlı parametreli bir özellik ekler.

#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı 'Nı kullanarak parametreli bir özellik eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Özellik Ekle**' ye tıklayın.

1. **Özellik adı** kutusuna yazın `Array` .

1. **Özellik türü** kutusunda, öğesini seçin **`short`** .

1. **Uygulama** türü Için, **get/set yöntemleri**' ne tıklayın.

1. **Get işlevi** ve **işlevi ayarla** kutularında, Get ve set işlevleriniz için benzersiz adlar yazın veya varsayılan adları kabul edin.

1. **Parametre adı** ve **parametre türü** denetimlerini kullanarak *satır* (tür *Short*) adlı bir parametre ekleyin.

1. *Column* adlı ikinci bir parametre ekleyin ( *Short*yazın).

1. **Son**'a tıklayın.

### <a name="changes-made-by-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı tarafından yapılan değişiklikler

Özel bir özellik eklediğinizde Özellik Ekleme Sihirbazı denetim sınıfı üst bilgisinde değişiklik yapar (. H) ve uygulama (. CPP) dosyaları.

Aşağıdaki satırlar denetim sınıfına eklenir. H dosyası:

[!code-cpp[NVC_MFC_AxUI#35](codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]

Bu kod, adlı iki işlev bildirir `GetArray` ve `SetArray` kullanıcının özelliğe erişirken belirli bir satır ve sütun istemesine izin verir.

Ayrıca Özellik Ekleme Sihirbazı, denetim sınıfı uygulamasında bulunan denetim dağıtım eşlemesine aşağıdaki satırları ekler (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#36](codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]

Son olarak, `GetArray` ve `SetArray` işlevlerinin uygulamaları öğesinin sonuna eklenir. CPP dosyası. Çoğu durumda, özelliğin değerini döndürmek için Get işlevini değiştirirsiniz. Set işlevi genellikle, özellik değişikliklerinden önce veya sonra yürütülmesi gereken kodu içerir.

Bu özelliğin yararlı olması için, **`short`** parametreli özellik değerlerini depolamak için türündeki Control sınıfında iki boyutlu bir dizi üye değişkeni bildirebilirsiniz. Daha sonra, parametreler tarafından gösterildiği gibi, uygun satırda ve sütunda depolanan değeri döndürmek için Get işlevini değiştirebilirsiniz ve satır ve sütun parametreleri tarafından başvurulan değeri güncelleştirmek için set işlevini değiştirebilirsiniz.

## <a name="handling-errors-in-your-activex-control"></a><a name="_core_handling_errors_in_your_activex_control"></a>ActiveX Denetiinizdeki hataları işleme

Denetimde hata koşulları oluşursa, hatayı denetim kapsayıcısına rapor etmeniz gerekebilir. Hatanın gerçekleştiği duruma bağlı olarak, hataları raporlamak için iki yöntem vardır. Hata bir özelliğin get veya set işlevi içinde ya da bir OLE Automation yönteminin uygulanması içinde oluşursa, denetim kullanıcıya bir hata oluştuğunu işaret eden [Cotacontrol:: ThrowError](reference/colecontrol-class.md#throwerror)öğesini çağırmalıdır. Hata başka bir zamanda oluşursa, denetim, bir stok hata olayını harekete geçen [Colicontrol:: FireError](reference/colecontrol-class.md#fireerror)öğesini çağırmalıdır.

Oluşan hata türünü belirtmek için, denetim veya ' a bir hata kodu iletmelidir `ThrowError` `FireError` . Hata kodu, 32 bitlik bir değere sahip bir OLE durum kodudur. Mümkün olduğunda, OLECTL 'de tanımlanan standart kod kümesinden bir hata kodu seçin. H üstbilgi dosyası. Aşağıdaki tabloda bu kodlar özetlenmektedir.

### <a name="activex-control-error-codes"></a>ActiveX denetimi hata kodları

|Hata|Açıklama|
|-----------|-----------------|
|CTL_E_ILLEGALFUNCTIONCALL|Geçersiz işlev çağrısı|
|CTL_E_OVERFLOW|Taşma|
|CTL_E_OUTOFMEMORY|Bellek yetersiz|
|CTL_E_DIVISIONBYZERO|Sıfıra bölme|
|CTL_E_OUTOFSTRINGSPACE|Dizeler için ayrılan alan doldu|
|CTL_E_OUTOFSTACKSPACE|Yığın için ayrılan alan doldu|
|CTL_E_BADFILENAMEORNUMBER|Hatalı dosya adı veya numarası|
|CTL_E_FILENOTFOUND|Dosya bulunamadı|
|CTL_E_BADFILEMODE|Hatalı dosya modu|
|CTL_E_FILEALREADYOPEN|Dosya zaten açık|
|CTL_E_DEVICEIOERROR|Cihaz G/Ç hatası|
|CTL_E_FILEALREADYEXISTS|Dosya zaten var|
|CTL_E_BADRECORDLENGTH|Hatalı kayıt uzunluğu|
|CTL_E_DISKFULL|Disk dolu|
|CTL_E_BADRECORDNUMBER|Hatalı kayıt numarası|
|CTL_E_BADFILENAME|Hatalı dosya adı|
|CTL_E_TOOMANYFILES|Çok fazla sayıda dosya|
|CTL_E_DEVICEUNAVAILABLE|Cihaz kullanılamıyor|
|CTL_E_PERMISSIONDENIED|İzin reddedildi|
|CTL_E_DISKNOTREADY|Disk yok|
|CTL_E_PATHFILEACCESSERROR|Yol/dosya erişim hatası|
|CTL_E_PATHNOTFOUND|Yol bulunamadı|
|CTL_E_INVALIDPATTERNSTRING|Geçersiz desenli dize|
|CTL_E_INVALIDUSEOFNULL|Geçersiz NULL kullanımı|
|CTL_E_INVALIDFILEFORMAT|Geçersiz dosya biçimi|
|CTL_E_INVALIDPROPERTYVALUE|Geçersiz özellik değeri|
|CTL_E_INVALIDPROPERTYARRAYINDEX|Geçersiz özellik dizisi dizini|
|CTL_E_SETNOTSUPPORTEDATRUNTIME|Çalışma zamanında desteklenmeyen ayarla|
|CTL_E_SETNOTSUPPORTED|Set desteklenmiyor (salt okunurdur özelliği)|
|CTL_E_NEEDPROPERTYARRAYINDEX|Need özelliği dizi dizini|
|CTL_E_SETNOTPERMITTED|İzin verilmiyor|
|CTL_E_GETNOTSUPPORTEDATRUNTIME|Çalışma zamanında desteklenmez|
|CTL_E_GETNOTSUPPORTED|Get desteklenmiyor (salt yazılır özellik)|
|CTL_E_PROPERTYNOTFOUND|Özellik bulunamadı|
|CTL_E_INVALIDCLIPBOARDFORMAT|Geçersiz Pano biçimi|
|CTL_E_INVALIDPICTURE|Geçersiz resim|
|CTL_E_PRINTERERROR|Yazıcı hatası|
|CTL_E_CANTSAVEFILETOTEMP|Dosya TEMP 'e kaydedilemiyor|
|CTL_E_SEARCHTEXTNOTFOUND|Arama metni bulunamadı|
|CTL_E_REPLACEMENTSTOOLONG|Değişiklikler çok uzun|

Gerekirse, standart kodlardan biri kapsamında olmayan bir koşul için özel bir hata kodu tanımlamak üzere CUSTOM_CTL_SCODE makrosunu kullanın. Bu makronun parametresi, dahil 1000 ile 32767 arasında bir tamsayı olmalıdır. Örnek:

[!code-cpp[NVC_MFC_AxUI#37](codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]

Var olan bir VBX denetimini değiştirmek için ActiveX denetimi oluşturuyorsanız, hata kodlarının uyumlu olduğundan emin olmak için, VBX denetiminin kullandığı sayısal değerlerle birlikte ActiveX denetim hata kodlarınızı tanımlayın.

## <a name="handling-special-keys-in-the-control"></a><a name="_core_handling_special_keys_in_your_control"></a>Denetimdeki özel anahtarları işleme

Bazı durumlarda belirli tuş bileşimlerini özel bir şekilde işlemek isteyebilirsiniz; Örneğin, ENTER tuşuna bir çok satırlı metin kutusu denetiminde basıldığında yeni bir satır ekleyin veya yönlü anahtar KIMLIĞI basıldığında bir düzenleme denetimleri grubu arasında geçiş yapın.

ActiveX denetiminizin temel sınıfı ise `COleControl` , kapsayıcıyı işleymadan önce iletileri işlemek Için [CWnd::P reTranslateMessage](reference/cwnd-class.md#pretranslatemessage) ' ı geçersiz kılabilirsiniz. Bu tekniği kullanırken, iletiyi geçersiz kılmanızda kullanırsanız her zaman **true** döndürün `PreTranslateMessage` .

Aşağıdaki kod örneği, yönlü anahtarlarla ilgili herhangi bir iletiyi işlemenin olası bir yolunu gösterir.

[!code-cpp[NVC_MFC_AxUI#38](codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]

ActiveX denetimine yönelik klavye arabirimlerini işleme hakkında daha fazla bilgi için bkz. ActiveX SDK belgeleri.

## <a name="accessing-dialog-controls-that-are-invisible-at-run-time"></a><a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a>Çalışma zamanında görünmeyen Iletişim kutusu denetimlerine erişme

Kullanıcı arabirimine sahip olmayan ve çalışma zamanında görünmeyen iletişim kutusu denetimleri oluşturabilirsiniz. Bir iletişim kutusuna görünmeyen bir çalışma zamanı ActiveX denetimi ekler ve denetime erişmek için [CWnd:: Getdlyıtem öğesini](reference/cwnd-class.md#getdlgitem) kullanırsanız denetim düzgün çalışmaz. Bunun yerine, denetimi temsil eden bir nesne elde etmek için aşağıdaki tekniklerden birini kullanmanız gerekir:

- Üye değişkeni Ekleme Sihirbazı ' nı kullanarak **denetim değişkeni** ' ni seçin ve ardından denetimin kimliğini seçin. Bir üye değişkeni adı girin ve denetim **türü**olarak denetimin sarmalayıcı sınıfını seçin.

     -veya-

- İletişim kutusu öğesi olarak yerel bir değişken ve alt sınıf bildirin. Aşağıdakine benzer bir kod ekleyin ( `CMyCtrl` sarmalayıcı sınıfı, IDC_MYCTRL1 DENETIMIN kimliğidir):

   [!code-cpp[NVC_MFC_AxCont#19](codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
