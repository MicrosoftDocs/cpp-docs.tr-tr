---
title: "-HIGHENTROPYVA (64 Bit ASLR desteği) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 059f6169cafc48fc67587ae2f5827966269e6ac7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)