---
title: Bağlantı noktası Sihirbazı'nı uygulamak | Microsoft Docs
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
ms.openlocfilehash: ef2f7efa92de3714170e403ea50b5f486c8367d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="implement-connection-point-wizard"></a>Bağlantı Noktası Uygulama Sihirbazı
Bu sihirbaz bir COM nesnesi için bir bağlantı noktası uygular. Bağlanılabilirlik nesne (diğer bir deyişle, bir kaynak) bir bağlantı noktası veya herhangi bir giden arabirimi kendi arabirimleri için getirebilir. Visual C++ hem de Windows giden arabirimine sahip türü kitaplıkları sağlar. Her giden arabirimi, bir nesne (diğer bir deyişle, bir havuz) istemci tarafından uygulanabilir.  
  
 Daha fazla bilgi için bkz: [ATL bağlantı noktaları](../atl/atl-connection-points.md).  
  
 **Kullanılabilir tür kitaplıkları**  
 Bağlantı noktaları uygulayabilirsiniz arabirimi tanımlarını içeren kullanılabilir tür kitaplıklarını görüntüler. Kullanmak için tür kitaplığı içeren bir dosyayı bulmak için üç nokta düğmesini tıklatın.  
  
 **Konum**  
 Şu anda seçili tür kitaplığı konumunu görüntüler **kullanılabilir tür kitaplıklarının** listesi.  
  
 **Arabirimler**  
 Tanımları, şu anda seçili tür kitaplığı içerdiği arabirimleri görüntüler **kullanılabilir tür kitaplıklarının** kutusu.  
  
|Aktarma düğmesi|Açıklama|  
|---------------------|-----------------|  
|**>**|Ekler **uygulamak bağlantı noktaları** geçerli seçili arabirim adı listesi **arabirimleri** listesi.|  
|**>>**|Ekler **uygulamak bağlantı noktaları** bulunan tüm arabirim adlarını listelemek **arabirimleri** listesi.|  
|**<**|Şu anda seçili arabirim adı kaldırır **uygulamak bağlantı noktaları** listesi.|  
|**<<**|Tüm arabirim şu anda listelenen adları kaldırır **uygulamak bağlantı noktaları** listesi.|  
  
 **Uygulama bağlantı noktaları**  
 Kendisi için uygulamanız bağlantı noktaları tıkladığınızda arabirimleri adlarını görüntüler **son**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir bağlantı noktası uygulama](../ide/implementing-a-connection-point-visual-cpp.md)