---
title: -CLRHEADER | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /CLRHEADER
dev_langs: C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 699fa0e97236b1c5cf207e73dcbb39156bfbb130
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="clrheader"></a>/CLRHEADER
```  
/CLRHEADER file  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 `file`  
 Bir görüntü dosyası ile oluşturulan [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="remarks"></a>Açıklamalar  
 CLRHEADER herhangi bir yönetilen programında kullanılan .NET üstbilgileri hakkındaki bilgileri görüntüler. Çıkış, .NET üstbilgi ve bölümleri üstbilgisinde bayt boyutunu ve konumunu gösterir.  
  
 Yalnızca [/HEADERS](../../build/reference/headers.md) DUMPBIN seçeneği ile üretilen dosyalarda kullanıma [/GL](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği.  
  
 / CLR ile derlenen bir dosyada /CLRHEADER kullanıldığında, olacaktır bir **clr üstbilgi:** DUMPBIN çıktı bölümünde.  Değeri **bayrakları** hangi/CLR seçeneği kullanılan gösterir:  
  
-   0--/ CLR (yerel kod görüntü içerebilir).  
  
-   1--/ CLR: safe (MSIL yalnızca, herhangi bir CLR platformda çalıştırılabilir ve büyük olasılıkla doğrulanabilen Görüntü'dir).  
  
-   3--/ CLR: pure (görüntüdür MSIL yalnızca x86 üzerinde çalıştırmak yalnızca kullanabilirsiniz ancak platformlar).  
  
 Görüntüyü bir ortak dil çalışma zamanı için oluşturulmuş program aracılığıyla da denetleyebilirsiniz.  Daha fazla bilgi için bkz: [nasıl yapılır: bir resmin yerel mi yoksa CLR mi olduğunu belirleme](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DUMPBIN seçenekleri](../../build/reference/dumpbin-options.md)