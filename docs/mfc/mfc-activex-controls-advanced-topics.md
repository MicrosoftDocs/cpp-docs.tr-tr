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
ms.openlocfilehash: c5e3be3915a0707f8df17d3c9ebe2eb0e4f623b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364635"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC ActiveX Denetimleri: Gelişmiş Konular

Bu makalede ActiveX denetimleri geliştirme ile ilgili gelişmiş konular ele al.) Bunlar:

- [ActiveX Denetimlerinde Veritabanı Sınıflarını Kullanma](#_core_using_database_classes_in_activex_controls)

- [Parametrelendirilmiş Özellik Uygulama](#_core_implementing_a_parameterized_property)

- [ActiveX Denetiminizdeki İşlem Hataları](#_core_handling_errors_in_your_activex_control)

- [Denetimde Özel Anahtarları Kullanma](#_core_handling_special_keys_in_your_control)

- [Çalışma Zamanında Görünmez Olan İletişim Denetimleri'ne Erişim](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

## <a name="using-database-classes-in-activex-controls"></a><a name="_core_using_database_classes_in_activex_controls"></a>ActiveX Denetimlerinde Veritabanı Sınıflarını Kullanma

ActiveX denetim sınıfları sınıf kitaplığı'nın bir parçası olduğundan, mfc veritabanı sınıflarını kullanan ActiveX denetimlerini geliştirmek için standart bir MFC uygulamasında veritabanı sınıflarını kullanmak için aynı yordamları ve kuralları uygulayabilirsiniz.

MFC veritabanı sınıflarının genel bir özeti için [MFC Veritabanı Sınıfları (DAO ve ODBC)](../data/mfc-database-classes-odbc-and-dao.md)bölümüne bakın. Makale, hem MFC ODBC sınıflarını hem de MFC DAO sınıflarını tanıtır ve sizi her iki si hakkında daha fazla ayrıntıya yönlendirir.

> [!NOTE]
> DAO, Office 2013 aracılığıyla desteklenir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir. Visual C++ ortamı ve sihirbazlar DAO'yu desteklemez (her ne kadar DAO sınıfları dahil olsa da ve bunları kullanmaya devam edebilirsiniz). Microsoft, yeni projeler için [OLE DB Şablonları](../data/oledb/ole-db-programming.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) kullanmanızı önerir. DAO'yu yalnızca varolan uygulamaları korurken kullanmalısınız.

## <a name="implementing-a-parameterized-property"></a><a name="_core_implementing_a_parameterized_property"></a>Parametrelendirilmiş Özellik Uygulama

Parametreli özellik (bazen özellik dizisi olarak da adlandırılır), denetimin tek bir özelliği olarak homojen bir değer koleksiyonunu ortaya çıkarmak için kullanılan bir yöntemdir. Örneğin, bir diziyi veya sözlüğü özellik olarak ortaya çıkarmak için parametreli bir özellik kullanabilirsiniz. Visual Basic'te, böyle bir özelliğe dizi gösterimi kullanılarak erişilir:

[!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]

Parametreli bir özellik uygulamak için Özellik Ekle Sihirbazı'nı kullanın. Özellik Ekle Sihirbazı, denetim kullanıcısının yukarıdaki gösterimi kullanarak veya standart moda kullanarak özelliğe erişmesine izin veren bir çift Get/Set işlevi ekleyerek özelliği uygular.

Yöntem ve özelliklere benzer şekilde, parametreli özelliklerin de izin verilen parametre sayısıiçin bir sınırı vardır. Parametreli özellikler söz konusu olduğunda, sınır 15 parametredir (özellik değerini depolamak için ayrılmış bir parametreile).

Aşağıdaki yordam, iki boyutlu bir tamsayı dizisi olarak erişilebilen Dizi adlı parametreli bir özellik ekler.

#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>Özellik Ekle Sihirbazı'nı kullanarak parametreli bir özellik eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Özellik Ekle'yi**tıklatın.

1. Özellik **Adı** kutusuna, `Array`yazın.

1. Özellik **Türü** kutusunda, **kısa'yı**seçin.

1. **Uygulama** Türü için **Yöntemleri Al/Ayarla'yı**tıklatın.

1. **İşlev Al** ve **Ayarla** kutularında, İşlevleri Al ve Ayarla'nız için benzersiz adlar yazın veya varsayılan adları kabul edin.

1. Parametre Adı ve **Parametre Türü** denetimlerini kullanarak *satır* *(kısa*yazı) adı verilen bir **parametre** ekleyin.

1. *Sütun* adı verilen ikinci bir parametre ekleyin *(kısa*yazın).

1. **Son**'a tıklayın.

### <a name="changes-made-by-the-add-property-wizard"></a>Özellik Ekle Sihirbazı tarafından yapılan değişiklikler

Özel bir özellik eklediğinizde, Özellik Ekle Sihirbazı denetim sınıfı üstbilgide değişiklik yapar (. H) ve uygulama (. CPP) dosyaları.

Denetim sınıfına aşağıdaki satırlar eklenir. H dosyası:

[!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]

Bu kod, çağrılan `GetArray` ve `SetArray` kullanıcının özelliğe erişirken belirli bir satır ve sütun istemesine izin veren iki işlevi bildirir.

Buna ek olarak, Özellik Ekle Sihirbazı denetim sınıfı uygulamasında bulunan denetim gönderme haritasına aşağıdaki satırları ekler (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]

Son olarak, ve `GetArray` `SetArray` işlevlerin uygulamaları sonuna eklenir. CPP dosyası. Çoğu durumda, özelliğin değerini döndürmek için Get işlevini değiştirirsiniz. Set işlevi genellikle özellik değişmeden önce veya sonra yürütülmesi gereken kod içerir.

Bu özelliğin yararlı oltaolması için, parametreli özellik için değerleri depolamak için **kısa**tür, denetim sınıfında iki boyutlu bir dizi üye değişkeni bildirebilirsiniz. Daha sonra, parametrelerde belirtildiği gibi uygun satır ve sütunda depolanan değeri döndürmek için Get işlevini değiştirebilir ve satır ve sütun parametreleri tarafından başvurulan değeri güncelleştirmek için Ayar işlevini değiştirebilirsiniz.

## <a name="handling-errors-in-your-activex-control"></a><a name="_core_handling_errors_in_your_activex_control"></a>ActiveX Denetiminizdeki İşlem Hataları

Denetimde hata koşulları oluşursa, hatayı denetim kapsayıcısına bildirmeniz gerekebilir. Hatanın oluştuğu duruma bağlı olarak hataları bildirmek için iki yöntem vardır. Hata bir özelliğin Get or Set işlevi nde veya Bir OLE Otomasyon yönteminin uygulanması nda oluşursa, denetim [COleControl::ThrowError,](../mfc/reference/colecontrol-class.md#throwerror)bir hata oluştuğunu kontrol eden kullanıcıya sinyal çağırmalıdır. Hata başka bir zamanda oluşursa, denetim [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror), bir stok Hata olay yangınları çağırmalısınız.

Oluşan hata türünü belirtmek için, `ThrowError` denetimin bir hata kodunu `FireError`veya . Hata kodu, 32 bit değeri olan bir OLE durum kodudur. Mümkün olduğunda, OLECTL'de tanımlanan standart kod kümesinden bir hata kodu seçin. H üstbilgi dosyası. Aşağıdaki tabloda bu kodlar özetlenmiştir.

### <a name="activex-control-error-codes"></a>ActiveX Kontrol Hata Kodları

|Hata|Açıklama|
|-----------|-----------------|
|CTL_E_ILLEGALFUNCTIONCALL|Yasadışı işlev çağrısı|
|CTL_E_OVERFLOW|Taşma|
|CTL_E_OUTOFMEMORY|Bellek dışında|
|CTL_E_DIVISIONBYZERO|Sıfıra göre bölme|
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
|CTL_E_DEVICEUNAVAILABLE|Aygıt kullanılamıyor|
|CTL_E_PERMISSIONDENIED|İzin reddedildi|
|CTL_E_DISKNOTREADY|Disk hazır değil|
|CTL_E_PATHFILEACCESSERROR|Yol/dosya erişim hatası|
|CTL_E_PATHNOTFOUND|Yol bulunamadı|
|CTL_E_INVALIDPATTERNSTRING|Geçersiz desen dizesi|
|CTL_E_INVALIDUSEOFNULL|NULL'un geçersiz kullanımı|
|CTL_E_INVALIDFILEFORMAT|Geçersiz dosya biçimi|
|CTL_E_INVALIDPROPERTYVALUE|Geçersiz özellik değeri|
|CTL_E_INVALIDPROPERTYARRAYINDEX|Geçersiz özellik dizi dizini|
|CTL_E_SETNOTSUPPORTEDATRUNTIME|Çalışma zamanında desteklenmeyen küme|
|CTL_E_SETNOTSUPPORTED|Desteklenmeyen leri ayarlayın (salt okunur özelliği)|
|CTL_E_NEEDPROPERTYARRAYINDEX|Need özelliği dizi dizini|
|CTL_E_SETNOTPERMITTED|İzin verilmeyecek şekilde ayarlayın|
|CTL_E_GETNOTSUPPORTEDATRUNTIME|Çalışma zamanında desteklenmeyin|
|CTL_E_GETNOTSUPPORTED|Desteklenmeyin (yalnızca yazma özelliği)|
|CTL_E_PROPERTYNOTFOUND|Özellik bulunamadı|
|CTL_E_INVALIDCLIPBOARDFORMAT|Geçersiz pano biçimi|
|CTL_E_INVALIDPICTURE|Geçersiz resim|
|CTL_E_PRINTERERROR|Yazıcı hatası|
|CTL_E_CANTSAVEFILETOTEMP|DOSYAYI TEMP'e kaydedemez|
|CTL_E_SEARCHTEXTNOTFOUND|Arama metni bulunamadı|
|CTL_E_REPLACEMENTSTOOLONG|Yedekler çok uzun|

Gerekirse, standart kodlardan biri tarafından kapsanmayan bir durum için özel hata kodu tanımlamak için CUSTOM_CTL_SCODE makroyu kullanın. Bu makro için parametre 1000 ve 32767 arasında bir tamsayı, dahil olmalıdır. Örneğin:

[!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]

Varolan bir VBX denetimini değiştirmek için activex denetimi oluşturuyorsanız, hata kodlarının uyumlu olduğundan emin olmak için ActiveX denetim hata kodlarınızı VBX denetiminin kullandığı sayısal değerlerle tanımlayın.

## <a name="handling-special-keys-in-the-control"></a><a name="_core_handling_special_keys_in_your_control"></a>Denetimde Özel Anahtarları Kullanma

Bazı durumlarda belirli tuş vuruşu kombinasyonlarını özel bir şekilde işlemek isteyebilirsiniz; örneğin, ENTER tuşuna çok satırlı metin kutusu denetimine basıldığında yeni bir satır ekleyin veya yön tuşu kimliğine basıldığında bir dizi denetim grubu arasında hareket edin.

ActiveX denetiminizin taban sınıfı `COleControl`ise, kapsayıcı bunları işlemeden önce iletileri işlemek için [CWnd::PreTranslateMessage'ı](../mfc/reference/cwnd-class.md#pretranslatemessage) geçersiz kılabilirsiniz. Bu tekniği kullanırken, **TRUE** `PreTranslateMessage`'' 'yi geçersiz kılmanızda iletiyi işlerseniz, her zaman TRUE döndürün.

Aşağıdaki kod örneği, yön tuşlarıile ilgili iletileri işlemenin olası bir yolunu gösterir.

[!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]

ActiveX denetimi için klavye arabirimlerinin işlenmesi hakkında daha fazla bilgi için ActiveX SDK belgelerine bakın.

## <a name="accessing-dialog-controls-that-are-invisible-at-run-time"></a><a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a>Çalışma Zamanında Görünmez Olan İletişim Denetimleri'ne Erişim

Kullanıcı arabirimi olmayan ve çalışma zamanında görünmez olan iletişim denetimleri oluşturabilirsiniz. Bir iletişim kutusuna görünmez bir çalışma zamanında ActiveX denetimi ekler ve denetime erişmek için [CWnd::GetDlgItem](../mfc/reference/cwnd-class.md#getdlgitem) kullanırsanız, denetim doğru çalışmaz. Bunun yerine, denetimi temsil eden bir nesne elde etmek için aşağıdaki tekniklerden birini kullanmanız gerekir:

- Üye Değişken Ekle Sihirbazı'nı **kullanarak, Denetim** Değişkeni'ni seçin ve ardından denetimin kimliğini seçin. Bir üye değişken adı girin ve **denetimin**sarıcı sınıfını Denetim Türü olarak seçin.

     -veya-

- Yerel bir değişkeni ve alt sınıfı iletişim öğesi olarak bildirin. Aşağıdakilere benzeyen ekle kodu`CMyCtrl` (sarmalayıcı sınıfıdır IDC_MYCTRL1 denetimin kimliğidir):

   [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
