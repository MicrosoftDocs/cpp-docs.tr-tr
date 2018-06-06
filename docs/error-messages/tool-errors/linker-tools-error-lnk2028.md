---
title: Bağlayıcı araçları hatası LNK2028 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2028
dev_langs:
- C++
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9c8eaa03927f51acd3c3d84731e9ef2b282b7c6
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704160"
---
# <a name="linker-tools-error-lnk2028"></a>Bağlayıcı Araçları Hatası LNK2028

"*exported_function*" (*decorated_name*) işlevinde başvurulan "*function_containing_function_call*" (*decorated_name*)

## <a name="remarks"></a>Açıklamalar

Yerel bir işleve saf görüntüsüne alınmaya çalışılırken örtük çağırma kurallarını yerel ve saf derlemeler arasında farklı olduğunu unutmayın.

**/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

## <a name="example"></a>Örnek

Bu kod örneği, çağırma olduğu örtük olarak dışarı aktarılan, yerel, işlevi içeren bir bileşen oluşturur [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2028.cpp
// compile with: /LD
__declspec(dllexport) int func() {
   return 3;
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, yerel işlevi tüketir saf bir istemci oluşturur. Ancak, çağırma altında **/CLR: pure** olan [__clrcall](../../cpp/clrcall.md). Aşağıdaki örnek LNK2028 oluşturur.

```cpp
// LNK2028_b.cpp
// compile with: /clr:pure lnk2028.lib
// LNK2028 expected
int func();

int main() {
   return func();
}
```