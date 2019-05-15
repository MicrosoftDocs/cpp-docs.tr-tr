---
title: Tür Kitaplığı Sihirbazından Sınıf Ekleme
ms.date: 05/09/2019
helpviewer_keywords:
- COM interfaces, adding classes
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
ms.openlocfilehash: 7a866c0e6b772a992f5ae81dbb17646765f172e6
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708332"
---
# <a name="add-class-from-typelib-wizard"></a>Tür Kitaplığı Sihirbazından Sınıf Ekleme

::: moniker range="vs-2019"

Bu sihirbaz, Visual Studio 2019 bulunan ve daha yeni değil.

::: moniker-end

::: moniker range="<=vs-2017"

Bir kullanılabilir tür kitaplığından bir MFC sınıfı eklemek için bu sihirbazı kullanın. Sihirbaz, seçilen tür kitaplığından eklediğiniz her arabirim için bir sınıf oluşturur.

- **Şuradan Sınıf Ekle**

   Tür kitaplığının sınıf oluşturulduğu konumu belirtir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Kayıt defteri**|Tür kitaplığını sistemde kayıtlı. Kayıtlı bir tür kitaplığı içinde listelenen **kullanılabilir tür kitaplıklarını**.|
   |**Dosya**|Tür kitaplığını mutlaka sistemde kayıtlı değil ancak bir dosyada yer alır. Dosya konumunda sağlamalısınız **konumu**.|

- **Kullanılabilir tür kitaplıkları**

   Şu anda sistemde kayıtlı tür kitaplıkları listeler. Bu listeden arabirimlerinden içinde görüntülemek için bir tür kitaplığını seçin **arabirimleri** listesi.

   Bkz: "içinde dağıtılmış COM: Kitaplıkları ve dil tümleştirme tür kitaplıklarını kaydetme hakkında daha fazla bilgi için MSDN Kitaplığı'nda tür".

- **Konum**

   Tür kitaplığının konumu belirtir. Tıklarsanız **dosya** altında **sınıfı gelen ekleme**, tür kitaplığı içeren dosyanın konumunu sağlayabilir. Dosyasının konumuna göz atmak için üç nokta düğmesine tıklayın.

- **Arabirimler**

   Tür kitaplığı şu anda seçili arabirimlerde listeler **kullanılabilir tür kitaplıklarını** listesi.

   |Aktarım düğmesi|Açıklama|
   |---------------------|-----------------|
   |**>**|Şu anda seçili arabirimi ekler **arabirimleri** listesi. Herhangi bir arabirim seçtiyseniz soluk.|
   |**>>**|Şu anda seçili tür kitaplığındaki tüm arabirimleri ekler **kullanılabilir tür kitaplıklarını** listesi.|
   |**\<**|Şu anda seçili sınıfını kaldırır **sınıfları oluşturulan** listesi. Hiçbir sınıf içinde seçilirse soluk **sınıfları oluşturulan** listesi.|
   |**\<\<**|Tüm sınıfları kaldırır **sınıfları oluşturulan** listesi. Soluk bir IF **sınıfları oluşturulan** listesi boş.|

- **Oluşturulan sınıflar**

   Sınıf adları kullanılarak eklenen arabirimlerinden oluşturulacak belirtir **>** veya **>>** düğmesi. Bir sınıf seçin ve ardından yukarı veya aşağı tuşlarını kullanarak, listede gezinmek için bu kutuyu her sınıf adını görüntüleme tıklayabilirsiniz **sınıfı** kutusu ve dosya adı **dosya** kutusu sihirbaz ne zaman oluşturur, tıklayın **son**. Bu kutuya bir kerede yalnızca bir sınıf seçebilirsiniz.

   Bu listede seçerek ve tıklatarak bir sınıf kaldırabilirsiniz **<**. Tüm sınıflar kaldırmak için oluşturulan sınıflar kutusunda bir sınıf seçin gerekmez; tıklayarak **<<**, içindeki tüm sınıflar Kaldır **sınıfları oluşturulan** kutusu.

- **Sınıfı**

   Seçilen sınıfın adını belirtir **sınıfları oluşturulan** tıkladığınızda sihirbaz ekler kutusu **son**. Adlarında düzenleyebileceğiniz **sınıfı** kutusu.

- **Dosya**

   Yeni bir sınıf için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıfları oluşturulan**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Tür kitaplığından MFC sınıfı](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)<br/>
[Otomasyon İstemcileri: Tür Kitaplıkları Kullanma](../../mfc/automation-clients-using-type-libraries.md)
