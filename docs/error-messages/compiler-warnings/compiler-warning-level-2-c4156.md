---
title: Derleyici Uyarısı (Düzey 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: 7d9a4ed09f026267e2c0f37fbbe4550ecd668dfc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350471"
---
# <a name="compiler-warning-level-2-c4156"></a>Derleyici Uyarısı (Düzey 2) C4156

'delete'; dizi biçimi kullanılmadan bir dizi ifadesinin silinmesi dizi biçimi kullanıldı

Dizi olmayan tür **Sil** dizi nelze odstranit. Derleyici çevrilmiş **Sil** dizi biçimi için.

Bu uyarı, yalnızca Microsoft uzantıları altında (/Ze) oluşur.

## <a name="example"></a>Örnek

```
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```