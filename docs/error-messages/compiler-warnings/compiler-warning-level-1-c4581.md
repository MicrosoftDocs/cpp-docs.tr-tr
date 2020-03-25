---
title: Derleyici Uyarısı (düzey 1) C4581
ms.date: 11/04/2016
f1_keywords:
- C4581
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
ms.openlocfilehash: 491121bc236c54ce5b74c76abfa6a650ff7a99ff
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162172"
---
# <a name="compiler-warning-level-1-c4581"></a>Derleyici Uyarısı (düzey 1) C4581

kullanım dışı davranış: ' "Dize1" ' özniteliği işlemek için ' dize2 ' ile değiştiriliyor

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin bir sonucu olarak oluşturulabilir: görsel C++ öznitelikler için parametre denetimi.

Önceki sürümlerde öznitelik değerleri, tırnak işaretleri içine alınmış olsun ya da etmeksizin kabul edildi. Değer bir sabit listesi ise, tırnak işaretleri içine alınmalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4581 oluşturur.

```cpp
// C4581.cpp
// compile with: /c /W1
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {};

[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581
// try the following line instead
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]
class CSample : public IMyI {};
```
