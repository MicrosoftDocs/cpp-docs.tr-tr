---
title: "-MANIFESTINPUT (bildirim girişini belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e1eec78675845e3f738bb0b6b440b3a71f1fd572
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (Bildirim Girişini Belirt)
Görüntüde katıştırılmış bildirimi dahil etmek için bir bildirim giriş dosyası belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/MANIFESTINPUT:filename  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Katıştırılmış bildiriminde dahil etmek için bildirim dosyası.  
  
## <a name="remarks"></a>Açıklamalar  
 **/MANIFESTINPUT** seçeneği gömülü bildirim yürütülebilir bir görüntü oluşturmak için kullanılacak bir giriş dosyası yolunu belirtir. Giriş dosyaları, birden çok kez anahtarını kullanın birden çok bildirim varsa — her giriş dosyası için bir kez. Bildirim girdi dosyaları katıştırılmış bildirimi oluşturmak için birleştirilir. Bu seçenek gerektirir **/bildirimi: KATIŞTIRMAK** seçeneği.  
  
 Bu seçenek doğrudan ayarlanamaz [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Bunun yerine, kullanın **ek bildirim dosyaları** dahil etmek için ek bildirim dosyaları belirtmek için projesinin özelliği. Daha fazla bilgi için bkz: [giriş ve çıkış, bildirim aracı, yapılandırma özellikleri \<Projectname > özellik sayfaları iletişim kutusu](../../ide/input-and-output-manifest-tool.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)