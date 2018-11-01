---
title: Bağlantı Noktası Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.impl.cp.overview
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
ms.openlocfilehash: b818a1a149e95805a8694f6c8d8d1325b33211b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531540"
---
# <a name="implement-connection-point-wizard"></a>Bağlantı Noktası Uygulama Sihirbazı

Bu sihirbaz bir COM nesnesi için bir bağlantı noktası uygular. Bağlanılabilirlik bir nesne (diğer bir deyişle, bir kaynak) bir bağlantı noktası kendi arabirimleri veya herhangi bir giden arabirimi üzerinden kullanıma sunabilirsiniz. Visual C++ hem de Windows giden arabirimlere sahip tür kitaplıkları sağlar. Giden her arabirim bir istemcide bir nesnenin (diğer bir deyişle, bir havuz) tarafından uygulanabilir.

Daha fazla bilgi için [ATL bağlantı noktaları](../atl/atl-connection-points.md).

- **Kullanılabilir tür kitaplıkları**

   Bağlantı noktaları uygulayabileceğiniz arabirim tanımlarını içeren kullanılabilir tür kitaplıklarını görüntüler. Tür kitaplığı içeren bir dosyayı bulmak için üç nokta düğmesine tıklayın.

- **Konum**

   Şu anda seçilen tür kitaplığının konumu görüntüler **kullanılabilir tür kitaplıklarını** listesi.

- **Arabirimler**

   Görüntüler, tanımları, şu anda seçili tür kitaplığı içerdiği arabirimleri **kullanılabilir tür kitaplıklarını** kutusu.

   |Aktarım düğmesi|Açıklama|
   |---------------------|-----------------|
   |**>**|Ekler **uygulamak bağlantı noktaları** geçerli seçili arabirim adı listesi **arabirimleri** listesi.|
   |**>>**|Ekler **uygulamak bağlantı noktaları** bulunan tüm arabirimi adlarını listelemek **arabirimleri** listesi.|
   |**\<**|Şu anda seçili arabirim adını kaldırır **uygulamak bağlantı noktaları** listesi.|
   |**\<\<**|Şu anda listelenen adları tüm arabirim kaldırır **uygulamak bağlantı noktaları** listesi.|

- **Uygulama bağlantı noktaları**

   Kendisi için uygulamanız bağlantı noktaları tıkladığınızda arabirimleri adlarını görüntüler **son**.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlantı noktasını uygulama](../ide/implementing-a-connection-point-visual-cpp.md)