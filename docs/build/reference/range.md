---
title: "-ARALIĞI | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1ccca814a388a458513773247f79cecf87fcdeae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="range"></a>/RANGE
/RAWDATA veya /DISASM gibi diğer DUMPBIN seçenekleri ile kullanıldığında DUMPBIN çıktısını değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## <a name="flags"></a>Bayraklar  
 **vaMin**  
 DUMPBIN işlemini başlatmak istediğiniz sanal adres.  
  
 **vaMax** (isteğe bağlı)  
 DUMPBIN işlemi sona erdirmek için istediğiniz sanal adres. Belirtilmezse, DUMPBIN dosyasının sonuna gidin.  
  
## <a name="remarks"></a>Açıklamalar  
 Görüntüyü sanal adreslerini görmek için eşleme dosyası (RVA + Bankası) görüntüsü için kullandığınız **/DISASM** veya **/HEADERS** DUMPBIN veya Visual Studio hata ayıklayıcısında ayrıştırma penceresi seçeneği.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, **/aralığı** görüntüsünü değiştirmek için kullanılan **/disasm** seçeneği. Bu örnekte, başlangıç değerini ondalık bir sayı olarak ifade edilir ve bitiş değeri bir onaltılık sayı olarak belirtilir.  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)