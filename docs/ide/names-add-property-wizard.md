---
title: Adlar, Özellik Ekleme Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.prop.overview
dev_langs:
- C++
ms.assetid: 0453b7ea-89cb-41a1-80a2-d45f61589c0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17c3fd5cfc86f76fcdc1c301bd92bb1fdfac3b9c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="names-add-property-wizard"></a>Adlar, Özellik Ekleme Sihirbazı
Bir özellik için bir arabirim eklemek için bu sihirbazı kullanın.  
  
 **Özellik türü**  
 Eklediğiniz özelliğin türünü ayarlar. MFC dispinterfaces için kendi türü sağlayın veya önceden tanımlanmış listeden seçin. Bir özelliğin stok uygulama sağlarsanız, **özellik türü** stok türü olarak ayarlayın ve değişikliği için kullanılamaz.  
  
 **Özellik adı**  
 Özelliğin adını ayarlar. ActiveX denetimleri ile ilişkili MFC dispinterfaces için kendi adınızı sağlayabilir veya bir stok özellik adı önceden tanımlanmış listeden seçebilirsiniz. Kendi özellik adı sağlarsanız, **hisse senedi** uygulama türü kullanılamaz. Bkz: [hisse senedi özellikleri](../ide/stock-properties.md) özellikler listesinde açıklaması.  
  
|Arabirim türü|Açıklama|  
|--------------------|-----------------|  
|ATL çift arabirim, özel arabirim ve yerel özel arabirimi|Bir özellik adı sağlayın.|  
|MFC görüntüleme arabirimi, MFC ActiveX denetim görüntüleme arabirimi|Bir özellik adı belirtin veya listeden bir stok özellik seçin. Listeden bir özellik seçerseniz, uygun değere görünür **özellik türü** kutusu. Altında yaptığınız seçime bağlı olarak bu türünü değiştirebilirsiniz **uygulama türü**.|  
  
 **Dönüş türü**  
 ATL yalnızca arabirimleri. Dönüş türü özelliği için ayarlar. Çift arabirimler için `HRESULT` her zaman dönüş türü ise ve bu kutusu kullanılamaz. Özel arabirimler için listeden bir dönüş türü seçebilirsiniz. `HRESULT` hataları döndürmek için standart bir yol sağladığından hala önerilir.  
  
 **Değişken adı**  
 MFC dispinterfaces yalnızca. Yalnızca belirlediğinizde kullanılabilir **üye değişkeni** altında **uygulama türü**. Özelliği ilişkili olduğu üye değişkeni adını ayarlar. Varsayılan olarak, değişken adı m_ için ayarlanmış*PropertyName*. Bu ad düzenleyebilirsiniz.  
  
 **Bildirim işlevi**  
 MFC dispinterfaces yalnızca. Yalnızca belirlediğinizde kullanılabilir **üye değişkeni** altında **uygulama türü**. Bildirim işlevi çağrılan IF adını özellik değişikliklerini ayarlar. Varsayılan olarak, bildirim işlevin adını üzerinde ayarlanmış*PropertyName*değiştirildi. Bu ad düzenleyebilirsiniz.  
  
 **Get işlevi**  
 MFC dispinterfaces için. Yalnızca belirlediğinizde kullanılabilir **Get/Set yöntemleri** altında **uygulama türü**. Özellik get yapılmaya işlevin adını ayarlar. Varsayılan olarak, Get işlevin adını Get öğesine Ayarla*PropertyName*. Bu ad düzenleyebilirsiniz. İşlev adı silerseniz [GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported) arabirimi gönderme eşlemeye eklenir. Get*PropertyName* işlevini belirten özelliği olarak okunabilir.  
  
 **Set işlevi**  
 MFC dispinterfaces yalnızca. Yalnızca belirlediğinizde kullanılabilir **Get/Set yöntemleri** altında **uygulama türü**. Özellik set yapılmaya işlevin adını ayarlar. Varsayılan olarak, kümesi işlevin adını ayarlanır*PropertyName*. Bu ad düzenleyebilirsiniz. İşlev adı silerseniz [SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported) arabirimi gönderme eşlemeye eklenir. Belirlenen*PropertyName* işlevi özelliği yazılabilir olduğunu belirtir.  
  
 **Uygulama türü**  
 MFC dispinterfaces yalnızca. Nasıl ekleyeceğiniz özelliği uygulanacağını belirtir.  
  
|Uygulama türü|Açıklama|  
|-------------------------|-----------------|  
|**Hisse senedi**|Seçili özellik için bir stok uygulama belirtir **özellik adı**. Varsayılan. Bkz: [hisse senedi özellikleri](../ide/stock-properties.md) daha fazla bilgi için.<br /><br /> Belirtirseniz **hisse senedi**, ardından **özellik türü**, **parametre türü**, ve **parametre adı** soluklaştırılır.|  
|**Üye değişkeni**|Özellik bir üye değişkenine eklenir belirtir. Üye değişkenleri olarak özel özellikler veya çoğu stok özellikleri ekleyebilirsiniz. Belirtemeyeceğiniz **üye değişkeni** için **resim yazısı**, **hWnd**, ve **metin** özellikleri.<br /><br /> Varsayılan adlarla sağlar **değişken adı** ve **bildirim işlevi**. Bu ad düzenleyebilirsiniz.|  
|**Get/Set yöntemleri**|Özellik Get eklenen belirtir*PropertyName* ve*PropertyName* İşlevler, varsayılan olarak. Bu adları altında görünür **Al işlevi** ve **ayarlamak işlevi**.<br /><br /> Varsayılan ayarı değiştirebilirsiniz **özellik türü**, Get işlevi için bir değer geçirir. Parametreleri için belirttiğiniz **almak** ve `Set` işlevleri.|  
  
 **Get işlevi**  
 ATL arabirimler için. Özellik okunamaz olarak ayarlar; diğer bir deyişle, oluşturduğu **almak** bu özellik nesnesinden geri alma yöntemi. Seçmelisiniz **almak**, `Put`, veya her ikisini de.  
  
 **PUT işlevi**  
 ATL yalnızca arabirimleri. Özelliği yazılabilir ayarlar; diğer bir deyişle, oluşturduğu `Put` ayarlanması veya "koyma," nesnenin bu özellik için yöntem. Seçmelisiniz **almak**, `Put`, veya her ikisini de. Bu seçeneği belirlerseniz, yöntemi uygulamak için aşağıdaki iki şekilde seçebilirsiniz:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**PropPut**|[PropPut](../windows/propput.md) işlevi nesnesinin bir kopyasını döndürür. Varsayılan ve özellik yazılabilir yapmak için en yaygın yolu budur.|  
|**PropPutRef**|[PropPutRef](../windows/propputref.md) işlevi nesnenin kopyasını döndürme yerine nesne için bir başvuru döndürür. Büyük yapılar veya başlatma yükü olabilecek dizileri gibi nesneler için bu seçeneği kullanmayı deneyin.|  
  
 **Parametre öznitelikleri**  
 ATL yalnızca arabirimleri. Parametresi tarafından belirtilen olup olmadığını ayarlar **parametre adı** olan **içinde**, **çıkışı**, her ikisini birden veya yok.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**in**|Parametresi çağrılan yordamı çağırma yordamdan geçirilen gösterir.|  
|**out**|İşaretçi parametresi (sunucudan istemciye) arama yordamı için çağrılan yordamdan döndürülen gösterir.|  
  
 **Parametre türü**  
 Parametrenin veri türünü ayarlar. Listeden seçin.  
  
 **Parametre adı**  
 Özellik parametrelere sahipse özelliği için eklemekte olduğunuz bir parametre adını ayarlar. Tıkladığınızda **Ekle**, parametre adı görünür **parametre listesi**.  
  
 **Parametre listesi**  
 Özelliğin eklenecek özniteliklerinin listesini görüntüler. Listedeki her öğeye parametre adı, parametre türü ve öznitelikleri oluşur. Kullanım **Ekle** ve **kaldırmak** listesini güncelleştirmek için.  
  
 **Ekle**  
 Belirttiğiniz parametre ekler **parametre adı** ve **parametre türü** için **parametre listesi**. ' I tıklatmalısınız **Ekle** bir parametre listesine eklemek için.  
  
 **Kaldır**  
 Öğesinde parametre kaldırır **parametre listesi**.  
  
 **Varsayılan özellik**  
 MFC görüntüleme yalnızca arabirimi yükle. Bu özellik, arabirim için varsayılan olarak ayarlar. Arabirim yalnızca bir varsayılan özellik olabilir; Bu kutu arabirimi, eklediğiniz diğer özellikler için varsayılan özelliği belirttiğinizde kullanılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik ekleme](../ide/adding-a-property-visual-cpp.md)   
 [IDL öznitelikleri, Özellik Ekleme Sihirbazı](../ide/idl-attributes-add-property-wizard.md)   
 [Arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md)