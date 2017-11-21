---
title: "-ARALIĞI | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /RANGE
dev_langs: C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2558beae1a7bd689beba001f4637b1109b70faa5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [DUMPBIN seçenekleri](../../build/reference/dumpbin-options.md)