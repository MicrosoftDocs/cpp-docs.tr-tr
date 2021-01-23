---
description: Microsoft C/C++ ' da hdrstop yönergesi hakkında daha fazla bilgi edinin pragma
title: hdrstop pragma
ms.date: 01/22/2021
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
helpviewer_keywords:
- hdrstop pragma
- pragma, hdrstop
no-loc:
- pragma
ms.openlocfilehash: caeaeb4a44182b6ba2edfa385a1504fde998cc43
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713616"
---
# <a name="hdrstop-no-locpragma"></a>`hdrstop` pragma

Ön derleme dosya adları üzerinde ve derleme durumunun kaydedildiği konum üzerinde daha fazla denetim sağlar.

## <a name="syntax"></a>Syntax

> **`#pragma hdrstop`** [("*filename*")]

## <a name="remarks"></a>Açıklamalar

*Dosya adı* , kullanılacak veya oluşturulacak ön derlenmiş üstbilgi dosyasının adıdır (veya belirtilen olmasına bağlı olarak [`/Yu`](../build/reference/yu-use-precompiled-header-file.md) [`/Yc`](../build/reference/yc-create-precompiled-header-file.md) ). *Dosya adı* bir yol belirtimi içermiyorsa, ön derlenmiş üstbilgi dosyasının kaynak dosyayla aynı dizinde olduğu varsayılır.

Bir C veya C++ dosyası **`hdrstop`** pragma ile **`/Yc`** derlendikleri zaman içeriyorsa, derleyici derlemenin durumunu öğesinin konumuna kaydeder pragma . Takip eden herhangi bir kodun derlenmiş durumu pragma kaydedilmez.

Derlenmiş durumun kaydedildiği ön derlenmiş üstbilgi dosyasını adlandırmak için *dosya adı* ' nı kullanın. **`hdrstop`** Ve *dosya adı* arasında boşluk isteğe bağlıdır. İçinde belirtilen dosya adı **`hdrstop`** pragma bir dizedir ve herhangi bir C veya C++ dizesinin kısıtlamalarına tabidir. Özellikle, tırnak işaretleri içine almalısınız ve **`\`** dizin adlarını belirtmek için kaçış karakterini (ters eğik çizgi) kullanmanız gerekir. Örneğin:

```C
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

Önceden derlenmiş üstbilgi dosyasının adı, öncelik sırasına göre, aşağıdaki kurallara uygun şekilde belirlenir:

1. Derleyici seçeneğinin bağımsız değişkeni **`/Fp`**

2. *Dosya adı* bağımsız değişkeni`#pragma hdrstop`

3. PCH uzantılı kaynak dosyanın temel adı

**`/Yc`** Ve **`/Yu`** seçeneklerinden hiçbiri veya **`hdrstop`** pragma bir dosya adı belirtilmezse, kaynak dosyanın temel adı önceden derlenmiş üstbilgi dosyasının temel adı olarak kullanılır.

Makro değiştirme işlemini gerçekleştirmek için ön işlem komutları da kullanabilirsiniz:

```C
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

Aşağıdaki kurallar, nerede **`hdrstop`** pragma yerleştirilebileceğini yönetir:

- Bir veri veya işlev bildiriminin ya da tanımının dışında görünmelidir.

- Bir üstbilgi dosyasında değil, kaynak dosyada belirtilmesi gerekir.

## <a name="example"></a>Örnek

```C
#include <windows.h>                 // Include several files
#include "myhdr.h"

__inline Disp( char *szToDisplay )   // Define an inline function
{
    // ...                           // Some code to display string
}
#pragma hdrstop
```

Bu örnekte, **`hdrstop`** pragma iki dosya eklendikten sonra görünür ve bir satır içi işlev tanımlanmıştır. Bu konum, ilk başta, için tek bir yerleştirme gibi görünebilir pragma . Bununla birlikte, el ile ön derleme seçeneklerini kullanmanın yanı sıra **`/Yc`** **`/Yu`** **`hdrstop`** pragma tüm kaynak dosyaları veya hatta satır içi kodu önceden derlemenize olanak tanır. Microsoft derleyicisi, yalnızca veri bildirimlerinin ön derlenmesini sınırlandırmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
