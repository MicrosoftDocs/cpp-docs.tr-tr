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
ms.openlocfilehash: ac71d4713a71833886e577106f4bd8fd6565014a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410617"
---
# <a name="names-add-property-wizard"></a>Adlar, Özellik Ekleme Sihirbazı

Bir özellik için bir arabirim eklemek için bu sihirbazı kullanın.

- **Özellik türü**

   Eklemekte olduğunuz özelliğin türünü ayarlar. MFC görüntüleme, kendi türü sağlayın veya önceden tanımlanmış bir listeden seçin. Bir özellik, bir stok uygulamasına sağlarsanız **özellik türü** stok türüne ayarlanır ve değişiklik için kullanılamıyor.

- **Özellik adı**

   Özelliğin adını ayarlar. MFC ActiveX denetimleri ile ilişkili görüntü arabirimlerinde, kendi adınızı sağlayabilir veya stok özellik adı önceden tanımlanmış bir listeden seçebilirsiniz. Kendi özellik adı sağlarsanız **hisse senedi** uygulama türü kullanılamaz. Bkz: [stok özellikleri](../ide/stock-properties.md) listesinde özellikleri açıklaması.

   |Arabirim türü|Açıklama|
   |--------------------|-----------------|
   |ATL çift arabirim, özel arabirim ve yerel özel arabirimi|Bir özellik adı belirtin.|
   |MFC dispinterface, MFC ActiveX denetimi dispinterface|Bir özellik adı belirtin veya listeden bir stok özellik seçin. Listeden bir özellik seçerseniz, uygun değere görünür **özellik türü** kutusu. Bu türü altında yaptığınız seçime bağlı olarak değiştirebileceğiniz **uygulama türü**.|

- **Dönüş türü**

   ATL yalnızca arabirimleri. Özelliğinin dönüş türünü ayarlar. Çift arabirimler için `HRESULT` her zaman dönüş türü ve bu kutusu kullanılamaz. Özel arabirimler için listeden bir dönüş türü seçebilirsiniz. `HRESULT` hatalarını döndürmek için standart bir yolu sağladığından yine de önerilir.

- **Değişken adı**

   Yalnızca MFC görüntüleme. Yalnızca belirlediğinizde kullanılabilir **üye değişkeni** altında **uygulama türü**. Özelliği ilişkili olduğu üye değişkeninin adını ayarlar. Varsayılan olarak, değişken adı m_ için ayarlanmış*PropertyName*. Bu ad düzenleyebilirsiniz.

- **Bildirim işlevi**

   Yalnızca MFC görüntüleme. Yalnızca belirlediğinizde kullanılabilir **üye değişkeni** altında **uygulama türü**. Özellik değişiklikleri bildirim işlevi çağrılan if adını ayarlar. Varsayılan olarak, bildirim işlevin adını üzerinde ayarlanır*PropertyName*değiştirildi. Bu ad düzenleyebilirsiniz.

- **Get işlevi**

   MFC görüntüleme için. Yalnızca belirlediğinizde kullanılabilir **Get/Set yöntemleri** altında **uygulama türü**. Özellik get yapılmaya işlevin adını ayarlar. Varsayılan olarak, Get kümesinin Get işlevi adı*PropertyName*. Bu ad düzenleyebilirsiniz. İşlev adı silerseniz [GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported) arabirimi gönderme eşlemesine eklenir. Get*PropertyName* işlevi belirtir özelliği olarak okunabilir.

- **Set işlevi**

   Yalnızca MFC görüntüleme. Yalnızca belirlediğinizde kullanılabilir **Get/Set yöntemleri** altında **uygulama türü**. Özellik ayarlamak için işlevin adını ayarlar. Varsayılan olarak, kümeye kümesinin Set işlevi adı*PropertyName*. Bu ad düzenleyebilirsiniz. İşlev adı silerseniz [SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported) arabirimi gönderme eşlemesine eklenir. Belirlenen*PropertyName* işlevi özelliği yazılabilir olduğunu belirtir.

- **Uygulama türü**

   Yalnızca MFC görüntüleme. Eklemekte olduğunuz işleminin özelliği uygulayan nasıl belirtir.

   |Uygulama türü|Açıklama|
   |-------------------------|-----------------|
   |**Hisse senedi**|Seçili özellik için bir stok uygulama belirtir **özellik adı**. Varsayılan. Bkz: [stok özellikleri](../ide/stock-properties.md) daha fazla bilgi için.<br /><br /> Belirtirseniz **hisse senedi**, ardından **özellik türü**, **parametre türü**, ve **parametre adı** soluklaştırılır.|
   |**Üye değişkeni**|Özellik olarak bir üye değişkeni eklenir belirtir. Özel özellikler veya stok özelliklerinin çoğu üye değişkenleri ekleyebilirsiniz. Belirtemezsiniz **üye değişkeni** için **açıklamalı alt yazı**, **hWnd**, ve **metin** özellikleri.<br /><br /> Varsayılan adlarla sağlar **değişken adı** ve **bildirim işlevini**. Bu ad düzenleyebilirsiniz.|
   |**Get/Set yöntemleri**|Özellik Get eklenen belirtir*PropertyName* ve*PropertyName* varsayılan işlevler. Bu adları altında görünür **alma işlevi** ve **Set işlevi**.<br /><br /> Varsayılan olarak değiştirebilirsiniz **özellik türü**, Get işlevi için bir değer geçirir. Parametreler için belirtebileceğiniz **alma** ve `Set` işlevleri.|

- **Get işlevi**

   ATL arabirimleri. Özelliği, okunamaz olarak ayarlar; diğer bir deyişle, oluşturduğu **alma** nesneden bu özelliği almak için yöntemi. Seçmelisiniz **alma**, `Put`, veya her ikisini de.

- **Put işlevi**

   ATL yalnızca arabirimleri. Özelliği yazılabilir ayarlar; diğer bir deyişle, oluşturduğu `Put` ayarlanması veya "ekledikçe," nesnesinin bu özelliği için yöntemi. Seçmelisiniz **alma**, `Put`, veya her ikisini de. Bu seçeneği belirlerseniz yöntemi uygulamak için aşağıdaki iki yoldan seçebilirsiniz:

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**PropPut**|[PropPut](../windows/propput.md) işlev nesnesinin bir kopyasını döndürür. Varsayılan ve özellik yazılabilir yapmak için en yaygın yolu budur.|
   |**PropPutRef**|[PropPutRef](../windows/propputref.md) işlev nesnesinin kopyasını döndüren yerine nesneye bir başvuru döndürür. Büyük yapılar veya başlatma yükü olabilecek diziler gibi nesneler için bu seçeneği kullanmayı düşünün.|

- **Parametre öznitelikleri**

   ATL yalnızca arabirimleri. Parametresi tarafından belirtilen ayarlar **parametre adı** olduğu **içinde**, **kullanıma**, her ikisi de veya yok.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**in**|Parametrenin çağıran yordamdan çağrılan yordama geçirildiğini gösterir.|
   |**out**|İşaretçi parametresi çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülür gösterir.|

- **Parametre türü**

   Parametrenin veri türünü ayarlar. Türü listeden seçin.

- **Parametre adı**

   Özelliği parametreleri varsa özelliği için eklediğiniz bir parametre adını ayarlar. ' A tıkladığınızda **Ekle**, parametre adı görünür **parametre listesi**.

- **Parametre listesi**

   Özelliğine eklenecek özniteliklerin listesini görüntüler. Listedeki her öğe, parametre adı, parametre türü ve öznitelikleri oluşur. Kullanım **Ekle** ve **Kaldır** listesini güncelleştirmek için.

- **Add**

   Belirttiğiniz parametre ekler **parametre adı** ve **parametre türü** için **parametre listesi**. ' A tıklamalıdır **Ekle** parametre listesine eklenecek.

- **Kaldır**

   Seçtiğiniz parametre kaldırır **parametre listesi**.

- **Varsayılan özellik**

   Yalnızca MFC dispinterface. Bu özellik, arabirim için varsayılan olarak ayarlar. Özelliği yalnızca bir varsayılan arabirim olabilir; Bu kutuyu arabirimi, eklediğiniz diğer tüm özellikler için varsayılan özelliği belirttiğinizde kullanılamaz.

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik ekleme](../ide/adding-a-property-visual-cpp.md)<br>
[IDL Öznitelikleri, Özellik Ekleme Sihirbazı](../ide/idl-attributes-add-property-wizard.md)<br>
[Arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md)