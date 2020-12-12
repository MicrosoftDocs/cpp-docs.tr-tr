---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3846'
title: Derleyici hatası C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: 13c9cb7a9dde3710cac31d8ee79fb148f8ff67bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255398"
---
# <a name="compiler-error-c3846"></a>Derleyici hatası C3846

' symbol ': ' Assembly2 ' öğesinden sembol içeri aktarılamıyor: ' symbol ' zaten başka bir ' assembly1 ' derlemesinden içeri aktarılmış

Başvurulan bir derlemeden daha önce içeri aktarıldığından, bir sembol başvurulan derlemeden içeri aktarılamadı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3846 oluşturur:

```cpp
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

Ardından bunu derleyin:

```cpp
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
