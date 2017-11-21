---
title: "-HIGHENTROPYVA (64 Bit ASLR desteği) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37bbc9330984eca85e96e1e2a4a2b3b7942a5642
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (64 Bit ASLR Destekle)
Yürütülebilir görüntü yüksek entropi 64-bit adres boşluğu düzeni rastgele seçimini (ASLR) desteklediğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, / highentropyva 64-bit yürütülebilir görüntüler açıktır. 32-bit yürütülebilir görüntüler için geçerli değildir. Bu seçeneği etkinleştirmek için /DYNAMICBASE ayrıca üzerinde olmalıdır.  
  
 / HIGHENTROPYVA bir .dll veya .exe dosyasının ASLR 64-bit adresleriyle desteklenip desteklenmediğini belirtmek için üstbilgisinin değiştirir. Bu seçenek, yürütülebilir bir dosya ve tüm bağımlı modülleri ayarlandığında, 64 bit ASLR destekleyen bir işletim sistemi yürütülebilir görüntü parçalarını yükleme zamanında bir 64-bit sanal adres alanı rastgele adreslerini kullanarak rebase. Bu büyük adres alanı bir saldırganın belirli bellek bölge konumunu tahmin edilmesi daha zor hale getirir.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneği ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **komut satırı** özellik sayfası.  
  
5.  İçinde **ek seçenekler**, girin `/HIGHENTROPYVA` veya `/HIGHENTROPYVA:NO`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)