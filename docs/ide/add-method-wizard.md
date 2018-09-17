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
ms.openlocfilehash: 9c26f4b75c2c4920cbf8a235064aea222a066fca
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718854"
---
# <a name="add-method-wizard"></a>Yöntem Ekleme Sihirbazı
Bir yöntem bir arabirim eklemek için bu sihirbazı kullanın. Proje türü veya yöntem ekleme arabirim türüne bağlı olarak sihirbazın farklı seçenekleri görüntüler.  
  
## <a name="names"></a>Adlar

- **Dönüş türü**

   Yöntem tarafından döndürülen veri türü. `HRESULT` hatalarını döndürmek için standart bir yol sağladığından, tüm arabirim türleri için önerilir.  
  
   |Arabirim türü|Açıklama|  
   |--------------------|-----------------|  
   |Çift arabirim|`HRESULT`. Değiştirilemez.|  
   |Özel arabirim|`HRESULT`. Değiştirilemez.|  
   |Yerel özel arabirimi|Kendi dönüş türü belirtin veya listeden seçin.|  
   |Dispinterface|Kendi dönüş türü belirtin veya listeden seçin.|  
   |MFC ActiveX denetimi dispinterface|Stok metodu uygularsanız, dönüş türü uygun değere ayarlanır ve değiştirilemez. Bir yöntemi seçerseniz **yöntem adı** listelemek ve tıklayın **özel** altında **yöntemi türünü seçin**, listeden bir dönüş türü seçin.|  
  
- **Yöntem adı**

   Yöntemin adını ayarlar.  
  
   |Arabirim türü|Açıklama|  
   |--------------------|-----------------|  
   |ATL çift arabirim, özel arabirim ve yerel özel arabirimi|Kendi yöntem adını belirtin.|  
   |MFC dispinterface|Kendi yöntemi adı belirtin veya listeden bir önerilen yöntem adı seçin. Listeden bir ad seçerseniz, uygun değere görünür **dönüş türü** kutusu ve değiştirilemez.|  
   |MFC ActiveX denetimi dispinterface|Stok yöntemlerden birini seçin veya kendi sağlamak [DoClick](../mfc/reference/colecontrol-class.md#doclick) ve [Yenile](../mfc/reference/colecontrol-class.md#refresh). Bkz: [MFC ActiveX denetimleri: stok yöntemler ekleme](../mfc/mfc-activex-controls-adding-stock-methods.md) daha fazla bilgi için.|  
  
- **Yöntem türü**

   MFC ActiveX denetimleri için kullanılabilir. Yöntem adı'sağlarsanız **yöntem adı** kutusunda, listeden bir yöntem seçmek yerine bu kutuyu kullanılamıyor.  
  
    Metotlarından birini seçerseniz **yöntem adı** listesinde, stok uygulaması ya da özel bir uygulama seçin.  
  
   |Yöntem türü|Açıklama|  
   |-----------------|-----------------|  
   |**Hisse senedi**|Varsayılan. Seçtiğiniz yöntem stok uygulaması ekler **yöntem adı** listesi. **Dönüş türü** seçerseniz değiştirilemez **hisse senedi**.|  
   |**Özel**|Seçilen yöntemin bir saplama uygulaması ekler **yöntem adı** listesi. Özel yöntem türleri için kendi dönüş türü sağlayabilir veya birinden seçebilirsiniz **dönüş türü** listesi.|  
  
- **İç adı**

   Yalnızca bir MFC dispinterface için eklenen özel yöntemler için kullanılabilir. Dağıtım eşlemesi, üstbilgi (.h) dosyası ve uygulama (.cpp) dosyası içinde kullanılan adını ayarlar. Varsayılan olarak, bu adı aynı olan **yöntem adı**. Bir MFC dispinterface ile çalışıyorsanız ya da özel bir yöntem için bir MFC ActiveX denetimi dispinterface ekliyorsanız, yöntem adını değiştirebilirsiniz.  
  
   |Arabirim türü|Açıklama|  
   |--------------------|-----------------|  
   |ATL çift arabirim, özel arabirim ve yerel özel arabirimi|Yok|  
   |MFC dispinterface|Yöntem adı için varsayılan olarak ayarlayın. İç adını düzenleyebilirsiniz.|  
   |MFC ActiveX denetimi dispinterface|Yalnızca özel yöntemler için iç ad ayarlayabilirsiniz. Stok yöntemler, bir iç adını kullanmayın.|  
  
- **Parametre öznitelikleri**

   Herhangi bir ek özniteliği için belirtilen parametre ayarlar **parametre adı**.  
  
   |Parametre özniteliği|Açıklama|İzin verilen birleşimleri|  
   |-------------------------|-----------------|--------------------------|  
   |**İçinde**|Parametrenin çağıran yordamdan çağrılan yordama geçirildiğini gösterir.|**içinde** yalnızca<br /><br /> **içinde** ve **uğradı**|  
   |**Çıkış**|İşaretçi parametresi çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülür gösterir.|**Çıkış** yalnızca<br /><br /> **içinde** ve **uğradı**<br /><br /> **Çıkış** ve **retval**|  
   |**retval**|Parametrenin, üyenin dönüş değeri alır gösterir.|**retval** ve çıkış|  
  
- **Parametre türü**

   Parametrenin veri türünü ayarlar. Türü listeden seçin.  
  
- **Parametre adı**

   Yönteminiz iletilecek parametre adını ayarlar. Adını yazdıktan sonra tıklamanız **Ekle** yönteminiz geçer parametre listesi eklemek için. Parametre adı belirtmezseniz, sihirbazın herhangi bir parametre özniteliği (sadece ATL) göz ardı eder veya **parametre türü** seçimleri.  
  
   ' A tıkladığınızda **Ekle**, parametre adı görünür **parametre listesi**.  
  
   > [!Note]
   > Parametre adı sağlayın ve ardından **son** tıklamadan önce **Ekle**, parametre yönteme eklenmez. Yöntemini bulun ve parametre el ile Ekle gerekir.  
  
- **Add**

   Belirttiğiniz parametre ekler **parametre adı**ve bunun türü ve parametre öznitelikleri için **parametre listesi**. ' A tıklamalıdır **Ekle** parametre listesine eklenecek.  
  
- **Kaldır**

   Seçtiğiniz parametre kaldırır **parametre listesi** listeden.  
  
- **Parametre listesi**

   Tüm parametreler ve değiştiriciler ve şu anda yöntemi için eklenen türleri görüntüler. Parametre ekleme gibi sihirbaz güncelleştirir **parametre listesi** değiştiricisi ve türü her parametre görüntülenecek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Yöntem ekleme](../ide/adding-a-method-visual-cpp.md)<br/>
[IDL Öznitelikleri, Yöntem Ekleme Sihirbazı](../ide/idl-attributes-add-method-wizard.md)