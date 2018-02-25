---
title: en iyi duruma getirme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae1988292b1f6dfa35f4cb77d145641528ed827f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="optimize"></a>optimize
Bir işlev tarafından işlevi temelinde gerçekleştirilecek iyileştirmelerini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **En iyi duruma getirme** pragma dışında bir işlev görünmesi gerekir ve pragma görülen sonra tanımlanan ilk işlevi etkili olur. **Üzerinde** ve **kapalı** bağımsız değişkenleri kapatma belirtilen seçenekler *en iyi duruma getirme listesi* açmak veya kapatmak.  
  
 *En iyi duruma getirme listesi* sıfır veya daha çok parametrelerden biri aşağıdaki tabloda gösterilen olabilir.  
  
### <a name="parameters-of-the-optimize-pragma"></a>Pragma İyileştir parametreleri  
  
|Parametre|En iyi duruma getirme türü|  
|--------------------|--------------------------|  
|**g**|Global iyileştirmeler sağlar.|  
|**s** veya **t**|Makine kodu kısa veya hızlı dizisi belirtin.|  
|**y**|Çerçeve işaretçisi program yığında oluşturur.|  
  
 İle kullanılan aynı harf bunlar [/O](../build/reference/o-options-optimize-code.md) derleyici seçenekleri. Örneğin, aşağıdaki pragma eşdeğerdir **/Os** derleyici seçeneği:  
  
```  
#pragma optimize( "ts", on )  
```  
  
 Kullanarak **en iyi duruma getirme** boş dize ile pragma (**""**) yönergesi özel şekildedir:  
  
 Kullandığınızda **kapalı** parametresi, Kapat, bu konunun önceki kısımlarında tabloda listelenen en iyi duruma getirme, açar.  
  
 Kullandığınızda **üzerinde** parametresi ile belirtilen olanlar için en iyi duruma getirme sıfırlar, [/O](../build/reference/o-options-optimize-code.md) derleyici seçeneği.  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)