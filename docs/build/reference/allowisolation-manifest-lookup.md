---
title: -ALLOWISOLATION (bildirim arama) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f467ff467d785d17601737436e0eb1ff972f37
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205499"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Bildirim Arama)
Bildirim arama davranışını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/ALLOWISOLATION:No** DLL'ler yüklü hiçbir bildirim olduysa olarak gösterir ve ayarlamak bağlayıcı neden `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` isteğe bağlı üst bilgisinde ait bit `DllCharacteristics` alan.  
  
 **/ ALLOWISOLATION** aramalar ve yükleri bildirim işletim sisteminin neden olur.  
  
 **/ ALLOWISOLATION** varsayılandır.  
  
 Bir yürütülebilir dosya için yalıtım devre dışı bırakıldığında, yeni oluşturulan işlem için bir uygulama bildirimi bulmak Windows Yükleyici denemez. Yeni işlem olsa bile bir bildirim yürütülebilir veya yürütülebilir dosya adı ile aynı dizine yerleştirilmiştir içinde varsayılan etkinleştirme bağlamı olmaz <em>yürütülebilir dosya adı</em>**. exe.manifest**.  
  
 Daha fazla bilgi için [bildirim dosyaları başvuru](/windows/desktop/SbsCs/manifest-files-reference).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Genişletin **yapılandırma özellikleri** düğümü.  
  
3.  Genişletin **bağlayıcı** düğümü.  
  
4.  Seçin **bildirim dosyası** özellik sayfası.  
  
5.  Değiştirme **izin yalıtım** özelliği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)