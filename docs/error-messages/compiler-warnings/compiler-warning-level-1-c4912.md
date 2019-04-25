---
title: Derleyici Uyarısı (düzey 1) C4912
ms.date: 11/04/2016
f1_keywords:
- C4912
helpviewer_keywords:
- C4912
ms.assetid: ba1f1a66-8c20-4792-9ac8-43e49f729ae2
ms.openlocfilehash: 7a6f7df79a98685a7eec1582ae248ea3f620c5fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207062"
---
# <a name="compiler-warning-level-1-c4912"></a>Derleyici Uyarısı (düzey 1) C4912

'attribute': özniteliği bir iç içe geçmiş UDT'de davranışı tanımlı değil

İç içe geçmiş Udt'ler (bir tür tanımı, birleşim veya yapı olabilecek kullanıcı tanımlı türü) için uygulanan öznitelikleri yoksayılabilir.

Aşağıdaki kod nasıl bu uyarı oluşturulacağını gösterir:

```
// C4912.cpp
// compile with: /W1
#include <windows.h>
[emitidl, module(name="xx")];

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMy
{
};

[coclass, default(IMy), appobject, uuid("00000000-0000-0000-0000-000000000001")]
class CMy : public IMy
{
   [export, v1_enum] typedef enum myEnum { k3_1 = 1, k3_2 = 2 } myEnumv;   // C4912
};
int main()
{
}
```