---
title: hdrstop
ms.date: 11/04/2016
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
ms.openlocfilehash: 5dc47e4b2ec264182d26925df60bf3ee29871b65
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497095"
---
# <a name="hdrstop"></a>hdrstop
Ön derleme dosya adları ve derleme durumunun kaydedildiği konum üzerinde ek denetim olanağı verir.

## <a name="syntax"></a>Sözdizimi

```
#pragma hdrstop [( "filename" )]
```

## <a name="remarks"></a>Açıklamalar

*Filename* kullanın veya oluşturmak için önceden derlenmiş üst bilgi dosyasının adı (bağlı olarak [/Yu](../build/reference/yu-use-precompiled-header-file.md) veya [/Yc](../build/reference/yc-create-precompiled-header-file.md) belirtilir). Varsa *filename* bir yol belirtimi içermiyor önceden derlenmiş üstbilgi dosyasının kaynak dosyayla aynı dizinde olduğu varsayılır.

Bir C veya C++ dosyası içeriyorsa bir **hdrstop** pragma ile derlendiğinde `/Yc`, derleyici derleme pragmanın konumuna kadar durumunu kaydeder. Pragmayı izleyen herhangi bir kodun derlenmiş hali kaydedilmez.

Kullanım *filename* derlenmiş halin kaydedildiği önceden derlenmiş üstbilgi dosyasını adlandırmak için. Arasında boşluk **hdrstop** ve *filename* isteğe bağlıdır. Belirtilen dosya adı **hdrstop** pragma bir dizedir ve bu nedenle herhangi bir C veya C++ dizelerinin kısıtlamalarına tabi olur. Özellikle, tırnak işaretleri içine almalı ve dizin adlarını belirtmek için çıkış karakterini (ters eğik çizgi) kullanmalısınız. Örneğin:

```
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

Önceden derlenmiş üstbilgi dosyasının adı, öncelik sırasına göre, aşağıdaki kurallara uygun şekilde belirlenir:

1. Bağımsız değişkeni `/Fp` derleyici seçeneği

2. *Filename* bağımsız değişkeni `#pragma hdrstop`

3. .PCH uzantılı kaynak dosyanın temel adı

İçin `/Yc` ve `/Yu` seçenekleri, iki derleme seçeneği hiçbiri, ya da **hdrstop** pragması, bir dosya adı belirtmiyorsa, kaynak dosyanın temel adı önceden derlenmiş üstbilgi dosyasının temel adı olarak kullanılır.

Makro değiştirme işlemini gerçekleştirmek için ön işlem komutları da kullanabilirsiniz:

```
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

Aşağıdaki kuralları nereye yöneten **hdrstop** pragma yerleştirilebileceğini:

- Bir veri veya işlev bildiriminin ya da tanımının dışında görünmelidir.

- Bir üstbilgi dosyasında değil, kaynak dosyada belirtilmesi gerekir.

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

Bu örnekte, **hdrstop** pragması, iki dosya eklendikten ve bir satır içi işlevi tanımlandıktan sonra görünür. Bu, ilk başta pragmanın tek bir yerleşimi olarak görünebilir. , Ancak, el ile ön derleme Seçenekleri'ni kullanarak göz önünde bulundurun `/Yc` ve `/Yu`, ile **hdrstop** pragması, tüm kaynak dosyaları derleneceği mümkün kılar — bile satır içi kod. Microsoft derleyicisi, size yalnızca veri bildirimlerini ön derlemek gibi bir sınırlama getirmez.

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)