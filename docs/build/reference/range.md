---
title: -ARALIĞI | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d06d699500ba3ea441af61a2e2a5a0da3f96903a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374430"
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