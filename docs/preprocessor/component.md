---
title: "Bileşen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.component
- component_CPP
dev_langs:
- C++
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3edb2f68b479eeadca777e0707dd96e148d13fe8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="component"></a>bileşenleri
Gözatma bilgilerinin ya da kaynak dosyalarından bağımlılık bilgilerinin toplanmasını denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      #pragma component( browser, { on | off }[, references [, name ]] )  
#pragma component( minrebuild, on | off )  
#pragma component( mintypeinfo, on | off )  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="browser"></a>Tarayıcı  
 Toplama işlemini açıp kapatabilir ve bilgiler toplanırken dikkate alınmayacak adları belirtebilirsiniz.  
  
 Açık veya kapalı'yı kullanmak pragmadan ileri doğru gözatma bilgilerinin toplanmasını denetler. Örneğin:  
  
```  
#pragma component(browser, off)  
```  
  
 Derleyicinin gözatma bilgilerini toplamasını durdurur.  
  
> [!NOTE]
>  Bu pragma Gözat bilgilerle toplama üzerinde açmak için [gözatma bilgilerini ilk etkinleştirilmelidir](../build/reference/building-browse-information-files-overview.md).  
  
 **Başvuruları** seçeneği ile veya olmadan kullanılabilir *adı* bağımsız değişkeni. Kullanarak **başvuruları** olmadan *adı* üzerinde veya başvuruları toplamayı devre dışı bırakır (ancak, toplanacak diğer gözatma bilgilerini devam eder). Örneğin:  
  
```  
#pragma component(browser, off, references)  
```  
  
 Derleyicinin başvuru bilgilerini toplama işlemini durdurur.  
  
 Kullanarak **başvuruları** ile *adı* ve **kapalı** başvurular engeller *adı* Gözat bilgi penceresinde görüntülenmesini. İlgilenmediğiniz adları ve türleri gözardı etmek ve gözatma bilgisi dosyalarının boyutunu küçültmek için bu sözdizimini kullanın. Örneğin:  
  
```  
#pragma component(browser, off, references, DWORD)  
```  
  
 başvurular yoksayar **DWORD** o noktadan. Başvuruları için toplama kapatabilirsiniz `DWORD` çubuğundaki Geri kullanarak **üzerinde**:  
  
```  
#pragma component(browser, on, references, DWORD)  
```  
  
 Bu, başvurular toplamaya devam etmek için tek yoludur *adı*; herhangi açıkça etkinleştirmelisiniz *adı* , devre dışı bırakmış.  
  
 Önişlemci aşmasını önlemek için *adı* (genişletme gibi **NULL** için **0**), etrafına tırnak işareti koyun:  
  
```  
#pragma component(browser, off, references, "NULL")  
```  
  
## <a name="minimal-rebuild"></a>En Az Yeniden Derleme  
 Visual C++ en az yeniden derleme özelliği, derleyicinin disk alanında yer kaplayan C++ sınıf bağımlılık bilgileri oluşturup depolamasını gerektirir. Disk alanı kaydetmek için kullanabileceğiniz `#pragma component( minrebuild, off )` her gerekmeyen bağımlılık bilgi, örneğin, değişmeyen üstbilgi dosyaları topla. INSERT `#pragma component(minrebuild, on)` bağımlılık toplamayı değişmeyen sınıfları tekrar sonra.  
  
## <a name="reduce-type-information"></a>Tür Bilgilerini Azaltma  
 **Mintypeinfo** seçeneği belirtilen bölgeyi hata ayıklama bilgileri azaltır. Bu bilgilerin hacmi epey büyüktür; .pdb ve .obj dosyalarını etkiler. mintypeinfo bölgesindeki sınıflarda ve yapılarda hata ayıklaması yapamazsınız. mintypeinfo seçeneğini kullanmak aşağıdaki uyarıyı önlemeye yardımcı olabilir:  
  
```  
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information  
```  
  
 Daha fazla bilgi için bkz: [en az yeniden etkinleştirme](../build/reference/gm-enable-minimal-rebuild.md) (/ Gm) derleyici seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)