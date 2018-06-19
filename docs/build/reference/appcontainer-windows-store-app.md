---
title: / APPCONTAINER (UWP/Microsoft mağazası uygulaması) | Microsoft Docs
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
ms.openlocfilehash: 8ca1a3ed5adaada689d374eeb3e67bae6c989e0b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369298"
---
# <a name="appcontainer-microsoft-store-app"></a>/ APPCONTAINER (Microsoft mağazası uygulaması)
Bağlayıcı bir uygulama kapsayıcısında çalıştırılmalıdır yürütülebilir bir görüntü oluşturup oluşturmayacağını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, /APPCONTAINER kapalıdır.  
  
 Bu seçenek, uygulama ve appcontaıner işlem yalıtımı ortamında çalışan olup olmadığını belirtmek için yürütülebilir bir dosya değiştirir. Appcontaıner ortamında çalışması gereken bir uygulama için /APPCONTAINER belirtin — örneğin, bir evrensel Windows Platformu (UWP) veya Windows Phone 8.x uygulaması. (Bir şablondan bir evrensel Windows uygulaması oluşturma seçeneği otomatik olarak Visual Studio'da ayarlanır.) Bir masaüstü uygulamasının /APPCONTAINER:NO belirtin veya yalnızca seçeneğini atlayın.  
  
 /APPCONTAINER seçeneği sunulmuştur [!INCLUDE[win8](../../build/reference/includes/win8_md.md)].  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneği ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **komut satırı** özellik sayfası.  
  
5.  İçinde **ek seçenekler**, girin `/APPCONTAINER` veya `/APPCONTAINER:NO`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)