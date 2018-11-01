---
title: ActiveX Denetimi Sihirbazından Sınıf Ekleme
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.axcontrol
helpviewer_keywords:
- ActiveX Control Wizard
- Add Class from ActiveX Control Wizard [C++]
ms.assetid: 668d801c-5fb6-4176-9191-5c38995a4713
ms.openlocfilehash: 736ac50f14d8434584c6f47b2953913c79b0b00a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472494"
---
# <a name="add-class-from-activex-control-wizard"></a>ActiveX Denetimi Sihirbazından Sınıf Ekleme

Kullanılabilir ActiveX denetiminden MFC sınıfı eklemek için bu sihirbazı kullanın. Sihirbaz seçilen ActiveX denetiminden eklediğiniz her arabirim için bir sınıf oluşturur.

- **Şuradan Sınıf Ekle**

   Tür kitaplığının sınıf oluşturulduğu konumu belirtir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Kayıt defteri**|Tür kitaplığını sistemde kayıtlı. Kayıtlı bir tür kitaplığı içinde listelenen **kullanılabilir ActiveX denetimleri**.|
   |**Dosya**|Tür kitaplığını mutlaka sistemde kayıtlı değil ancak bir dosyada yer alır. Dosya konumunda sağlamalısınız **konumu**.|

- **Kullanılabilir ActiveX denetimleri**

   Şu anda sistemde kayıtlı ActiveX denetimleri belirtir. ActiveX denetimi arabirimlerinden içinde görüntülemek için bu listeden seç **arabirimleri** listesi. Bkz: [MFC ActiveX denetimleri: ActiveX denetimlerini dağıtma](../mfc/mfc-activex-controls-distributing-activex-controls.md) ActiveX denetimlerini kaydetme hakkında daha fazla bilgi.

   Tıklarsanız **dosya** altında **sınıfı gelen ekleme**, bu kutusuna değişiklik için kullanılamıyor.

- **Konum**

   ActiveX denetimi konumunu belirtir. Tıklarsanız **dosya** altında **sınıfı gelen ekleme**, tür kitaplığı içeren dosyanın konumunu sağlayabilir. Dosyasının konumuna göz atmak için üç nokta düğmesine tıklayın.

   Tıklarsanız **kayıt defteri** altında **sınıfı gelen ekleme**, bu kutusuna değişiklik için kullanılamıyor.

- **Arabirimler**

   Şu anda seçilen ActiveX denetimi arabirimler belirtir **kullanılabilir ActiveX denetimleri** veya belirtilen dosya tür kitaplığındaki **konumu**.

   |Aktarım düğmesi|Açıklama|
   |---------------------|-----------------|
   |**>**|Şu anda seçili arabirimi ekler **arabirimleri** listesi. Herhangi bir arabirim seçilirse kullanılabilir.|
   |**>>**|Tüm arabirimleri içinde seçili ActiveX denetimi ekler **kullanılabilir ActiveX denetimleri** veya belirtilen dosya tür kitaplığındaki **konumu**.|
   |**\<**|Şu anda seçili sınıfını kaldırır **sınıfları oluşturulan** listesi. Hiçbir sınıf içinde seçtiyseniz, kullanılabilir **sınıfları oluşturulan** listesi.|
   |**\<\<**|Tüm sınıfları kaldırır **sınıfları oluşturulan** listesi. Kullanılabilir ise **sınıfları oluşturulan** listesi boş.|

- **Oluşturulan sınıflar**

   Sınıf adları kullanılarak eklenen arabirimlerinden oluşturulacak belirtir **>** veya **>>** düğmesi. Bir sınıf seçin ve ardından yukarı veya aşağı tuşlarını kullanarak, listede gezinmek için bu kutuyu her sınıf adını görüntüleme tıklayabilirsiniz `Class` kutusu ve dosya adı **.h dosyası** tıkladığınızda, sihirbazın oluşturduğu kutusu  **Son**. Bu kutuya bir kerede yalnızca bir sınıf seçebilirsiniz.

   Bu listede seçerek ve tıklatarak bir sınıf kaldırabilirsiniz **<**. Bir sınıfta seçmek gerekmez **sınıfları oluşturulan** tıklayarak; tüm sınıflar Kaldır kutusunun **<<**, içindeki tüm sınıflar Kaldır **sınıfları oluşturulan** bir kutu.

- **Sınıfı**

   Seçilen sınıfın adını belirtir **sınıfları oluşturulan** tıkladığınızda sihirbaz ekler kutusu **son**. Adlarında düzenleyebileceğiniz **sınıfı** kutusu.

- **.h dosyası**

   Yeni nesne sınıfı için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıfları oluşturulan**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **.cpp dosyası**

   Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıfları oluşturulan**. Dosya adı, tercih ettiğiniz bir konuma kaydetmek için üç nokta düğmesine tıklayın. ' A kadar dosyasını seçili konuma kaydedilmez **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf uygulaması dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

## <a name="see-also"></a>Ayrıca Bkz.

[ActiveX denetiminden sınıf ekleme](../ide/adding-a-class-from-an-activex-control-visual-cpp.md)<br>
[Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](../mfc/automation-clients-using-type-libraries.md)