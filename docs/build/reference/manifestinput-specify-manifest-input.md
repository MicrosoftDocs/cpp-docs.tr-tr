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
ms.openlocfilehash: d1b5ed266f1b8929deee3ffb60a10b18b7604afc
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42464770"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (Bildirim Girişini Belirt)
Görüntüde gömülü bildirimi eklemek için bildirim giriş dosyasını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/MANIFESTINPUT:filename  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Katıştırılmış bildirime dahil edilecek bildirim dosyası.  
  
## <a name="remarks"></a>Açıklamalar  
 **/MANIFESTINPUT** seçeneği, yürütülebilir bir görüntüde gömülü bildirimi oluşturmak için kullanılacak bir girdi dosyasının yolunu belirtir. Giriş dosyalarını, birden çok kez anahtar kullanmak birden çok bildirim varsa — her giriş dosyası için bir kez. Bildirim giriş dosyaları katıştırılmış bildirim oluşturmak üzere birleştirilir. Bu seçenek gerektirir **/MANIFEST: ekleme** seçeneği.  
  
 Bu seçenek, doğrudan Visual Studio'nun içinde olacak şekilde ayarlanamaz. Bunun yerine, **ek bildirim dosyaları** dahil etmek için ek bildirim dosyaları belirtmek için projenin özelliği. Daha fazla bilgi için [girdi ve çıktı, bildirim aracı, yapılandırma özellikleri, \<Projectname > özellik sayfaları iletişim kutusu](../../ide/input-and-output-manifest-tool.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)