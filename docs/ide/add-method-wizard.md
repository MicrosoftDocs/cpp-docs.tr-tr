---
title: Yöntem Ekleme Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.method.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- methods [C++], adding using wizards
ms.assetid: b9a71b0e-9ecf-40fa-9f86-4200cb23d671
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc2ebd18640f0ab778cb45252691e63206861d53
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33340352"
---
# <a name="add-method-wizard"></a>Yöntem Ekleme Sihirbazı
Bir yöntem için bir arabirim eklemek için bu sihirbazı kullanın. Proje türü veya yöntem ekleme arabirim türüne bağlı olarak sihirbazın farklı seçenekler görüntüler.  
  
## <a name="names"></a>Adlar  
 **Dönüş türü**  
 Yöntemi tarafından döndürülen veri türü. `HRESULT` hataları döndürmek için standart bir yol sağladığından tüm arabirim türleri için önerilir.  
  
|Arabirim türü|Açıklama|  
|--------------------|-----------------|  
|Çift arabirim|`HRESULT`. Değiştirilemez.|  
|Özel arabirim|`HRESULT`. Değiştirilemez.|  
|Yerel özel arabirimi|Kendi dönüş türü sağlayın veya listeden seçin.|  
|Görüntüleme arabirimi|Kendi dönüş türü sağlayın veya listeden seçin.|  
|MFC ActiveX denetim görüntüleme arabirimi|Stok yöntemi uygularsanız, dönüş türü uygun değere ayarlanır ve değiştirilemez. Bir yöntemin seçerseniz **yöntem adı** listesinde ve tıklatın **özel** altında **yöntemi türünü seçin**, listeden bir dönüş türü seçin.|  
  
 **Yöntem adı**  
 Yöntem adını belirler.  
  
|Arabirim türü|Açıklama|  
|--------------------|-----------------|  
|ATL çift arabirim, özel arabirim ve yerel özel arabirimi|Kendi yöntem adını belirtin.|  
|MFC görüntüleme arabirimi|Kendi yöntemi adı belirtin veya listeden bir önerilen yöntem adı seçin. Listeden bir adı seçerseniz, uygun değere görünür **dönüş türü** kutusunu ve değiştirilemez.|  
|MFC ActiveX denetim görüntüleme arabirimi|Kendi sağlayın veya stok yöntemlerinden birini seçin [DoClick](../mfc/reference/colecontrol-class.md#doclick) ve [yenileme](../mfc/reference/colecontrol-class.md#refresh). Bkz: [MFC ActiveX denetimleri: stok yöntemler ekleme](../mfc/mfc-activex-controls-adding-stock-methods.md) daha fazla bilgi için.|  
  
 **Yöntem türü**  
 MFC ActiveX denetimleri için kullanılabilir. Bir yöntem adı sağlarsanız, **yöntem adı** kutusunda, listeden bir yöntem seçmek yerine bu kutusu kullanılamaz.  
  
 Yöntemlerden birini seçerseniz **yöntem adı** listesinde, stok uygulama veya özel bir uygulama seçin.  
  
|Yöntem türü|Açıklama|  
|-----------------|-----------------|  
|**Hisse senedi**|Varsayılan. İçinde seçtiğiniz yönteme stok uyarlamasını ekler **yöntem adı** listesi. **Dönüş türü** seçerseniz değiştirilemez olan **hisse senedi**.|  
|**Özel**|Seçili yöntemi saplama uyarlamasını ekler **yöntem adı** listesi. Özel yöntem türleri için kendi dönüş türü sağlayabilir veya birinden seçebilirsiniz **dönüş türü** listesi.|  
  
 **İç adı**  
 Yalnızca bir MFC görüntüleme arabirimi eklenen özel yöntemler için kullanılabilir. Gönderme harita, üstbilgi (.h) dosyası ve uygulama (.cpp) dosya kullanılan adını ayarlar. Varsayılan olarak, bu adı aynı olan **yöntem adı**. Bir MFC görüntüleme arabirimi ile çalışıyorsanız veya özel bir yöntem bir MFC ActiveX denetim görüntüleme arabirimi ekliyorsanız, yöntem adını değiştirebilirsiniz.  
  
|Arabirim türü|Açıklama|  
|--------------------|-----------------|  
|ATL çift arabirim, özel arabirim ve yerel özel arabirimi|Yok|  
|MFC görüntüleme arabirimi|Yöntem adı varsayılan olarak ayarlayın. İç adı düzenleyebilirsiniz.|  
|MFC ActiveX denetim görüntüleme arabirimi|Yalnızca özel yöntemler için iç ad ayarlayabilirsiniz. Stok yöntemler, bir iç adı kullanmayın.|  
  
 **Parametre öznitelikleri**  
 Belirtilen parametre için ek öznitelik ayarlar **parametre adı**.  
  
|Parametre özniteliği|Açıklama|İzin verilen birleşimler|  
|-------------------------|-----------------|--------------------------|  
|**İçinde**|Parametresi çağrılan yordamı çağırma yordamdan geçirilen gösterir.|**içinde** yalnızca<br /><br /> **içinde** ve **çıkışı**|  
|**Çıkışı**|İşaretçi parametresi (sunucudan istemciye) arama yordamı için çağrılan yordamdan döndürülen gösterir.|**out** yalnızca<br /><br /> **içinde** ve **çıkışı**<br /><br /> **out** ve **retval**|  
|**retval**|Parametresi üyesinin dönüş değerini alan gösterir.|**retval** ve teslim alma|  
  
 **Parametre türü**  
 Parametrenin veri türünü ayarlar. Listeden seçin.  
  
 **Parametre adı**  
 Yönteminizi iletmek için bir parametre adını ayarlar. Adını yazdıktan sonra'ı tıklatmalısınız **Ekle** yönteminizi geçirir parametrelerin listesi eklemek için. Bir parametre adı belirtmezseniz, sihirbazın tüm parametre öznitelikleri (yalnızca ATL) göz ardı eder veya **parametre türü** seçimleri.  
  
 Tıkladığınızda **Ekle**, parametre adı görünür **parametre listesi**.  
  
 **Not** bir parametre adı sağlayın ve ardından **son** tıklamadan önce **Ekle**, yönteme parametre eklenmedi. Find yöntemi ve parametre el ile ekleyin.  
  
 **Ekle**  
 Belirttiğiniz parametre ekler **parametre adı**ve bunun türü ve parametre öznitelikleri için **parametre listesi**. ' I tıklatmalısınız **Ekle** bir parametre listesine eklemek için.  
  
 **Kaldır**  
 Öğesinde parametre kaldırır **parametre listesi** listeden.  
  
 **Parametre listesi**  
 Tüm parametreleri ve değiştiricileri ve şu anda yöntemi için eklenen türleri görüntüler. Parametre ekleme gibi sihirbaz güncelleştirir **parametre listesi** değiştirici ve türe sahip her bir parametreyi görüntülemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yöntem ekleme](../ide/adding-a-method-visual-cpp.md)   
 [IDL Öznitelikleri, Yöntem Ekleme Sihirbazı](../ide/idl-attributes-add-method-wizard.md)