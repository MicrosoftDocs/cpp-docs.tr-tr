---
title: Bağlayıcı Araçları Uyarısı LNK4078
ms.date: 11/04/2016
f1_keywords:
- LNK4078
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
ms.openlocfilehash: 9ce72f476aa85434acd5277d0307ffc61e0a0214
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990995"
---
# <a name="linker-tools-warning-lnk4078"></a>Bağlayıcı Araçları Uyarısı LNK4078

farklı özniteliklere sahip birden çok ' bölüm adı ' bölümü bulundu

BAĞLANTı, aynı ada ancak farklı özniteliklere sahip iki veya daha fazla bölüm buldu.

Bu uyarı, bir içeri aktarma kitaplığı veya bağlantı ya da LıB 'in önceki bir sürümü tarafından oluşturulan dışarı aktarma dosyası nedeniyle oluşabilir.

Dosyayı yeniden oluşturun ve yeniden bağlayın.

## <a name="example"></a>Örnek

Ayrıca LNK4078, bir kırılmaya neden olabilir: x86 üzerinde [init_seg](../../preprocessor/init-seg.md) tarafından adlandırılan bölüm okuma/yazma, artık salt okunurdur.

Aşağıdaki örnek LNK4078 oluşturur.

```cpp
// LNK4078.cpp
// compile with: /W1
// LNK4078 expected
#include <stdio.h>
#pragma warning(disable : 4075)
typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors to call
PF pfx[200];   // pointers to destructors.

struct A { A() {} };

int myexit (PF pf) { return 0; }

#pragma section(".mine$a", read, write)
// try the following line instead
// #pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) int ii = 1;

#pragma section(".mine$z", read, write)
// try the following line instead
// #pragma section(".mine$z", read)
__declspec(allocate(".mine$z")) int i = 1;

#pragma data_seg()
#pragma init_seg(".mine$m", myexit)
A bbbb;
A cccc;
int main() {}
```
