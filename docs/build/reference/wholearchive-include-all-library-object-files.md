---
title: "-WHOLEARCHIVE (tüm kitaplık nesnesi dosyaları dahil) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3499d6583c7d9801aa4c3b12c66196c975b192ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wholearchive-include-all-library-object-files"></a>/ WHOLEARCHIVE (tüm kitaplık nesnesi dosyaları içerir)
Force bağlayıcı bağlantılı yürütülebilir statik kitaplığındaki tüm nesne dosyaları içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
> / WHOLEARCHIVE [:*Kitaplığı*]  
  
## <a name="remarks"></a>Açıklamalar  
  
/WHOLEARCHIVE seçeneği her nesne dosyasından ya da belirtilen bir statik kitaplık dahil etmek veya bağlantısını belirtilen tüm statik kitaplıklarından kitaplık belirtilmezse, komut için bağlayıcı zorlar. Birden çok kitaplıkları /WHOLEARCHIVE seçeneği belirtmek için birden fazla /WHOLEARCHIVE geçiş bağlayıcı komut satırında kullanabilirsiniz. Yalnızca diğer nesne yürütülebilir dosyalarında başvurduğu simgeleri veriyorsanız varsayılan olarak, bağlayıcı bağlantılı çıkış nesne dosyaları içerir. Bağlayıcı komut satırında ayrı ayrı belirtilmiş olması gibi bir statik kitaplık arşivlenen tüm nesne dosyaları kabul bağlayıcı /WHOLEARCHIVE seçenektir.  
  
/WHOLEARCHIVE seçeneği statik kitaplığından tüm sembolleri yeniden vermek için kullanılabilir. Bir bileşenin birden fazla statik kitaplığından oluşturduğunuzda, tüm kitaplık kodu, kaynakları ve meta verileri dahil edildiğinden emin olmanızı sağlar. Windows çalışma zamanı bileşenleri dışa aktarma için bir statik kitaplık oluşturduğunuzda LNK4264 uyarı içeriyor görürseniz, bu kitaplığın başka bir bileşeni ya da uygulama bağlama /WHOLEARCHIVE seçeneği kullanın.  
  
/WHOLEARCHIVE seçeneği Visual Studio 2015 güncelleştirme 2'de sunulmuştur.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneği ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
1.  Seçin **komut satırı** altında özellik sayfası **yapılandırma özellikleri**, **bağlayıcı**.  
  
1.  /WHOLEARCHIVE seçeneğine eklemek **ek seçenekler** metin kutusu.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)