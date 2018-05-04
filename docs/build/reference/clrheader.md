---
title: -CLRHEADER | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRHEADER
dev_langs:
- C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5896e12d5e3b3b3984884388d11c6380e900d73d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
  
 Görüntüyü bir ortak dil çalışma zamanı için oluşturulmuş program aracılığıyla da denetleyebilirsiniz.  Daha fazla bilgi için bkz: [nasıl yapılır: bir resmin yerel mi yoksa CLR mi olduğunu belirleme](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı bırakılmış ve derleyici gelecek bir sürümünde kaldırılacak. "Saf" veya "safe" olmalıdır kod C# için bağlantı noktası kurulmuş. 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)