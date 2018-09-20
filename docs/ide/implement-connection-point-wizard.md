---
title: Uygulama bağlantı noktası Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.impl.cp.overview
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92312bc130ed24f2aafe2e4b95e2c4bcf6381215
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429675"
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