---
title: Derleyici Hatası C3807 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3807
dev_langs:
- C++
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7531d5e758828a83bc94ed88b137033182bbfea6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041122"
---
# <a name="compiler-error-c3807"></a>Derleyici Hatası C3807

'type': ComImport özniteliğine sahip sınıf 'type2' türetilemez; yalnızca arabirim uygulamaya izin verilir

Tan türetilmiş bir tür <xref:System.Runtime.InteropServices.ComImportAttribute> yalnızca bir arabirim uygulayabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3807 oluşturur.

```
// C3807.cpp
// compile with: /clr /c
ref struct S {};
interface struct I {};

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 : S {};   // C3807
ref struct S2 : I {};
```