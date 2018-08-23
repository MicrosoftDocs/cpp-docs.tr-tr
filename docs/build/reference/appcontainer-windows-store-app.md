---
title: / APPCONTAINER (UWP/Microsoft Store uygulaması) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eab6a9bd8ac37dec250739e3554c370726dce9eb
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589583"
---
# <a name="appcontainer-microsoft-store-app"></a>/ APPCONTAINER (Microsoft Store uygulaması)
Bağlayıcı, bir uygulama kapsayıcısında çalıştırılması gereken bir yürütülebilir görüntü oluşturup oluşturmayacağını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak/appcontaıner kapalıdır.  
  
 Bu seçenek, uygulamanın appcontainer işlem yalıtımı ortamında çalıştırılması gereken olup olmadığını belirtmek için bir yürütülebilir dosya değiştirir. Ortamında çalıştırılması gereken bir uygulama için/appcontaıner belirtin — örneğin, Evrensel Windows Platformu (UWP) veya Windows Phone 8.x uygulaması. (Bir şablondan bir evrensel Windows uygulaması oluştururken seçeneğini otomatik olarak Visual Studio'da ayarlanır.) Bir masaüstü uygulaması için /APPCONTAINER:NO belirtin veya seçeneği atlayın.  
  
 / Appcontaıner seçeneği, Windows 8'de sunulmuştur.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Genişletin **yapılandırma özellikleri** düğümü.  
  
3.  Genişletin **bağlayıcı** düğümü.  
  
4.  Seçin **komut satırı** özellik sayfası.  
  
5.  İçinde **ek seçenekler**, girin `/APPCONTAINER` veya `/APPCONTAINER:NO`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)