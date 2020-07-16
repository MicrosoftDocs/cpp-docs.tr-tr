---
title: Tür Kitaplığı Sihirbazından Sınıf Ekleme
ms.date: 05/09/2019
helpviewer_keywords:
- COM interfaces, adding classes
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
ms.openlocfilehash: 6fa1dd3985fd5b565bcc4b4727f41960d1f4f5d0
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86405136"
---
# <a name="add-class-from-typelib-wizard"></a>Tür Kitaplığı Sihirbazından Sınıf Ekleme

::: moniker range="vs-2019"

Bu sihirbaz, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=vs-2017"

Kullanılabilir bir tür kitaplığından bir MFC sınıfı eklemek için bu sihirbazı kullanın. Sihirbaz, seçilen tür kitaplığından eklediğiniz her arabirim için bir sınıf oluşturur.

- **Sınıf Ekle**

   Sınıfın oluşturulduğu tür kitaplığının konumunu belirtir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Kapsayıcı Kayıt Defteri**|Tür kitaplığı sisteme kaydedilir. Kayıtlı tür kitaplıkları **kullanılabilir tür kitaplıklarında**listelenmiştir.|
   |**Dosya**|Tür kitaplığının sistemde kayıtlı olması gerekmez, ancak bir dosyada yer alır. Dosya konumunu **konuma**sağlamanız gerekir.|

- **Kullanılabilir tür kitaplıkları**

   Sistemde kayıtlı olan tür kitaplıklarını listeler. Arabirimlerini **arabirimler** listesinde göstermek için bu listeden bir tür kitaplığı seçin.

- **Konum**

   Tür kitaplığının konumunu belirtir. **Sınıfından sınıf Ekle**altında **Dosya** ' ya tıklarsanız, tür kitaplığını içeren dosyanın konumunu sağlayabilirsiniz. Dosyanın konumuna gitmek için üç nokta düğmesine tıklayın.

- **Arabirimler**

   **Kullanılabilir tür kitaplıkları** listesinde şu anda seçili olan tür kitaplığındaki arabirimleri listeler.

   |Aktar düğmesi|Açıklama|
   |---------------------|-----------------|
   |**>**|**Arabirimler** listesinde seçili olan arabirimi ekler. Hiçbir arabirim seçilmezse soluk.|
   |**>>**|**Kullanılabilir tür kitaplıkları** listesinde seçili olan tür kitaplığındaki tüm arabirimleri ekler.|
   |**\<**|**Oluşturulan sınıflar** listesinde şu anda seçili olan sınıfı kaldırır. **Oluşturulan sınıflar** listesinde hiçbir sınıf seçili değilse soluk.|
   |**\<\<**|**Oluşturulan sınıflar** listesindeki tüm sınıfları kaldırır. **Oluşturulan sınıflar** listesi boşsa soluk olur.|

- **Oluşturulan sınıflar**

   Or düğmesi kullanılarak eklenen arabirimlerde oluşturulacak sınıf adlarını belirtir **>** **>>** . Bir sınıf seçmek için bu kutuya tıklayabilir ve ardından listede gezinmek için yukarı veya aşağı tuşlarını kullanabilir, sonra da **son**' a tıkladığınızda sihirbazın ürettiği **Dosya** kutusundaki **sınıf** kutusu ve dosya adı ' nda her bir sınıf adını görüntüleyebilirsiniz. Bu kutuda tek seferde yalnızca bir sınıf seçebilirsiniz.

   Bir sınıfı bu listede seçip öğesini tıklatarak kaldırabilirsiniz **<** . Tüm sınıfları kaldırmak için oluşturulan sınıflar kutusunda bir sınıf seçmeniz gerekmez; öğesine tıklayarak **<<** , **oluşturulan sınıflar** kutusundaki tüm sınıfları kaldırırsınız.

- **Sınıf**

   **Son**' a tıkladığınızda sihirbazın eklediği **oluşturulan sınıflar** kutusunda seçilen sınıfın adını belirtir. **Sınıf** kutusunda adı düzenleyebilirsiniz.

- **Dosya**

   Yeni sınıf için üst bilgi dosyasının adını ayarlar. Varsayılan olarak, bu ad, **üretilen sınıflarda**sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini tıklatın. Var olan bir dosyayı seçerseniz, sihirbazda **son** ' a tıklaana kadar sihirbaz onu seçilen konuma kaydetmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda, sihirbaz sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Bir tür kitaplığından MFC sınıfı](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)<br/>
[Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](../../mfc/automation-clients-using-type-libraries.md)
