---
title: Derleyici Hatası C2857
ms.date: 09/13/2018
f1_keywords:
- C2857
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
ms.openlocfilehash: 10c0ea3b54ded29bf80f83713cea33428dca6ca0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350445"
---
# <a name="compiler-error-c2857"></a>Derleyici Hatası C2857

> ' #include ' ifade /Yc ile belirtilen*filename* komut satırı seçeneği kaynak dosyasında bulunamadı

[/Yc](../../build/reference/yc-create-precompiled-header-file.md) seçeneği derlenmiş kaynak dosyada yer almayan bir dahil etme dosyasının adını belirtir.

## <a name="remarks"></a>Açıklamalar

Kullanırken **/Yc**<em>filename</em> kaynak dosyasını (PCH) önceden derlenmiş üst bilgi dosyası, oluşturma seçeneği bir kaynak dosyaya dahil etmelisiniz *filename* üst bilgi dosyası. En fazla ve belirtilen kaynak dosya tarafından eklenen her dosya *filename*, PCH dosyasına dahil edilir. Diğer kaynak dosyalarındaki kullanılarak derlenmiş **/Yu**<em>filename</em> PCH kullanmak için seçeneği dosya, bir dahil etme, *filename* dosyadaki ilk yorum olmayan satır olması gerekir. Derleyici bu önce kaynak dosyadaki her şeyi yoksayar.

Bu hataya neden olabilir bir `#include "filename"` bir koşullu derleme bloğundaki PCH kaynak dosyanıza derlenmedi.

## <a name="example"></a>Örnek

Tipik kullanım PCH kaynak dosyayı farklı bir kaynak dosyayı projenize atanır ve bir üst bilgi dosyası PCH üstbilgi dosyası olarak kullanılır. Tipik bir PCH üstbilgi dosyası tüm projenizde kullanılan kitaplığı üstbilgileri, ancak hala geliştirilmektedir yerel üstbilgiler vardır. Bu örnekte, PCH üstbilgi dosyası adlı *my_pch.h*.

```cpp
// my_pch.h
#pragma once
#include <stdio.h>
```

PCH kaynak dosyası kullanılarak derlenmiş **/Yc**<em>my_pch.h</em> seçeneği. Derleyici bu PCH üstbilgi dosyasının bir içerme bulamazsa C2857 oluşturur:

```cpp
// my_pch.cpp
// Compile by using: cl /EHsc /W4 /Yumy_pch.h /c my_pch.cpp

#if 0
#include "my_pch.h"  // C2857; remove conditional directives to fix
#endif
```

Bu PCH dosyası kullanmak için kaynak dosyaları kullanarak derlenmelidir **/Yu**<em>my_pch.h</em> seçeneği. PCH üstbilgi dosyası PCH kullanan kaynak dosyalarında ilk dahil edilmelidir:

```cpp
// C2857.cpp
// Compile my_pch.cpp first, then
// compile by using: cl /EHsc /W4 /Yumy_pch.h my_project.cpp my_pch.obj
// Include the pch header before any other non-comment line
#include "my_pch.h"

int main()
{
    puts("Using a precompiled header file.\n");
}
```