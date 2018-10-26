---
title: Derleyici Hatası C2842 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6143249871384d89227d63fe1900814ae5077fd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055248"
---
# <a name="compiler-error-c2842"></a>Derleyici Hatası C2842

'class': yönetilen bir WinRT türü kendi 'operator new' tanımlayamaz veya 'operator delete'

Kendi tanımlayabilirsiniz ** new işleci veya **delete işleci** yerel yığında bellek ayırmalarını yönetmek için. Ancak, yalnızca yönetilen yığında ayrılmış olduğundan başvuru sınıfları bu işleçler tanımlayamazsınız.

Daha fazla bilgi için [kullanıcı tanımlı işleçler (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2842 oluşturur.

```
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
