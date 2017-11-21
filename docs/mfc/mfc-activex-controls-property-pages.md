---
title: "MFC ActiveX denetimleri: Özellik sayfaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DDP_ functions [MFC]
- MFC ActiveX controls [MFC], properties
- property pages [MFC], MFC ActiveX controls
- DoDataExchange method [MFC]
- OLEIVERB_PROPERTIES
- CPropertyPageDialog class [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3dd62127d5fb09675d6c91963d85dd6ae7f44f35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-property-pages"></a>MFC ActiveX Denetimleri: Özellik Sayfaları
Özellik sayfaları ActiveX denetimi özelliklerini görüntülemek ve değiştirmek bir ActiveX denetimi verin. Bu özellikleri görüntülemek ve denetim özelliklerini düzenleme için özelleştirilmiş, grafik bir arabirim sağlayan bir veya daha fazla özellik sayfaları içeren bir denetim özellikleri iletişim kutusu çağırarak erişilir.  
  
 ActiveX denetimi özellik sayfaları iki yolla görüntülenir:  
  
-   Zaman denetimin özelliklerini fiil (**OLEIVERB_PROPERTIES**) olan çağrılan denetimi denetimin özellik sayfaları içeren bir modal özelliğini iletişim kutusunu açar.  
  
-   Kapsayıcıya Seçili denetim özellik sayfalarından gösteren kendi kalıcı olmayan iletişim kutusu görüntüleyebilir.  
  
 (Aşağıdaki şekilde gösterilmiştir) Özellikleri iletişim kutusu sekmeler arasında geçiş yapma özellik sayfaları ve özellik sayfası iletişim kutusunu kapatma gibi genel görevleri gerçekleştirmenize düğmeleri koleksiyonu için geçerli özellik sayfasını görüntülemek için bir alanı oluşur, yapılan değişiklikler iptal etme veya hemen ActiveX denetimi herhangi bir değişiklik uygulama.  
  
 ![Özellikler iletişim kutusunu Circ3](../mfc/media/vc373i1.gif "vc373i1")  
Özellikleri iletişim kutusu  
  
 Bu makalede, özellik sayfaları ActiveX denetiminde kullanmayla ilgili konular yer almaktadır. Bu güncelleştirmeler şunlardır:  
  
-   [ActiveX denetimi için varsayılan özellik sayfası uygulama](#_core_implementing_the_default_property_page)  
  
-   [Özellik sayfasına denetim ekleme](#_core_adding_controls_to_a_property_page)  
  
-   [DoDataExchange işlevi özelleştirme](#_core_customizing_the_dodataexchange_function)  
  
 ActiveX denetiminde özellik sayfalarını kullanma ile ilgili daha fazla bilgi için aşağıdaki makalelere bakın:  
  
-   [MFC ActiveX denetimleri: Başka bir özel özellik sayfası ekleme](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
-   [MFC ActiveX denetimleri: Stok özellik sayfalarını kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
 ActiveX denetimi dışında bir MFC uygulamasında özellik sayfalarını kullanma hakkında daha fazla bilgi için bkz: [özellik sayfalarını](../mfc/property-sheets-mfc.md).  
  
##  <a name="_core_implementing_the_default_property_page"></a>Varsayılan özellik sayfası uygulama  
 Denetim projenizi oluşturmak için ActiveX Denetim Sihirbazı'nı kullanırsanız denetimi türetildiği için ActiveX Denetim Sihirbazı'nı varsayılan özellik sayfası sınıfı sağlar [COlePropertyPage sınıfı](../mfc/reference/colepropertypage-class.md). Başlangıçta, bu özellik sayfası boş kalır, ancak herhangi bir iletişim kutusu denetimi veya denetimleri kümesini ona ekleyebilirsiniz. ActiveX Denetim Sihirbazı'nı varsayılan olarak, ek özellik sayfası sınıfları yalnızca bir özellik sayfası sınıfı oluşturduğundan (aynı zamanda türetilmiş `COlePropertyPage`) Sınıf Görünümü kullanılarak oluşturulmalıdır. Bu yordam hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: başka bir özel özellik sayfası ekleme](../mfc/mfc-activex-controls-adding-another-custom-property-page.md).  
  
 Bir özellik uygulama sayfasıdır (Bu durumda, varsayılan) üç adımlık bir işlemdir:  
  
#### <a name="to-implement-a-property-page"></a>Özellik sayfası uygulamak için  
  
1.  Ekleme bir `COlePropertyPage`-denetim projeye türetilmiş sınıf. ActiveX Denetim Sihirbazı'nı (örneğin, bu durumda) kullanarak proje oluşturulmuşsa, varsayılan özellik sayfası sınıfı zaten mevcut.  
  
2.  Herhangi bir denetim özellik sayfası şablonuna eklemek için iletişim kutusu düzenleyicisi kullanın.  
  
3.  Özelleştirme `DoDataExchange` işlevinin `COlePropertyPage`-türetilmiş sınıf özellik sayfası ve ActiveX denetimi arasındaki değerleri değişimi.  
  
 Örneğin ("Örnek" olarak adlandırılır) basit bir denetim amacıyla, aşağıdaki yordamları kullanın. Örnek ActiveX Denetim Sihirbazı'nı kullanarak oluşturulmuş ve yalnızca stok resim yazısı özelliğini içerir.  
  
##  <a name="_core_adding_controls_to_a_property_page"></a>Özellik sayfasına denetim ekleme  
  
#### <a name="to-add-controls-to-a-property-page"></a>Özellik sayfasına denetim eklemek için  
  
1.  Denetim projenizi açın, kaynak görünümü açın.  
  
2.  Çift **iletişim** dizin simgesi.  
  
3.  Açık **IDD_PROPPAGE_SAMPLE** iletişim kutusu.  
  
     ActiveX Denetim Sihirbazı'nı projesinin adı iletişim kimliği, bu durumda, örnek sonuna ekler.  
  
4.  Sürükleyip Seçili denetimi iletişim kutusunu alanı Kutusu'ndan.  
  
5.  Bu örnekte, bir metin etiket denetimini "Başlık:" ve düzenleme kutusu denetimine sahip bir **IDC_CAPTION** tanımlayıcısı yeterli.  
  
6.  Tıklatın **kaydetmek** değişikliklerinizi kaydetmek için araç çubuğunda.  
  
 Kullanıcı arabirimi değiştirildi, resim yazısı özelliğini Düzenle kutusuyla bağlamanız gerekir. Bu aşağıdaki bölümde düzenleyerek yapılır `CSamplePropPage::DoDataExchange` işlevi.  
  
##  <a name="_core_customizing_the_dodataexchange_function"></a>DoDataExchange işlevi özelleştirme  
 Özellik sayfası [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) işlevi bağlantı özellik sayfası değerlerini denetiminde özelliklerinin gerçek değerlerle izin verir. Bağlantıları kurmak için ilgili denetim özelliklerini uygun özellik sayfası alanları eşlemeniz gerekir.  
  
 Bu eşlemeler özellik sayfası kullanılarak uygulanan **DDP_** işlevleri. **DDP_** işlevleri çalışır gibi **COleDBRecordView** standart MFC iletişim kutuları, bir özel durum ile kullanılan işlevler. Ek olarak bir üye değişkenine başvuruyu **DDP_** işlevleri ele denetim özelliğin adı. Aşağıdaki normal bir giriştir `DoDataExchange` işlevi için bir özellik sayfası.  
  
 [!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]  
  
 Bu işlev özellik sayfanın ilişkilendirir `m_caption` yazılı üye değişkeni kullanarak `DDP_TEXT` işlevi.  
  
 Eklenen özellik sayfası denetimi aldıktan sonra özellik sayfası denetimi arasında bağlantı kurmak gereken `IDC_CAPTION`, ve resim yazısı gerçek denetim özelliğini kullanarak **DDP_Text** yukarıda açıklandığı gibi işlev.  
  
 [Özellik sayfaları](../mfc/reference/property-pages-mfc.md) onay kutularını, radyo düğmeleri gibi diğer iletişim denetim türleri kullanılabilir ve liste kutuları. Özellik sayfası kümesinin tamamını aşağıdaki tabloda listelenmiştir **DDP_** işlevleri ve bunların amaçları:  
  
### <a name="property-page-functions"></a>Özellik sayfası işlevleri  
  
|İşlev adı|Bağlamak için bu işlevi kullanın|  
|-------------------|-------------------------------|  
|`DDP_CBIndex`|Birleşik giriş kutusu denetimi özelliği ile dizinde seçili dizesinin.|  
|`DDP_CBString`|Birleşik giriş kutusu denetimi özelliği ile seçilen dizesinde. Seçili dizeyi özelliğin değerini aynı harflerle başlayabilir ancak onu tam olarak eşleşmiyor.|  
|`DDP_CBStringExact`|Birleşik giriş kutusu denetimi özelliği ile seçilen dizesinde. Seçili dizeyi ve özelliğin dize değeri tam olarak eşleşmelidir.|  
|`DDP_Check`|Onay kutusu denetimi özelliğe sahip.|  
|`DDP_LBIndex`|Bir denetim özelliği ile bir liste kutusunda seçili dizesinin dizini.|  
|`DDP_LBString`|Bir denetim özelliği ile bir liste kutusunda seçili dizesi. Seçili dizeyi özelliğin değerini aynı harflerle başlayabilir ancak onu tam olarak eşleşmiyor.|  
|`DDP_LBStringExact`|Bir denetim özelliği ile bir liste kutusunda seçili dizesi. Seçili dizeyi ve özelliğin dize değeri tam olarak eşleşmelidir.|  
|`DDP_Radio`|Radyo düğmesi denetimini özelliğe sahip.|  
|**DDP_Text**|Metin denetim özelliğe sahip.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [COlePropertyPage sınıfı](../mfc/reference/colepropertypage-class.md)
