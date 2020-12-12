---
description: 'Daha fazla bilgi edinin: hdrstop pragması'
title: hdrstop pragması
ms.date: 08/29/2019
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
ms.openlocfilehash: 1fec99503adfb1d81f7da324db83e4c2b56a3912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167519"
---
# <a name="hdrstop-pragma"></a>hdrstop pragması

Ön derleme dosya adları ve derleme durumunun kaydedildiği konum üzerinde ek denetim sağlar.

## <a name="syntax"></a>Syntax

> **#pragma hdrstop** [("*filename*")]

## <a name="remarks"></a>Açıklamalar

*Dosya adı* , kullanılacak veya oluşturulacak ön derlenmiş üstbilgi dosyasının adıdır ( [/yu](../build/reference/yu-use-precompiled-header-file.md) veya [/rivc](../build/reference/yc-create-precompiled-header-file.md) 'nin belirtilmediğine bağlı olarak). *Dosya adı* bir yol belirtimi içermiyorsa, ön derlenmiş üstbilgi dosyasının kaynak dosyayla aynı dizinde olduğu varsayılır.

Bir C veya C++ dosyası ile derlendikten sonra bir **hdrstop** `/Yc` pragması içeriyorsa, derleyici derlemenin durumunu pragma 'ın konumuna kaydeder. Pragmayı izleyen kodun derlenmiş durumu kaydedilmez.

Derlenmiş durumun kaydedildiği ön derlenmiş üstbilgi dosyasını adlandırmak için *dosya adı* ' nı kullanın. **Hdrstop** ve *filename* arasındaki boşluk isteğe bağlıdır. **Hdrstop** pragması 'nda belirtilen dosya adı bir dizedir ve bu nedenle herhangi bir C veya C++ dizesinin kısıtlamalarına tabidir. Özellikle, tırnak işaretleri içine almalı ve dizin adlarını belirtmek için çıkış karakterini (ters eğik çizgi) kullanmalısınız. Örneğin:

```C
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

Önceden derlenmiş üstbilgi dosyasının adı, öncelik sırasına göre, aşağıdaki kurallara uygun şekilde belirlenir:

1. Derleyici seçeneğinin bağımsız değişkeni `/Fp`

2. *Dosya adı* bağımsız değişkeni`#pragma hdrstop`

3. .PCH uzantılı kaynak dosyanın temel adı

`/Yc`Ve seçenekleri için `/Yu` , iki derleme seçeneğinin veya **hdrstop pragmanın** bir dosya adı belirtmediği durumlarda kaynak dosyanın temel adı, önceden derlenmiş üstbilgi dosyasının temel adı olarak kullanılır.

Makro değiştirme işlemini gerçekleştirmek için ön işlem komutları da kullanabilirsiniz:

```C
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

Aşağıdaki kurallar **hdrstop** pragma 'un yerleştirilebileceği yeri yönetir:

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

Bu örnekte, **hdrstop** pragması iki dosya eklendikten sonra görünür ve bir satır içi işlev tanımlanmıştır. Bu konum, ilk başta, pragma için tek bir yerleştirme gibi görünebilir. Bununla birlikte, el ile ön derleme seçeneklerini kullanmanın `/Yc` ve `/Yu` **hdrstop** pragması ile tüm kaynak dosyaları (hatta satır içi kod) önceden derlemenize olanak tanıyan göz önünde bulundurun. Microsoft derleyicisi, size yalnızca veri bildirimlerini ön derlemek gibi bir sınırlama getirmez.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
