---
title: -MANIFESTINPUT (bildirim girişini belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eecf1740855c2feef0d7cac4bbcc85ad95eade6f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372857"
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