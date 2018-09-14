---
title: Derleyici Hatası C2857 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2857
dev_langs:
- C++
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49e94e12b4cdf07d9f7fe74dd481bbc032a937eb
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601385"
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