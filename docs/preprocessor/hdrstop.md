---
title: hdrstop | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
dev_langs:
- C++
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1c628efaf45be87dcfc046cf1774c762c157f4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="hdrstop"></a>hdrstop
Ön derleme dosya adları ve derleme durumunun kaydedildiği konum üzerinde ek denetim olanağı verir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma hdrstop [( "filename" )]    
```  
  
## <a name="remarks"></a>Açıklamalar  
 *Filename* kullanın veya oluşturmak için önceden derlenmiş üst bilgi dosyasının adıdır (mı bağlı olarak [/Yu](../build/reference/yu-use-precompiled-header-file.md) veya [/Yc](../build/reference/yc-create-precompiled-header-file.md) belirtilir). Varsa *filename* yol belirtimi içermiyor önceden derlenmiş üst bilgi dosyasını kaynak dosyası ile aynı dizinde olduğu varsayılır.  
  
 C veya C++ dosya içeriyorsa, bir **hdrstop** /Yc ile derlendiğinde pragma derleyici pragma konumunu kadar derleme durumunu kaydeder. Pragmayı izleyen herhangi bir kodun derlenmiş hali kaydedilmez.  
  
 Kullanım *filename* derlenmiş durumu kaydedilir önceden derlenmiş üst bilgi dosyasını adlandırın. Arasında bir boşluk **hdrstop** ve *filename* isteğe bağlıdır. Belirtilen dosya adı **hdrstop** pragma bir dizedir ve bu nedenle herhangi bir C veya C++ dize kısıtlamalar geçerlidir. Özellikle, tırnak işaretleri içine almalı ve dizin adlarını belirtmek için çıkış karakterini (ters eğik çizgi) kullanmalısınız. Örneğin:  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
 Önceden derlenmiş üstbilgi dosyasının adı, öncelik sırasına göre, aşağıdaki kurallara uygun şekilde belirlenir:  
  
1.  /Fp derleyici seçeneğinin bağımsız değişkeni  
  
2.  *Filename* # bağımsız değişkeni**hdrstop pragması**  
  
3.  .PCH uzantılı kaynak dosyanın temel adı  
  
 /Yc ve /Yu seçenekleri için iki derleme seçeneklerin ikisi varsa veya **hdrstop** pragma belirtir bir dosya adı, kaynak dosyasının temel adı önceden derlenmiş üst bilgi dosyasını temel adı olarak kullanılır.  
  
 Makro değiştirme işlemini gerçekleştirmek için ön işlem komutları da kullanabilirsiniz:  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
 Aşağıdaki kuralları where yöneten **hdrstop** pragma yerleştirilebilen:  
  
-   Bir veri veya işlev bildiriminin ya da tanımının dışında görünmelidir.  
  
-   Bir üstbilgi dosyasında değil, kaynak dosyada belirtilmesi gerekir.  
  
## <a name="example"></a>Örnek  
  
```  
#include <windows.h>                 // Include several files  
#include "myhdr.h"  
  
__inline Disp( char *szToDisplay )   // Define an inline function  
{  
    ...                              // Some code to display string  
}  
#pragma hdrstop  
```  
  
 Bu örnekte, **hdrstop** pragma iki dosyaları dahil edilmiştir ve satır içi işlev tanımlanan sonra görüntülenir. Bu, ilk başta pragmanın tek bir yerleşimi olarak görünebilir. Ancak, bu el ile ön derleme seçenekleri, /Yc ve /Yu, kullanarak düşünün **hdrstop** pragma sizin için tüm kaynak dosyaları derleneceği mümkün kılar — bile satır içi kod. Microsoft derleyicisi, size yalnızca veri bildirimlerini ön derlemek gibi bir sınırlama getirmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)