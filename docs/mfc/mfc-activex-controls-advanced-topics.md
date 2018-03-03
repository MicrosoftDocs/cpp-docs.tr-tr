---
title: "MFC ActiveX denetimleri: Gelişmiş konular | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2205862a438099c08801556f511ebf3c5e93a277
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC ActiveX Denetimleri: Gelişmiş Konular
Bu makalede, ActiveX denetimleri geliştirme ile ilgili gelişmiş konular yer almaktadır. Bu güncelleştirmeler şunlardır:  
  
-   [ActiveX denetimlerinde veritabanı sınıflarını kullanma](#_core_using_database_classes_in_activex_controls)  
  
-   [Parametreli özellik uygulama](#_core_implementing_a_parameterized_property)  
  
-   [ActiveX denetiminde hataları işleme](#_core_handling_errors_in_your_activex_control)  
  
-   [Özel anahtarları denetiminde işleme](#_core_handling_special_keys_in_your_control)  
  
-   [Çalışma zamanında görünmez iletişim kutusu denetimlerine erişme](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)  
  
##  <a name="_core_using_database_classes_in_activex_controls"></a>ActiveX denetimlerinde veritabanı sınıflarını kullanma  
 ActiveX denetim sınıfları sınıf kitaplığı parçası olduğundan, aynı yordamlar ve MFC veritabanı sınıfları kullanan ActiveX denetimleri geliştirme için standart bir MFC uygulamasında veritabanı sınıflarını kullanma kuralları uygulayabilirsiniz.  
  
 MFC veritabanı sınıfları genel bir bakış için bkz: [MFC veritabanı sınıfları (DAO ve ODBC)](../data/mfc-database-classes-odbc-and-dao.md). MFC ODBC sınıfları makaleyi tanıtır ve MFC DAO sınıflarını ve ya da daha fazla ayrıntı için yönlendirir.  
  
> [!NOTE]
>  Visual C++ ortamı ve sihirbazları DAO (DAO sınıfları dahil edilmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, kullanmanızı önerir [OLE DB Şablonları](../data/oledb/ole-db-programming.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) yeni projeler için. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.  
  
##  <a name="_core_implementing_a_parameterized_property"></a>Parametreli özellik uygulama  
 (Bazen özellik dizisi denir) parametreli özellik değerleri homojen koleksiyonunu denetiminin tek bir özellik olarak gösterme bir yöntemdir. Örneğin, bir dizi veya bir sözlük bir özellik olarak kullanıma sunmak için parametreli bir özelliğini kullanabilirsiniz. Visual Basic'te, böyle bir özellik, dizi gösterim kullanılarak erişilir:  
  
 [!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]  
  
 Parametreli özellik uygulamak için Özellik Ekleme Sihirbazı'nı kullanın. Özellik Ekleme Sihirbazı'nı bir çifti Get/Set işlevlerin denetim kullanıcının yukarıdaki gösterimini kullanarak özellik erişmesine izin vermek veya standart şekilde ekleyerek özelliği uygular.  
  
 Yöntemleri ve özellikleri, parametreli özellikleri benzer ayrıca izin verilen parametre sayısı için bir sınır vardır. Parametreli özellikleri söz konusu olduğunda, 15 parametreleriyle (özellik değeri depolamak için ayrılmış bir parametre) sınırlıdır.  
  
 Aşağıdaki yordam tamsayılar iki boyutlu bir dizi erişilebilir dizi adlı parametreli bir özellik ekler.  
  
#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak parametreli özellik eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden tıklatın **Ekle** ve ardından **Özellik Ekle**.  
  
5.  İçinde **özellik adı** kutusuna `Array`.  
  
6.  İçinde **özellik türü** kutusunda **kısa**.  
  
7.  İçin **uygulama** türü,'ı tıklatın **Get/Set yöntemleri**.  
  
8.  İçinde **Al işlevi** ve **ayarlamak işlevi** kutuları, alma ve ayarlama işlevleri için benzersiz adlar yazın veya varsayılan adı kabul edin.  
  
9. Adlı bir parametre eklemek `row` (tür `short`) kullanarak **parametre adı** ve **parametre türü** kontrol eder.  
  
10. Adlı ikinci bir parametre eklemek `column` (tür `short`).  
  
11. **Son**'a tıklayın.  
  
### <a name="changes-made-by-the-add-property-wizard"></a>Tarafından yapılan değişiklikleri ekleme özelliği Sihirbazı  
 Özellik Ekleme Sihirbazı'nı bir özel özellik eklediğinizde, control sınıfı üstbilgisine değişiklikleri yapar (. Y) ve uygulama (. CPP) dosyaları.  
  
 Aşağıdaki satırları denetim sınıfına eklenir. H dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]  
  
 Bu kod adlı iki işlevleri bildirir `GetArray` ve `SetArray` belirli satır ve sütun özelliğine erişirken isteği kullanıcıya izin verin.  
  
 Buna ek olarak, Özellik Ekleme Sihirbazı'nı aşağıdaki satırları denetim sınıfı uygulamasında bulunan denetim gönderme eşlemesi ekler (. CPP) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]  
  
 Son olarak, uygulamaları `GetArray` ve `SetArray` işlevleri sonuna eklenir. CPP dosyası. Çoğu durumda, Get işlevi özelliğinin değeri döndürecek şekilde değiştirir. Set işlevi genellikle önce veya sonra özellik değişikliklerini yürütülecek kod içerir.  
  
 Bu özellik kullanışlı olması, Denetim sınıfının türü iki boyutlu dizi üye değişkeninde bildirebilirsiniz **kısa**, parametreli özellik değerlerini depolamak için. Ardından Get işlevi parametreleri tarafından belirtildiği şekilde doğru satır ve sütun, depolanan değeri döndürecek şekilde değiştirin ve satır ve sütun parametreleri tarafından başvurulan değer güncelleştirmek için Set işlevi değiştirin.  
  
##  <a name="_core_handling_errors_in_your_activex_control"></a>ActiveX denetiminde hataları işleme  
 Hata koşulları denetiminde meydana gelirse, denetimi kapsayıcısı hata raporu gerekebilir. Hata oluştuğu durum bağlı olarak, hata raporlama için iki yöntem vardır. Hata oluşursa bir özelliğin içinde almak veya ayarlamak işlevi veya OLE Otomasyon yöntemi uygulama içinde denetimi çağırmalıdır [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror), hangi sinyalleri denetim kullanıcıya bir hata oluştu. Diğer herhangi bir zamanda hata oluşursa, Denetim çağırmalıdır [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror), bir stok hata olayı ateşlenir.  
  
 Oluştu hata türünü belirtmek için denetim bir hata kodu için geçmesi gereken `ThrowError` veya `FireError`. 32-bit değerine sahip bir OLE durum kodu bir hata kodudur. Mümkün olduğunda, bir hata kodu OLECTL tanımlanan kodları standart kümesi seçin. H üstbilgi dosyası. Aşağıdaki tabloda bu kodları özetler.  
  
### <a name="activex-control-error-codes"></a>ActiveX denetimi hata kodları  
  
|Hata|Açıklama|  
|-----------|-----------------|  
|**CTL_E_ILLEGALFUNCTIONCALL**|Geçersiz işlev çağrısı|  
|**CTL_E_OVERFLOW**|Taşma|  
|**CTL_E_OUTOFMEMORY**|Bellek yetersiz|  
|**CTL_E_DIVISIONBYZERO**|Sıfıra bölme|  
|**CTL_E_OUTOFSTRINGSPACE**|Dize alanı yetersiz|  
|**CTL_E_OUTOFSTACKSPACE**|Yığın alanı kalmadı|  
|**CTL_E_BADFILENAMEORNUMBER**|Hatalı dosya adı veya numarası|  
|**CTL_E_FILENOTFOUND**|Dosyası bulunamadı|  
|**CTL_E_BADFILEMODE**|Hatalı dosya modu|  
|**CTL_E_FILEALREADYOPEN**|Dosya zaten açık|  
|**CTL_E_DEVICEIOERROR**|Cihaz G/Ç hatası|  
|**CTL_E_FILEALREADYEXISTS**|Dosya zaten var.|  
|**CTL_E_BADRECORDLENGTH**|Hatalı kayıt uzunluğu|  
|**CTL_E_DISKFULL**|Disk dolu|  
|**CTL_E_BADRECORDNUMBER**|Hatalı kayıt numarası|  
|**CTL_E_BADFILENAME**|Hatalı dosya adı|  
|**CTL_E_TOOMANYFILES**|Çok fazla sayıda dosya|  
|**CTL_E_DEVICEUNAVAILABLE**|Aygıt kullanılamıyor|  
|**CTL_E_PERMISSIONDENIED**|İzin reddedildi|  
|**CTL_E_DISKNOTREADY**|Disk hazır değil|  
|**CTL_E_PATHFILEACCESSERROR**|Yol/dosya erişim hatası|  
|**CTL_E_PATHNOTFOUND**|Yol bulunamadı|  
|**CTL_E_INVALIDPATTERNSTRING**|Geçersiz örnek dize|  
|**CTL_E_INVALIDUSEOFNULL**|NULL kullanımı geçersiz|  
|**CTL_E_INVALIDFILEFORMAT**|Dosya biçimi geçersiz|  
|**CTL_E_INVALIDPROPERTYVALUE**|Özellik değeri geçersiz|  
|**CTL_E_INVALIDPROPERTYARRAYINDEX**|Geçersiz özellik dizisi dizini|  
|**CTL_E_SETNOTSUPPORTEDATRUNTIME**|Çalışma zamanında desteklenmeyen ayarlayın|  
|**CTL_E_SETNOTSUPPORTED**|Desteklenmeyen kümesi (salt okunur özelliği)|  
|**CTL_E_NEEDPROPERTYARRAYINDEX**|Need özelliği dizi dizini|  
|**CTL_E_SETNOTPERMITTED**|İzin ayarlama|  
|**CTL_E_GETNOTSUPPORTEDATRUNTIME**|Çalışma zamanında desteklenmeyen|  
|**CTL_E_GETNOTSUPPORTED**|Desteklenmiyor (salt yazılır özellik) Al|  
|**CTL_E_PROPERTYNOTFOUND**|Özellik bulunamadı|  
|**CTL_E_INVALIDCLIPBOARDFORMAT**|Geçersiz Pano biçimi|  
|**CTL_E_INVALIDPICTURE**|Geçersiz resim|  
|**CTL_E_PRINTERERROR**|Yazıcı hatası|  
|**CTL_E_CANTSAVEFILETOTEMP**|Dosya TEMP kaydedilemiyor.|  
|**CTL_E_SEARCHTEXTNOTFOUND**|Arama metni bulunamadı|  
|**CTL_E_REPLACEMENTSTOOLONG**|Değiştirilenler çok uzun|  
  
 Gerekirse, kullanın **CUSTOM_CTL_SCODE** makrosu standart kodları biri tarafından kapsanmayan bir koşul için bir özel hata kodu tanımlayın. Parametresi bu makrosu için 1000 arasında bir tamsayı olmalıdır ve 32767 (dahil) arasındadır. Örneğin:  
  
 [!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]  
  
 Varolan bir VBX denetim değiştirmek için bir ActiveX denetimi oluşturuyorsanız, ActiveX denetimi hata kodları VBX denetimi hata kodları uyumlu olduğundan emin olmak için kullanır aynı sayısal değerleri tanımlayın.  
  
##  <a name="_core_handling_special_keys_in_your_control"></a>Özel anahtarları denetiminde işleme  
 Bazı durumlarda, özel bir yolla belirli tuş birleşimleri işlemek isteyebilirsiniz; Örneğin, bir çok satırlı metin ENTER tuşuna basıldığında yeni bir satır kutusu denetim veya bir düzen grubu arasında taşıma Ekle denetleyen bir yönlü zaman anahtar basılı kimliği.  
  
 ActiveX denetimi temel sınıfını ise `COleControl`, geçersiz kılabilirsiniz [CWnd::PreTranslateMessage](../mfc/reference/cwnd-class.md#pretranslatemessage) kapsayıcı bunları işlemeden önce iletileri işlemek için. Bu yöntemi kullanırken, her zaman geri **TRUE** geçersiz kılmada iletiyi işlemek, `PreTranslateMessage`.  
  
 Aşağıdaki kod örneğinde tek yönlü anahtarlarına ilgili tüm iletileri işleme olası bir yol gösterir.  
  
 [!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]  
  
 ActiveX denetimi için klavye arabirimleri işleme ile ilgili daha fazla bilgi için ActiveX SDK belgelerine bakın.  
  
##  <a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a>Çalışma zamanında görünmez iletişim kutusu denetimlerine erişme  
 Kullanıcı arabirimi ve çalışma zamanında görünmez iletişim kutusu denetimleri oluşturabilirsiniz. ActiveX denetiminin çalışma zamanında bir iletişim kutusu ve kullanmak için bir görünmez eklerseniz, [CWnd::GetDlgItem](../mfc/reference/cwnd-class.md#getdlgitem) erişim denetimi için denetim düzgün çalışmaz. Bunun yerine, denetimini temsil eden bir nesne almak için aşağıdaki teknikleri birini kullanmalıdır:  
  
-   Ekleme üye değişkeni Sihirbazı'nı kullanarak seçin **denetim değişken** ve denetimin kimliği seçin. Denetimin sarmalayıcı sınıfı olarak bir üye değişken adı girin ve **denetim türü**.  
  
     veya  
  
-   Bir yerel değişken ve bir alt iletişim öğesi olarak bildirin. Aşağıdakine benzer bir kod ekleme (`CMyCtrl` sarmalayıcı sınıftır `IDC_MYCTRL1` denetimin kimliği):  
  
     [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

