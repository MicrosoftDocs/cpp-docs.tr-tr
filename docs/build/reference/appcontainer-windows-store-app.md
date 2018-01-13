---
title: "-APPCONTAINER (Windows mağazası uygulamaları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22ca7bec885f20518950626d33f7e3af553d0d52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="appcontainer-windows-store-app"></a>/APPCONTAINER (Windows Mağazası Uygulamaları)
Bağlayıcı bir uygulama kapsayıcısında çalıştırılmalıdır yürütülebilir bir görüntü oluşturup oluşturmayacağını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, /APPCONTAINER kapalıdır.  
  
 Bu seçenek, uygulama ve appcontaıner işlem yalıtımı ortamında çalışan olup olmadığını belirtmek için yürütülebilir bir dosya değiştirir. Appcontaıner ortamında çalışması gereken bir uygulama için /APPCONTAINER belirtin — örneğin, bir [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] uygulama. (Oluşturduğunuzda seçenek Visual Studio'da otomatik olarak ayarlanır bir [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] bir şablon uygulamadan.) Bir masaüstü uygulamasının /APPCONTAINER:NO belirtin veya yalnızca seçeneğini atlayın.  
  
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